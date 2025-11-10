# Week03 – Randomness, Probability & Discrete Random Variables  
# 第三周：随机性、概率与离散随机变量

> 对应 PPT：Class 3 – Randomness and Probability; Random Variables and Probability Models。fileciteturn2file2

---

## 1. Uncertainty & Managerial Decisions 不确定性与管理决策

管理者经常要在不确定的环境下决策，例如：fileciteturn2file2  
- 如果涨价，销售量下降的概率有多大？  
- 新的装配方法提高生产率的可能性多大？  
- 新投资项目获利的几率有多大？  

概率（probability）就是形式化地刻画这些“不确定性”的工具。

原子笔记：[[Concept-Probability-Basics|Probability Basics 概率基础]]。

---

## 2. Events, Probability & Odds 事件、概率与赔率

### 2.1 事件和样本空间

- **Sample space S 样本空间**：所有可能结果的集合。  
- **Event 事件**：样本空间中的一个子集。  

性质：fileciteturn2file2  
1. 任意事件 E 的概率满足 0 ≤ P(E) ≤ 1。  
2. 一组互斥且完备的事件，其概率和为 1。  

### 2.2 Mutually Exclusive & Exhaustive 互斥与完备

- **Mutually exclusive / disjoint 互斥**：两个事件不能同时发生。  
- **Exhaustive 完备**：这些事件覆盖了所有可能结果。  

### 2.3 Odds – 赔率

- 给定 P(E)，则赔率（odds for E）= P(E) / [1 − P(E)]。  
- 若给出“a to b 的赔率”，则对应概率 P(E) = a / (a + b)。fileciteturn2file2  

详细见：[[Concept-Events-and-Odds|Events & Odds 事件与赔率]]。

---

## 3. Probability Rules 概率基本规则

### 3.1 Rule 1 – Probability Assignment Rule

- 对整个样本空间 S，有 P(S) = 1。fileciteturn2file2  

### 3.2 Rule 2 – Complement Rule 补事件

- 事件 A 的补集记作 A^c，即“不发生 A 的事件”。  
- 有：P(A^c) = 1 − P(A)。fileciteturn2file2  

Venn 图见 PPT。

### 3.3 Rule 3 – Multiplication Rule 乘法规则（独立）

- 若 A 与 B 独立，则：  
  - P(A ∩ B) = P(A) × P(B)。fileciteturn2file2  

FTSE100 与 S&P500 例子：  
- 如果假设二者独立，则 P(两者都涨) = P(A)P(B)，但 PPT 给出真实 P(A ∩ B) = 0.30，与 0.55 × 0.35 不同，说明实际上 **不独立**。fileciteturn2file2  

### 3.4 Rule 4 – General Addition Rule 加法公式

- 一般情况：  
  - P(A ∪ B) = P(A) + P(B) − P(A ∩ B)。fileciteturn2file2  
- 若 A 与 B 互斥（disjoint），则 P(A ∩ B)=0，简化成 P(A) + P(B)。  

FTSE100 & S&P500 例子：  
- P(A) = 0.55, P(B) = 0.35, P(A ∩ B) = 0.30 →  
  - P(A ∪ B) = 0.55 + 0.35 − 0.30 = 0.60。fileciteturn2file2  

详细见：[[Concept-Addition-and-Multiplication-Rules|Addition & Multiplication Rules]].

---

## 4. Conditional Probability & Independence 条件概率与独立性

### 4.1 Conditional Probability 条件概率

- 定义：P(B | A) = P(A ∩ B) / P(A)。fileciteturn2file2  
  - “在事件 A 已经发生的条件下，事件 B 发生的概率”。  

### 4.2 General Multiplication Rule 一般乘法公式

- P(A ∩ B) = P(A) × P(B | A)。fileciteturn2file2  

### 4.3 Independence 独立性

- 若 P(B | A) = P(B)，则 A 与 B 独立。  
- 直观：知道 A 发生与否，不改变 B 的发生概率。  
- 重要警告：**互斥 ≠ 独立**；互斥事件往往不独立。fileciteturn2file2  

原子笔记：[[Concept-Conditional-Probability|Conditional Probability]]，[[Concept-Independent-vs-Disjoint|Independent vs Disjoint]].

---

## 5. Contingency Tables & Conditional Distributions 列联表与条件分布

