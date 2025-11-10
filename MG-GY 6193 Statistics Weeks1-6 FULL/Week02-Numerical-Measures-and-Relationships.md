# Week02 – Numerical Measures & Relationships  
# 第二周：数值度量与变量关系（Descriptive Statistics: Numerical Measures）

> 对应 PPT：Class 2 – Descriptive Statistics: Numerical Measures。主要内容：分布形状、集中趋势、离散程度、百分位数、IQR、例题与 Excel 函数。fileciteturn2file1

---

## 1. Shape 复习：分布形状（回顾 + 补充）

描述一个分布时，要同时关注：形状 (shape)、中心 (center)、离散程度 (spread)。fileciteturn2file1  

### 1.1 Modes – 峰数 / 模式

- 直方图中一个“峰”（peak / hump）叫做一个 **mode（模态）**。  
- 分类：
  - **Unimodal 单峰**：一个主要峰。  
  - **Bimodal 双峰**：两个峰，可能代表两个子群体。  
  - **Multimodal 多峰**：多个峰。  
  - **Uniform 均匀**：柱高差不多，没有明显峰。  

### 1.2 Symmetry & Skewness – 对称与偏态

- 对称（symmetric）：中心左右两侧大致镜像。  
- 尾部（tails）：两端较薄的部分。  
- 如果一个尾巴拉得更长，则称为 skewed：  
  - 长尾向右 → **right-skewed / positively skewed 右偏**；  
  - 长尾向左 → **left-skewed / negatively skewed 左偏**。  

### 1.3 Outliers – 离群值

- 远离主体分布的一小部分点。fileciteturn2file1  
- 影响：
  - 可能显著影响均值、标准差、相关系数、回归等。  
  - 也可能是数据录入错误。  
- 必须在结论中单独讨论。详见：[[Concept-Outlier|Outlier 离群值]]。

---

## 2. Measures of Center 集中趋势度量（均值、中位数、众数等）

### 2.1 Mean – 均值

- **Sample mean 样本均值**：  
  - 定义：所有观测值求和除以观测个数。  
  - 直观：分布的“平衡点”（balancing point）。fileciteturn2file1  
- PPT 示例：18 个学生的体重，求平均体重。  
- 均值对**极端值非常敏感**。

Excel：[[Excel-AVERAGE|AVERAGE(range)]].  
原子笔记：[[Concept-Mean|Mean 均值]]。

### 2.2 Population Mean – 总体均值

- 记作 μ，定义类似，只是把 n 换成 N（总体大小）。fileciteturn2file1  

### 2.3 Median – 中位数

- 将数据按升序排序：
  - 若 n 为奇数：中位数是中间位置的那个值。  
  - 若 n 为偶数：中位数是中间两个值的平均。fileciteturn2file1  
- 对离群值不敏感，被称为 **resistant 抗干扰**。  
- 对于偏态分布，更适合用中位数描述“典型值”。  

Excel：[[Excel-MEDIAN|MEDIAN(range)]].  
原子笔记：[[Concept-Median|Median 中位数]]。

### 2.4 Mode – 众数

- 数据集中出现频率最高的值。  
- 可能：无众数 / 单众数 / 双众数 / 多众数。fileciteturn2file1  

Excel：[[Excel-MODE.SNGL|MODE.SNGL(range)]].  
原子笔记：[[Concept-Mode|Mode 众数]]。

### 2.5 Trimmed Mean – 截尾均值

- 当数据中有极端值，可以去掉两端若干比例后再求平均。  
- 例如：5% trimmed mean → 删除最小 5% 与最大 5% 的数据，然后对剩余数据求均值。fileciteturn2file1  
- 用于“折中”：保留大部分信息，又减弱极端值影响。  

原子笔记：[[Concept-Trimmed-Mean|Trimmed Mean 截尾均值]]。

### 2.6 Weighted Mean – 加权平均

- 有些场景不同观测的“重要程度”不同，需要加权。  
- 例：GPA → 每门课的成绩按学分加权。  
- PPT 示范：Construction Wages（不同工种不同时薪和工作小时数）。fileciteturn2file1  
  - 加权平均 = Σ(工资 × 小时) / Σ小时。  

原子笔记：[[Concept-Weighted-Mean|Weighted Mean 加权平均]].

### 2.7 Geometric Mean – 几何平均数

- 用于分析**多个时期收益率 / 增长率**时更合适。fileciteturn2file1  
- 比如 5 年投资收益率分别是 r1,…,r5，对应的增长因子为 (1+r1)…(1+r5)，几何平均增长率 = (增长因子乘积) 的 1/5 次方再减 1。  
- PPT 例子：一只股票 5 年的年度收益率。  

Excel：[[Excel-GEOMEAN|GEOMEAN(range)]].  
原子笔记：[[Concept-Geometric-Mean|Geometric Mean 几何平均数]].

---

## 3. Percentiles & Quartiles 百分位数与四分位数

### 3.1 Percentiles – 百分位数

PPT 定义：fileciteturn2file1  

