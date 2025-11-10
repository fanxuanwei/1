# Week04 – Continuous Distributions & The Normal Distribution  
# 第四周：连续分布与正态分布

> 对应 PPT：Class 4 – The Normal and other Continuous Distributions。fileciteturn2file3

---

## 1. Continuous Random Variables & pdf 连续随机变量与密度函数

- 连续随机变量 X：可以在某个区间（或多个区间）上取任意实数值。fileciteturn2file3  
- 不再讨论“X 等于某个点”的概率（通常为 0），而是讨论“X 落在某个区间内”的概率。

关键概念：**概率密度函数 pdf f(x)**  
- f(x) ≥ 0；  
- 整个实数轴下的面积 = 1；  
- P(x1 < X < x2) = 曲线 f(x) 在 [x1, x2] 之间下方的面积。  

---

## 2. Continuous Uniform Distribution 连续均匀分布

PPT 定义：fileciteturn2file3  

- X 在区间 [a, b] 上均匀分布：
  - 在 [a, b] 内每个同长度区间的概率相同。  
  - pdf: f(x) = 1/(b−a) for a < x < b；其他地方为 0。  
- 期望：E(X) = (a + b)/2。  
- 方差：Var(X) = (b − a)² / 12。  

PPT 例 1：第三季度销售预测  
- 销售额在 17 到 19 million 之间均匀分布。  
- f(x) = 0.5 for 17 ≤ x ≤ 19；否则 0。  

PPT 例 2：Slater’s Buffet 沙拉自助称重  
- X = 沙拉盘重量（oz），在 [5, 15] 均匀分布。  
- f(x) = 1/10 for 5 < x < 15。  
- 问 P(12 < x < 15) = 区间长度 3 × 高度 1/10 = 0.3。fileciteturn2file3  

原子笔记：[[Concept-Uniform-Distribution|Uniform Distribution 均匀分布]].

---

## 3. Normal Distribution 正态分布

### 3.1 模型定义

- 若 X 服从正态分布，记作 X ~ N(μ, σ²)。fileciteturn2file3  
- pdf 是经典的“钟形曲线”：  
  - 对称、单峰、左右渐近于 0；  
  - 均值 μ 控制中心；  
  - 标准差 σ 控制“胖瘦”。  

### 3.2 经验规则（68–95–99.7 Rule）

对于 N(μ, σ²)：fileciteturn2file3  
- 约 68% 数据落在 μ ± 1σ。  
- 约 95% 数据落在 μ ± 2σ。  
- 约 99.7% 数据落在 μ ± 3σ。  

这是一个非常重要的“快速判断”工具。

### 3.3 标准正态与 z-score

- 将任意 N(μ, σ²) 的 X 标准化：  
  - Z = (X − μ) / σ。  
- Z 服从标准正态 N(0, 1)。  
- 使用 Z 分数的好处：可以统一用一张标准正态表或一个函数求概率。  

PPT 中给出的 Excel 函数：fileciteturn2file3  
- `=NORM.S.DIST(z, TRUE)` → P(Z ≤ z)。  
- `=NORM.S.INV(p)` → 给定 P(Z ≤ z) = p，求 z。  

原子笔记：[[Concept-Normal-Distribution|Normal Distribution 正态分布]]，[[Concept-Standard-Normal-and-Z|Standard Normal & Z-score]].

---

## 4. Using the Normal Model 例题：资产收益率 & GMAT

### 4.1 Asset Returns Example 资产收益率例子

- 假设某资产年收益率服从 N(4%, 10%²)。fileciteturn2file3  
- 问：某一年收益率小于 5.6% 的概率？  
  - 标准化：z = (5.6 − 4) / 10 = 0.16。  
  - 用标准正态表或 Excel 求 P(Z < 0.16) ≈ 0.5636。  

- 问：收益率在 8.2% 和 9.6% 之间的概率？  
  - 对两个端点分别标准化：  
    - z1 = (8.2 − 4) / 10 = 0.42  
    - z2 = (9.6 − 4) / 10 = 0.56  
  - 概率 = P(0.42 < Z < 0.56) = Φ(0.56) − Φ(0.42) ≈ 0.0495。fileciteturn2file3  

### 4.2 GMAT Scores Example

- 假设 GMAT 成绩近似服从 N(500, 100²)。fileciteturn2file3  
- 问：成绩在 450 与 600 之间的比例？  
  - 标准化： z(600) = 1.0, z(450) = −0.5。  
  - 概率 = Φ(1.0) − Φ(−0.5)。  
- 问：前 10% 门槛是多少分？  
  - 找 z，使得 P(Z ≤ z) = 0.90（或 P(Z ≥ z) = 0.10）。  
  - 用标准正态表或 `NORM.S.INV(0.90)` 得出 z，再转回 X。  

---

## 5. Excel 帮助：标准正态概率

PPT 给出一个 Excel 计算标准正态概率的示例表：fileciteturn2file3  

- 示例：
  - `=NORM.S.DIST(1, TRUE)` → P(Z < 1) = 0.8413。  
  - `=1 - NORM.S.DIST(1.58, TRUE)` → P(Z > 1.58) = 0.0571。  
- 你可以在自己的 Excel 里重建 PPT 中的表格，一边算一边熟悉。  

---

## 6. Week04 小结

这一周目的是：

1. 从“点概率”过渡到“曲线下面积”，理解连续型概率分布。  
2. 掌握一个最简单的连续分布：uniform，并能用面积计算区间概率。  
3. 熟悉正态分布的性质、z-score、经验规则和 Excel 计算方法。  
4. 能够把具体金融/考试场景建模成正态，并计算区间概率和分位数。  

**下一步（Week05）**：在此基础上，讨论**样本统计量**（样本比例、样本均值）的分布（sampling distributions），引出中心极限定理。  