PPT 举了一个“Pick Your Prize Promotion” 的例子：性别 × 奖品偏好。fileciteturn2file2  

- **Marginal probability** 边缘概率：只看行/列总和的概率。  
  - 如 P(woman) = 251/478 ≈ 0.525。  
- **Joint probability** 联合概率：两个事件同时发生的概率。  
  - 如 P(woman and camera) = 91/478 ≈ 0.190。  
- **Conditional distribution** 条件分布：给定一行或一列的情况下的分布。  
  - 如 P(bike | woman) = 30/251 ≈ 0.120。  

这些在后面做 Bayes、Logit、分类问题时都非常常见。

---

## 6. Bayes’ Rule 贝叶斯公式 & 全概率公式

PPT 通过 EPS exceed/meet/fall short 与 Firm expands 的例子说明：fileciteturn2file2  

- 给定三个互斥完备事件 A1, A2, A3（如 EPS 三种情况），以及一个新信息 B（公司扩张）。  
- 已知先验 P(Ai) 和条件概率 P(B | Ai)（likelihood），需要更新后验 P(Ai | B）。  

涉及：  
- **Total Probability Rule 全概率公式**：  
  - P(B) = Σ P(B | Ai) P(Ai)。  
- **Bayes’ Rule 贝叶斯公式**：  
  - P(Aj | B) = [P(B | Aj) P(Aj)] / Σ P(B | Ai) P(Ai)。  

原子笔记：[[Concept-Bayes-Theorem|Bayes Theorem 贝叶斯定理]].

---

## 7. Random Variables 随机变量

PPT 定义：fileciteturn2file2  

- **Random variable 随机变量**：其取值由随机试验结果决定的数值变量。  
- 若可能取值可以列出（有限或可数），则为 **Discrete random variable 离散随机变量**；  
- 若在某区间内可以取任意值，则为 **Continuous random variable 连续随机变量**。  

原子笔记：[[Concept-Random-Variable|Random Variable 随机变量]]，[[Concept-Discrete-vs-Continuous|Discrete vs Continuous]].

---

## 8. Discrete Probability Distributions 离散概率分布

### 8.1 Probability Function 概率函数

- 用 f(x) 描述离散随机变量 X 在每个可能取值 x 上的概率。fileciteturn2file2  
- 必须满足：
  - f(x) ≥ 0；  
  - Σ f(x) = 1。  

### 8.2 Discrete Uniform Distribution 离散均匀分布

- 例：掷一枚公平骰子，X 为点数。  
- P(X = 1) = … = P(X = 6) = 1/6。fileciteturn2file2  
- PMF 可以列为一个表，也可画条形图。  

原子笔记：[[Concept-Uniform-Distribution|Uniform Distribution 均匀分布]].

### 8.3 Example: TV Sales JSL Appliances

- X = 一天卖出的电视数，可取值 0,1,2,3,4。  
- 利用历史数据统计每种销量的频率 → 得到经验概率分布。fileciteturn2file2  

---

## 9. (预告) Special Discrete Models 特殊离散模型

在 PPT 后半和后续课程中会更加系统讨论：  

- [[Concept-Binomial-Distribution|Binomial Distribution 二项分布]]：
  - 固定 n、独立重复试验、每次两种结果（成功/失败）、成功概率恒定。  
- [[Concept-Poisson-Distribution|Poisson Distribution 泊松分布]]：
  - 单位时间/空间内事件发生次数，假设事件独立、平均发生率 λ 恒定。  

对应 Excel：[[Excel-BINOM.DIST|BINOM.DIST]]，[[Excel-POISSON.DIST|POISSON.DIST]]。

---

## 10. Week03 小结

本周从“统计描述”转向“概率与随机变量”，核心目标：

1. 理解事件、样本空间和概率的基本规则（补集、加法、乘法）。  
2. 能处理条件概率、独立性，以及用列联表计算各种概率。  
3. 理解离散随机变量和概率分布表，熟悉离散均匀分布。  
4. 初步接触贝叶斯公式的思想（如何用新信息更新信念）。  

这些内容将为后续：  
- 特殊分布（binomial, Poisson）；  
- 连续分布（uniform, normal）；  
- 抽样分布和推断（置信区间、检验）打基础。  
