# 📈 Market Anomalies or Structural Shift? Fama-French in A-Share

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success.svg)]()

## 📝 项目摘要 (Executive Summary)
本项目旨在验证 Fama-French 三因子模型在中国 A 股市场的有效性。通过对 2016-2025 年近十年 CSMAR 高频交易数据的深度挖掘，本项目不仅复现了经典定价模型，更揭示了中国市场特有的**“ Lottery Preference（彩票效应）”**与**“价值陷阱（Value Trap）”**现象。

## 🔍 核心发现 (Key Findings)
*   **因子失效:** 传统价值因子 (HML) 在样本期间出现显著负溢价 (Sharpe Ratio: -1.98)，验证了 A 股“价值陷阱”的普遍存在。
*   **Alpha 之谜:** 在 Small-Growth (SL) 组合中观察到显著的正向 Alpha (0.83% per month)，揭示了中国散户驱动型市场对小盘成长股的非理性溢价。
*   **流动性冲击:** Amihud 价格冲击指数与因子溢价存在强负相关，证明了中国市场资产定价受流动性约束极深。

## 🛠 技术栈 (Tech Stack)
*   **数据工程:** Pandas, NumPy (Look-ahead bias 规避, MAD 缩尾处理, 单位校准)
*   **统计建模:** Statsmodels (Newey-West HAC 稳健标准误回归)
*   **可视化:** Matplotlib, LaTeX 排版 (全英文报告输出)

## 📂 项目结构 (Project Structure)
| 文件名 | 功能描述 |
| :--- | :--- |
| `01_data_cleaning.ipynb` | **Data-First 处理逻辑**：解决 CSMAR 原始数据单位错配与异常值清洗 |
| `02_factor_construction.ipynb` | 因子合成与 FF3 滚动回归分析 |
| `data/` | 存储原始交易数据及清洗后的中间结果 |
| `ff3_factors_plot.png` | 累计财富路径图（展示 Value Trap 与 SOE rally 的脱节） |

## 💡 对未来研究的建议 (Reflections)
在实证复盘中，我意识到直接套用 US-based 模型存在局限：
1. **ROE 补充:** 传统 BM 因子失效，未来建议引入 ROE 财务指标以过滤劣质公司。
2. **微观市值校准:** 等权 (EW) 组合放大了微盘股风险，后续将迭代为市值加权 (Value-Weighted) 方案以修正极端偏差。

---
*Research by Jiaxiang Liu | 2026 | CUFE School of Finance*