- 第 p 百分位（p-th percentile）：
  - 至少 p% 的数据“小于或等于”该值；
  - 至少 (100 − p)% 的数据“大于或等于”该值。  
- 常用在：标准化考试（SAT、GRE）、收入分布等。  

手工计算的一般步骤：  
1. 把数据按升序排列。  
2. 计算位置 Lp = (p/100) × (n + 1)。  
3. 若 Lp 为整数，取该位置值；若是小数，插值。  
- PPT Apartment Rents 例子：70 个租金数据，求第 80 百分位。fileciteturn2file1  

### 3.2 Quartiles – 四分位数

- 特殊的百分位数：  
  - Q1 = 25th percentile  
  - Q2 = 50th percentile = median  
  - Q3 = 75th percentile  
- IQR（Interquartile Range 四分位距）= Q3 − Q1，代表中间 50% 数据的范围。fileciteturn2file1  

### 3.3 Excel 计算

- Percentile：[[Excel-PERCENTILE.EXC|PERCENTILE.EXC(array, k)]]  
- Quartile：[[Excel-QUARTILE.EXC|QUARTILE.EXC(array, quart)]]  
  - quart=1,2,3 对应 Q1, median, Q3。  

原子笔记：[[Concept-Percentiles-and-Quartiles|Percentiles & Quartiles 百分位与四分位数]].

---

## 4. Spread of the Distribution 离散程度（Range, IQR, Variance, SD）

### 4.1 Range – 极差

- 定义：max − min。  
- 优点：简单、直观。  
- 缺点：只看两个最极端的点，对离群值极其敏感。  

原子笔记：[[Concept-Range|Range 极差]].

### 4.2 Interquartile Range – IQR 四分位距

- IQR = Q3 − Q1，表示中间 50% 数据的跨度。fileciteturn2file1  
- 更“稳健”（robust），不受极端值影响太多。  
- 也是判断离群值（1.5 IQR 规则）的基础。  
- PPT 例子：小数据 {3,5,1,8,9,8,2}，求 mean、median、range、IQR。fileciteturn2file1  

原子笔记：[[Concept-Boxplot|Boxplot 箱线图]] 中也会用到 IQR。

### 4.3 Variance & Standard Deviation – 方差与标准差

PPT：用“每个数据与均值的偏差”来构造一个统一的离散度量。fileciteturn2file1  

- Step 1：对每个观测算 deviation = x − mean。  
- Step 2：平方 deviation，避免正负抵消。  
- Step 3：求这些平方的平均（总体用 N、样本用 n−1 分母）。  
- Step 4：对样本方差开根号得到 SD。  

直观：  
- 标准差越大 → 数据越“分散”；  
- 越小 → 越“集中”。  

Excel：[[Excel-STDEV.S|STDEV.S]]，[[Excel-VAR.S|VAR.S]]。  
原子笔记：[[Concept-Variance|Variance 方差]]，[[Concept-Standard-Deviation|Standard Deviation 标准差]].

---

## 5. Example：七个数据的小练习（PPT 示例）

数据：{3, 5, 1, 8, 9, 8, 2}。fileciteturn2file1  
- **Mean**：全部加总再除以 7。  
- **Median**：排序后 {1,2,3,5,8,8,9}，中位数=5。  
- **Range**：9−1=8。  
- **IQR**：
  1. 按 median 分成两半：{1,2,3,5} 和 {5,8,8,9}；  
  2. 各自求中位数，得到 Q1 ≈ 2.5，Q3 ≈ 8；  
  3. IQR = 8 − 2.5 = 5.5。  

建议你在 Excel 上也亲手做一遍，并用函数 [[Excel-AVERAGE]]、[[Excel-MEDIAN]]、[[Excel-STDEV.S]]、[[Excel-QUARTILE.EXC]] 进行验证。

---

## 6. Excel Functions 回顾

PPT 中给出的函数：fileciteturn2file1  

- Mean：`=AVERAGE(data_range)`  
- Median：`=MEDIAN(data_range)`  
- Mode：`=MODE.SNGL(data_range)`  
- Geometric Mean：`=GEOMEAN(data_range)`  
- Percentile：`=PERCENTILE.EXC(array, k)`  
- Quartile：`=QUARTILE.EXC(array, quart)`  
- Sample SD：`=STDEV.S(data_range)`  

见总览：[[Excel-Overview|Excel 统计函数总览]].

---

## 7. Week02 小结 & 学习建议

这一周的目标：给“形状”配上“数字版摘要”：

1. 用中心度量总结“数据大概在哪儿”：mean, median, mode 等。  
2. 用离散度量总结“数据散得厉不厉害”：range, IQR, variance, SD。  
3. 理解百分位数和四分位数的含义，以及与箱线图的联系。  
4. 会用 Excel 快速算这些量。  

**下一步（Week03）**：在有了“数据长什么样”的基础上，引入 **不确定性 / 概率 / 随机变量**，开始搭建“概率模型”，为后面的分布、抽样分布和推断做准备。  
