# AI Trading Research Summary — 2026-10-21

> **Status: RESEARCH ONLY. NO LIVE ORDERS. NO VERIFIED PROFITABLE EDGE.**  
> 本文件依据截至 2026-10-21 的历史实验记录整理。不是投资建议，也不表示已完成实盘测试。

## 1. 研究目标 / Objective

使用 Python 研究 BTC/USDT **1 小时 K 线**，验证技术指标策略和机器学习模型能否在考虑交易成本后，产生稳定且可重复的交易优势。

研究过程包括：数据获取 → 指标与信号 → 策略回测 → 成本和风险分析 → 时间顺序验证 → 机器学习 → 历史模拟交易 → 随机基准比较。

## 2. 技术栈 / Tech stack

- **语言**：Python（Windows，虚拟环境 `.venv`）
- **数据**：pandas、NumPy；BTC/USDT OHLCV 1H historical candles
- **可视化**：Matplotlib
- **机器学习**：scikit-learn（StandardScaler、LogisticRegression、RandomForest、HistGradientBoosting）
- **开发工具**：VS Code、Git/GitHub
- **下一阶段计划**：Docker、Freqtrade、FreqAI（尚不代表已经安装或运行）

当前原始代码保存在本地 `AI-Trading-Bot` 项目中；**本仓库是学习路线与研究总结，不声称已上传全部交易源代码**。

## 3. 已完成的研究功能

1. **历史数据与特征**：获取约 8,760 根 BTC/USDT 1H K 线；计算 EMA50、EMA200、RSI14、历史收益、波动率、成交量变化。
2. **规则策略**：EMA/RSI 入场；测试 EMA 退出和只依靠止损/止盈两种版本。
3. **资金和交易成本**：Portfolio 账户模拟、仓位风险预算、手续费、滑点、止损、止盈、最大回撤。
4. **数据质量**：K 线间隔、时间排序、训练/验证/测试时间边界、目标标签与执行时间核对。
5. **历史验证**：时间顺序 Train/Validation/Test、Walk-Forward、多时间跨度信号研究、Bootstrap 和趋势/随机基准。
6. **AI 模型**：Logistic Regression、Random Forest、Gradient Boosting；比较 AUC、Brier、准确率、概率分组与特征筛选。
7. **历史 paper-style 回测**：模拟下一根开盘买入、再下一根开盘卖出；**不是连接交易所的实时 Paper Trading**。
8. **随机策略对照**：1000 次随机模拟，同样的 24 小时冷却期和每次 125 笔交易。

## 4. 核心历史结果

### 4.1 规则策略：全年历史回测

| Strategy | Simulated total return | Trades | Profit factor |
|---|---:|---:|---:|
| A — EMA Exit | **-24.37%** | 143 | 0.46 |
| B — Stop/Target Only | **-12.03%** | 63 | 0.71 |

策略 B 比 A 损失较少，但**仍然亏损**。历史结果不能预测未来。

### 4.2 机器学习：训练数据内部的 Walk-Forward

TOP_3 特征：`rsi14`, `return_1h`, `return_4h`。5 折滚动测试下：

| Model | Avg ROC AUC | Avg accuracy | Avg Brier |
|---|---:|---:|---:|
| Logistic Regression | **0.5335** | 51.64% | 0.2495 |
| Random Forest | 0.5274 | 51.72% | 0.2500 |
| Gradient Boosting | 0.5093 | 50.06% | 0.2534 |

预测能力很弱；**AUC 略高于 0.5 不等于具有可盈利的交易优势**。特征选择曾参考验证表现，不应视为完全独立的预先注册实验。最终 ML Test 子集尚未用于一套严格冻结规则后的独立验证。

### 4.3 原始 AI 历史模拟交易

假设初始 1,000 USDT，每次使用 10% 可用现金，不使用杠杆，单边手续费 0.1%，单边滑点 0.05%，持仓约 1 小时：

| Metric | Historical result |
|---|---:|
| Trades | 1,655 |
| Final equity | **601.21 USDT** |
| Total return | **-39.88%** |
| Net profitable trade rate | 20.48% |
| Fee cost, historical executed quantities | 256.35 USDT |

成本敏感性测试：使用完全相同的信号并重新按账户权益计算仓位，零交易成本情况下回报仍约 **-1.29%**，原始成本下约 **-39.88%**。因此不仅是费用问题，信号本身也未展示可靠优势。

### 4.4 冷却期与随机基准（探索性）

选用 **24H Cooldown** 后：

| Experiment | Return |
|---|---:|
| AI signals, 125 trades | **-4.8967%** |
| Random baseline, 1,000 trials, **exactly 125 trades each** | **-3.8631% mean** |
| Random median | -3.8513% |
| Random 5th–95th percentiles | -4.7843% to -2.9676% |
| Share of random trials beaten by AI | **3.60%** |

这表示：在这一特定随机基准设计里，AI 仅优于约 3.6% 的随机试验；**不是盈利概率，也不能直接当作严格统计检验的 p 值**。

**限制**：24H Cooldown 是经过观察历史结果后选出的；随机策略虽匹配交易次数和冷却期，却未完全匹配市场状态或每折交易分布。上述实验主要使用训练时期的历史数据，不是全新独立的样本外证据。

## 5. 关键研究教训

- **AI 预测 ≠ 盈利**：要证明优势，必须扣除交易费、滑点和实际执行约束。
- **防止未来信息泄漏**：特征必须只用已完成 K 线；信号与成交执行时间严格区分。
- **样本外验证重要**：避免对同一时期反复挑参数，随后声称策略经过独立验证。
- **回测不是实盘**：模拟开盘成交、固定滑点、止损的 K 线内部路径都可能偏乐观。
- **风险优先**：暂不连接真实交易资金、不使用杠杆，不允许大模型绕过硬性风险控制。

## 6. 下一阶段 / Next steps

- [ ] 保存旧 Python 项目和历史研究数据，避免为了迁移而覆盖已有成果。
- [ ] 在独立工作目录安装 **Freqtrade + Docker**（先研究官方回测与 Dry Run）。
- [ ] 重现一套明确成本假设的 BTC/USDT 历史基准回测，并记录版本、数据范围、参数和限制。
- [ ] 使用独立的风险规则：单笔风险上限、总风险上限、最大亏损限制、异常停机和人工紧急停止。
- [ ] 仅在验证框架可靠后探索 FreqAI；以真实未来时段的 Dry Run 和冻结规则检验策略。
- [ ] 若未找到稳定优势，继续研究，**不以真钱交易弥补研究不足**。

## 7. 项目入口 / References

- [Main learning roadmap](README.md)
- [October daily sprint](plans/2026-10-sprint.md)
- [Day 1 GitHub issue](https://github.com/Stanford0903/ai-roadmap/issues/1)

**Research checkpoint:** 2026-10-21.
