# Week05 – Sampling Distributions & Central Limit Theorem  
# 第五周：抽样分布与中心极限定理

> 对应 PPT：Class 5 – Introduction to Sampling Distributions, Point Estimation, Selecting a Sample, Other Sampling Methods。fileciteturn2file4

---

## 1. Population / Sample / Frame / Sampled Population 基本术语回顾

PPT 定义：fileciteturn2file4  

- **Population 总体**：我们感兴趣的所有元素（个体）的集合。  
- **Element 元素**：收集数据的实体（例如一个人、一家公司、一份合约）。  
- **Sample 样本**：从总体中抽取的一部分元素。  
- **Frame 抽样框**：可以从中选取样本的元素列表（如：900 份申请名单）。  
- **Sampled population 被抽样总体**：实际上样本是从中抽出的那一群（有时与理论总体略有区别）。  

我们通过样本统计量来估计总体特征（参数）。但样本只是总体的一部分，带来不确定性 → 抽样误差。

原子笔记：[[Concept-Population-and-Sample|Population & Sample]].

---

## 2. Point Estimation 点估计与抽样误差

- 例如：
  - 样本比例 p-hat 用来估计总体比例 p；  
  - 样本均值 x-bar 用来估计总体均值 μ。  
- 每次抽样会得到略有不同的样本 → p-hat 与 x-bar 会在不同样本之间波动。  
- 这种从样本到样本的自然波动叫做 **sampling variability / sampling error 抽样误差**，不是“犯错”，而是“样本不同”。fileciteturn2file4  

原子笔记：[[Concept-Sampling-Error|Sampling Error]].

---

## 3. Selecting a Sample 选取样本（有限 & 无限总体）

### 3.1 Finite Population Sampling 有限总体抽样

- 通常有一个明确的 frame（名单）。  
- 例子：St. Andrew’s College 收到 900 份申请，想抽取 30 份进行详细审查。fileciteturn2file4  
- **Simple Random Sample (SRS)**：  
  - 从 N 个元素中选 n 个，使所有 C(N, n) 种样本组合都有相同概率。  
- 实际操作中常用：
  - Excel RAND() 生成 0~1 的随机数，加在每个申请旁边；  
  - 按随机数排序，取最小的 30 个。  

PPT 示范了 Excel 中排序随机数的方法。

### 3.2 Sampling with / without Replacement 放回与不放回

- **With replacement 有放回**：每次抽完放回，下次抽样总体不变。  
- **Without replacement 不放回**：抽过的元素不再放回，下次抽的总体大小减少。  
- 实务中调查通常是不放回，但若 n 远小于 N（n/N < 0.05），可以**近似当作有放回**处理。fileciteturn2file4  

### 3.3 Infinite Population Sampling 无限总体抽样

- 很多场景中无法枚举所有元素：  
  - 生产线上不断产生的产品；  
  - 到店顾客流；  
  - 银行的交易记录等。fileciteturn2file4  
- 我们将这些看作由某个“过程”生成的无限总体。  
- 只要保证每个抽样单位：
  - 来自同一总体；  
  - 相互独立；  
  就可以视作从无限总体中抽样。  

原子笔记：[[Concept-Sampling-Distribution|Sampling Distribution]].

---

## 4. Sampling Distribution of Sample Proportion 样本比例的抽样分布

PPT 用大量模拟（例如 10,000 次抽样）展示：对于给定 population proportion p，每一次从同样大小的样本中计算 p-hat，会形成一个近似钟形的分布。fileciteturn2file4  

理论结论：  
- 真正比例为 p，样本量为 n 时：  
  - E(p-hat) = p（p-hat 无偏估计 p）；  
  - SD(p-hat) = sqrt(p(1−p) / n)。  
- 当 n 足够大时，p-hat 的分布形状近似正态。  

**为使正态模型有效，需要的条件（Assumptions and Conditions）：**fileciteturn2file4  

1. Independence Assumption 独立性假设：样本中的观测要相互独立。  
2. Randomization Condition 随机化条件：样本应该来自随机抽样或随机分组。  
3. 10% Condition：若是不放回抽样，则 n ≤ 0.1N。  
4. Success/Failure Condition 成功-失败条件：  
   - 期望成功数 np ≥ 10；  
   - 期望失败数 n(1−p) ≥ 10。  

在满足上述条件时，我们可以写：  
- p-hat 约 ~ Normal(mean = p, sd = sqrt(p(1−p)/n))。  

PPT 中 New York City 车险合同示例（p=0.92, n=160）就是用这些条件检查是否可以用正态近似。fileciteturn2file4  

---

## 5. Sampling Distribution of Sample Mean 样本均值的抽样分布

设总体均值 μ，总体标准差 σ，样本量 n，样本均值为 x-bar：fileciteturn2file4  

- E(x-bar) = μ；  
- SD(x-bar) = σ / sqrt(n)。  

核心问题：x-bar 的分布形状是什么？这就引出：

### 5.1 Central Limit Theorem 中心极限定理（CLT）

PPT 通过模拟掷骰子的平均值，展示随着 n 增大，样本均值的直方图越来越接近正态分布：fileciteturn2file4  

- 抽样 2 个骰子求平均 → 略有钟形；  
- 抽样 5 个骰子求平均 → 更接近钟形；  
- 抽样 20 个骰子求平均 → 非常接近正态曲线。  

**CLT 正式陈述（非严格）：**  
> 只要样本量 n 足够大，来自任意分布（有有限均值与方差）的样本，其样本均值的抽样分布会逼近正态分布。  

结论：  
- x-bar 近似 ~ Normal(mean = μ, sd = σ / sqrt(n))。  
- 总体越偏斜，所需 n 越大。  
- 实务中 n ≥ 30 常被视为“足够大”的粗略标准。fileciteturn2file4  

原子笔记：[[Concept-Central-Limit-Theorem|Central Limit Theorem]].

### 5.2 Sampling Distribution Conditions for Mean

PPT 条件：fileciteturn2file4  

1. Independence Assumption 独立性假设。  
2. Randomization Condition 随机抽样或随机分组。  
3. 10% Condition：对不放回抽样，n ≤ 0.1N。  
4. Large Enough Sample Condition：样本够大（特别是总体高度偏斜时要求更大）。  

---

## 6. 从抽样分布到置信区间（预告）

有了抽样分布模型之后，我们就能：  
- 知道 p-hat 或 x-bar “通常”会落在哪里；  
- 用“中心 ± 若干个标准误差”的形式构造区间，来估计总体参数。  

这就是下一周（Class 6）重点：  
- **One-Proportion z-Interval（单样本比例置信区间）**；  
- 以及误差界（Margin of Error）、样本量设计等。  

---

## 7. Week05 小结

本周关键：把“样本统计量也看作随机变量”，理解其分布。

1. 样本比例 p-hat 的抽样分布：中心在 p，标准差 sqrt(p(1−p)/n)，在条件满足时近似正态。  
2. 样本均值 x-bar 的抽样分布：中心在 μ，标准差 σ/sqrt(n)，由 CLT 给出正态近似。  
3. 抽样误差是自然波动，不是“错误”，但它决定了我们估计总体时的“精度极限”。  

**下一步（Week06）**：在这些抽样分布的基础上，构建正式的置信区间（confidence intervals）并讨论如何解读和设计样本量。  
