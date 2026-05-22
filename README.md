# E-commerce Landing Page A/B Test Analysis for Online Retail

## Executive Summary

This project evaluates whether an e-commerce company should replace its old landing page with a new version. The business question is simple: does the redesigned page improve user conversion enough to justify rollout?

After cleaning invalid experiment assignments and duplicate users, the analysis used **290,584 valid user records**. The control group using the old page converted at **12.04%**, while the treatment group using the new page converted at **12.30%**. The new page delivered a lift of about **0.26 percentage points**, or roughly **2,606 additional conversions per 1 million visitors**, with a z-test p-value of **0.0317**.

The z-test shows a statistically significant difference between the old and new pages, but the effect size is extremely small (**Cohen's d = -0.0080**). This means the significant result is likely driven by the very large sample size, not by a large business improvement from the new page. Therefore, the company should also evaluate revenue impact, launch cost, and user experience before deciding whether to fully use the new page.

## Business Problem

Landing pages directly influence customer acquisition, checkout starts, and revenue. Even a small conversion-rate change can matter for a high-traffic e-commerce business, but launching a new page also creates engineering cost, design cost, and potential customer-experience risk.

The company needs evidence before deciding whether to keep the old page or adopt the new page. This project uses A/B testing to answer whether the new page produces a measurable conversion improvement and whether that improvement is large enough for business stakeholders to act on.

## Methodology

- Loaded the original A/B testing dataset with user ID, timestamp, experiment group, landing page version, and conversion status.
- Checked data quality, including missing values, incorrect group-page assignments, and duplicate users.
- Removed mismatched experiment records:
  - Treatment users who saw the old page.
  - Control users who saw the new page.
- Removed duplicate user records to keep one observation per user.
- Verified that traffic allocation was balanced, with about **50.01%** of users seeing the new page and **49.99%** seeing the old page.
- Calculated conversion rates for control and treatment groups.
- Ran a two-proportion z-test at alpha = 0.05.
- Calculated Cohen's d to evaluate practical effect size.

## Skills

- Python data analysis with `pandas` and `numpy`
- Data cleaning and experiment validation
- A/B test design logic
- Conversion-rate analysis
- Two-proportion z-test
- Statistical significance interpretation
- Effect-size interpretation with Cohen's d

## Results & Business Recommendation

The new page converted slightly better than the old page:

| Metric | Old Page / Control | New Page / Treatment |
|---|---:|---:|
| Valid users | 145,274 | 145,310 |
| Converted users | 17,489 | 17,872 |
| Conversion rate | 12.04% | 12.30% |

Key test results:

- Absolute lift: **+0.26 percentage points**
- Relative lift: **+2.16%**
- Z-statistic: **-2.1484**
- P-value: **0.0317**
- Cohen's d: **-0.0080**

Business recommendation:

- The new page shows a statistically significant conversion improvement, so it is a candidate for rollout.
- The lift is small, so the company should not roll it out blindly if the new page requires meaningful engineering, design, compliance, or support cost.
- If the page is inexpensive and low-risk to launch, test it with a small share of users first and keep tracking conversion rate, bounce rate, checkout behavior, revenue per visitor, and customer feedback.
- If the business needs a larger impact, continue experimentation with more substantial UX, copy, offer, personalization, or checkout-flow changes.

---

# 面向在线零售行业的电商落地页 A/B 测试分析

## 摘要

本项目评估一家电商公司是否应该用新版落地页替换旧版落地页。核心业务问题是：新版页面是否能有效提升用户转化，并且提升幅度是否足以支持上线决策。

在清洗实验分组错误和重复用户之后，本次分析使用了 **290,584 条有效用户记录**。旧页面对照组转化率为 **12.04%**，新版页面实验组转化率为 **12.30%**。新版页面带来约 **0.26 个百分点** 的绝对提升，相当于每 **100 万访问用户约增加 2,606 次转化**，z 检验的 p 值为 **0.0317**。

Z 检验显示新旧页面存在统计显著差异，但效应量非常小（**Cohen's d = -0.0080**）。这说明显著性很可能主要来自于样本量很大，而不是因为新版页面带来了明显的业务提升。因此，公司还需要结合收入影响、上线成本和用户体验，再决定是否全面使用新版页面。

## 业务问题

落地页会直接影响用户获取、下单意愿和收入表现。对于高流量电商平台，即使很小的转化率变化也可能带来可观的订单增量；但上线新版页面也会带来研发、设计、运营和用户体验风险。

公司需要用数据判断是否保留旧页面，还是切换到新版页面。本项目通过 A/B 测试判断新版页面是否带来可衡量的转化提升，以及这个提升是否值得业务团队采取行动。

## 分析方法

- 读取原始 A/B 测试数据，包括用户 ID、时间戳、实验组、页面版本和是否转化。
- 检查数据质量，包括缺失值、实验组与页面版本不匹配、重复用户。
- 删除实验逻辑错误的数据：
  - 实验组用户看到旧页面。
  - 对照组用户看到新页面。
- 删除重复用户，保证每个用户只保留一条记录。
- 检查流量分配是否均衡，新页面用户占 **50.01%**，旧页面用户占 **49.99%**。
- 计算对照组和实验组转化率。
- 在 alpha = 0.05 下进行双样本比例 z 检验。
- 使用 Cohen's d 评估实际效应大小。

## 技能

- 使用 `pandas` 和 `numpy` 进行 Python 数据分析
- 数据清洗与实验数据校验
- A/B 测试设计逻辑
- 转化率分析
- 双样本比例 z 检验
- 统计显著性解读
- 使用 Cohen's d 解读效应量

## 分析结果与业务建议

新版页面的转化率略高于旧版页面：

| 指标 | 旧页面 / 对照组 | 新页面 / 实验组 |
|---|---:|---:|
| 有效用户数 | 145,274 | 145,310 |
| 转化用户数 | 17,489 | 17,872 |
| 转化率 | 12.04% | 12.30% |

关键检验结果：

- 绝对提升：**+0.26 个百分点**
- 相对提升：**+2.16%**
- Z 统计量：**-2.1484**
- P 值：**0.0317**
- Cohen's d：**-0.0080**

业务建议：

- 新版页面带来了统计显著的转化率提升，因此可以作为上线候选方案。
- 但提升幅度很小，如果新版页面需要较高的研发、设计、合规或运营成本，不建议仅凭本次结果直接全面上线。
- 如果上线成本低、风险低，可以先让一小部分用户使用新版页面，并继续观察转化率、跳出率、结账行为、每访客收入和用户反馈。
- 如果业务目标是获得更明显增长，应继续测试更有力度的页面设计、文案、优惠信息、个性化推荐或结账流程优化。
