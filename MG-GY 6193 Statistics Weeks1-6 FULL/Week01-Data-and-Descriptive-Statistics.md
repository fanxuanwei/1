# Week01 – Data & Descriptive Statistics  
# 第一周：数据和描述性统计（Chapter 1 & 2）

> 对应 PPT：1st Class NYU – 主要是统计学简介、数据类型、测量尺度、分类和数值数据的展示。

---

## 1. What is Statistics? 什么是统计学？

**Statistics（统计学）**有两个含义：  

1. 作为 **数值事实（numerical facts）**：  
   - 用来描述商业、经济、金融等现象的数字，例如：
     - 平均数（mean）
     - 中位数（median）
     - 百分比（percent）
     - 指数（index numbers）  
   - 用这些数字，我们可以快速把握一个现象的大致情况。

2. 作为 **方法论（art and science）**：  
   - 指一整套关于**数据的收集、分析、展示和解释**的工具和思维方式：  
     - 如何设计调查或实验收集数据（collecting）  
     - 如何用数值和图形总结数据（analyzing & presenting）  
     - 如何从样本数据推断总体（interpreting）

典型应用场景：  
- **Accounting 会计**：审计时用统计抽样检查账目。  
- **Economics 经济学**：用失业率、GDP 增长率等统计数据进行宏观预测。  
- **Finance 金融**：用收益率、波动率、PE 等指标分析资产。  
- **Production 生产**：用控制图（control charts）做质量控制。  
- **Marketing 市场营销**：POS 扫描器记录销售数据，用于顾客行为分析。  
- **Information Systems 信息系统**：统计网络访问量、响应时间等，评估系统性能。  

---

## 2. Data, Element, Variable, Observation 数据、元素、变量和观测

PPT 定义：  

- **Data（数据）**：
  - 为分析和解释而收集的事实与数字。  
  - 可以是数值、文本、类别标签等。

- **Data set（数据集）**：  
  - 某次研究或项目中所有数据的集合。  

- **Element / Entity（元素 / 实体）**：
  - 数据收集的对象，如一个公司、一位学生、一只股票、一份合同。

- **Variable（变量）**：
  - 对每个元素感兴趣的特征或属性，如：  
    - 股票年收益率（Annual Return）  
    - 员工工资（Salary）  
    - 是否违约（Default? Y/N）

- **Observation（观测）**：  
  - 某个元素的所有变量取值，通常对应数据表中的“一行”。  

- 一个数据集的 **总数据值数量 = 元素数 × 变量数**。  
- 若数据集包含 n 个元素，就有 n 条观测（n observations）。

更系统的原子笔记见：[[Concept-Data-Element-Variable-Observation|Element / Variable / Observation]]。

---

## 3. Scales of Measurement 测量尺度

测量尺度决定：  
- 数据里到底包含了多少信息？  
- 能不能比较大小？能不能做加法？能不能说“两倍”？  
- 哪些统计方法是合法的？  

PPT 里四种尺度：[[Concept-Scales-of-Measurement|详细笔记]]

### 3.1 Nominal Scale 名义尺度

- 数据只是 **标签 / 名字**，只能用来区分不同类别，不能排序。  
- 可以用文字或数字编码，但数字**没有数量意义**。  
- 例子：  
  - 学生所属学院：Business, Humanities, Engineering, …  
  - 编码成：1=Business, 2=Humanities, 3=Engineering …  
- 只能做：计数、比例、众数等。

### 3.2 Ordinal Scale 顺序尺度

- 既有“标签”，又有**顺序**，但“差多少”不确定。  
- 例子：
  - 年级：Freshman, Sophomore, Junior, Senior  
  - 满意度：Very Satisfied, Satisfied, Neutral, Dissatisfied  
- 可以比较“高一点 / 低一点”，但不能说“高 2 倍”。

### 3.3 Interval Scale 区间尺度

- 一定是数值型。  
- 具有：
  - 顺序 meaningful order  
  - 差值 meaningful differences （差多少有意义）  
- **0 不代表“完全没有”**，仅是刻度上的一个点。  
- 例子：  
  - SAT 分数  
  - 摄氏 / 华氏温度（0°C 不代表没有温度）

### 3.4 Ratio Scale 比率尺度

- 拥有 interval 的所有性质，**再加一个：有绝对零点**。  
- 可以说“是它的 2 倍”等比率关系有意义。  
- 例子：
  - 距离、重量、时间、金额、学分数。  
  - 0 重量 = 没有重量。  
  - Kevin 72 学分，Melissa 36 学分 → Kevin 是 Melissa 的两倍。  

---

## 4. Types of Data 数据类型

根据变量性质分为两大类：[[Concept-Categorical-vs-Quantitative|详细原子笔记]]

### 4.1 Categorical / Qualitative Data 分类（质性）数据

- 用标签 / 名字标记类别：如性别、血型、是否购买。  
- 常用 **Nominal / Ordinal** 尺度。  
- 可以是文字，也可以是数字编码，但数字不代表“多少”。  
- 可做：
  - 频数表（frequency table）  
  - 条形图（bar chart）  
  - 饼图（pie chart）  
  - 列联表（contingency table）等。

### 4.2 Quantitative Data 数值（定量）数据

- 表示“多少”(how many / how much)。  
- 必须是 **数值型**，可以加减乘除。  
- 常分为：
  - **离散 discrete**：计数，例如：顾客数、缺陷件数、订单数。  
  - **连续 continuous**：测量，例如：身高、体重、时间、价格。  

---

## 5. Cross‑sectional vs Time Series 横截面 vs 时间序列

PPT 定义：[[Concept-Cross-sectional-vs-Time-Series|Cross-sectional vs Time Series]]

- **Cross-sectional data 横截面数据**：  
  - 在同一时间点，对很多个体同时观察。  
  - 例：2023 年 11 月，各县发放的建筑许可数。

- **Time series data 时间序列数据**：  
  - 对同一变量，在很多时间点上连续观察。  
  - 例：某县过去 36 个月每月发放的建筑许可数。  

时间序列图常用于：  
- 看趋势（Trend）  
- 看周期 / 季节性（Cycle / Seasonality）  
- 预测未来（Forecasting）  

---

## 6. Data Sources & Study Types 数据来源与研究类型

### 6.1 Data Sources 数据来源

PPT 分类：fileciteturn2file0

- **Internal company records 内部公司记录**  
  - 员工记录、生产记录、库存记录、销售记录、信用数据、客户档案等。  
- **Business database services 商业数据库**  
  - 例如：Dow Jones & Co.，Bloomberg 等。  
- **Government agencies 政府机构**  
  - Census Bureau、Federal Reserve、BLS…。  
- **Industry associations 行业协会**  
- **Special-interest organizations 专业机构**  
- **Internet 互联网**：越来越重要的数据来源。  

### 6.2 Statistical Studies 统计研究类型

- **Observational Study 观察性研究**：
  - 不干预、不控制，只观察记录。  
  - 例：吸烟者 vs 不吸烟者的健康结果比较。  
  - 研究者不能决定谁吸烟，所以难以得出严格“因果关系”。  

- **Experimental Study 实验性研究**：
  - 研究者控制处理（treatment），比较不同组结果。  
  - 例：1954 年 Salk 小儿麻痹疫苗实验：随机分配接种 / 安慰剂，比较发病率。  

---

## 7. Summarizing Categorical Data 分类变量的汇总

### 7.1 Frequency Tables 频数表

- 记录每个类别的：
  - 频数（frequency）  
  - 相对频数（relative frequency） = 频数 / 总数  
  - 百分比（percent frequency） = relative frequency × 100%  

例：Super Bowl 观众调查 ——“更期待比赛还是广告？”  
- 用频数表显示 40 个受访者对“game / commercials / both / neither”等选项的计数与百分比。fileciteturn2file0

### 7.2 Bar Charts 条形图

- 水平轴：类别；垂直轴：频数或百分比。  
- 每个类别一个柱子，**柱子之间有间隙**，强调类别是离散的。  
- 若用百分比，称为 **relative frequency bar chart**。  

### 7.3 Pie Charts 饼图

- 把 360° 的圆按各类别比例切成扇形。  
- 例：Google 搜索占 57%，对应 0.57 × 360 ≈ 205°。fileciteturn2file0  
- 更适合展示整体构成。

**使用条形图/饼图之前，要满足“Categorical Data Condition”：**  
- 数据是每个类别的计数或比例；  
- 各类别互不重叠、且覆盖所有可能。  

详见：[[Concept-Contingency-Table|Contingency Table 列联表与分类数据图表]]。

---

## 8. Summarizing Quantitative Data 数值变量的汇总

### 8.1 Histograms 直方图

- 用于展示定量数据的分布。PPT 中步骤：fileciteturn2file0  
  1. 决定组数（classes/bins），一般 5–20 个。  
  2. 决定组宽（class width）。  
  3. 决定每个组的上下限。  
- 每个组对应一个柱子，宽度等于组宽，高度为该组频数或相对频数。  
- 直方图不留空隙（连续变量）。  
- 用于观察：集中区间、偏态、峰数、离群值等。  

详见：[[Concept-Histogram|Histogram 直方图]].

### 8.2 Relative / Percent Frequency Distributions 相对频率与百分比分布

- **Relative frequency** = 某组频数 / 总样本量。  
- **Percent frequency** = relative frequency × 100%。  
- 直方图 y 轴可画频数，也可画相对频率或百分比。  

### 8.3 Stem-and-Leaf Displays 茎叶图

- 展示定量数据形状，同时保留每个观测值。  
- 将数值拆为“茎”（高位）+ “叶”（低位）：  
  - 如 8.6, 8.8, 9.1 → 茎=8,9；叶=6,8,1。  
- 适合样本量中等的情况。  

详见：[[Concept-Stem-and-Leaf|Stem-and-Leaf 茎叶图]].

---

## 9. Distribution Shape & Outliers 分布形状与离群值

PPT 强调描述一个分布时，要看：fileciteturn2file1  

1. **Shape（形状）**
   - Modes：有几个峰（unimodal / bimodal / multimodal / uniform）。  
   - Symmetry：是否对称。  
   - Skewness：尾巴是否向左 / 向右（左偏 / 右偏）。  

2. **Center（中心）**
   - 可以用均值、 中位数描述（第二周详细）。  

3. **Spread（离散程度）**
   - 用极差、方差、标准差、IQR 等（第二周详细）。  

4. **Outliers（离群值）**
   - 离群值是远离主体的一些点。  
   - 可能是：
     - 真实异常现象（很重要的信息）；
     - 录入错误。  
   - 会影响几乎所有统计方法，必须单独检查和解释。  

详见：[[Concept-Shape-of-Distribution|Shape of Distribution]] 和 [[Concept-Outlier|Outlier 离群值]].

---

## 10. Two Categorical Variables: Contingency Tables 两个分类变量：列联表

- 用 **contingency table / crosstab（列联表）** 展示两个分类变量的联合频数：  
  - 每行：一个变量的类别；  
  - 每列：另一个变量的类别；  
  - 格子里：joint count 联合频数。  
- 可以计算：
  - joint distribution（联合分布）；  
  - conditional distribution（条件分布，如“给定性别下，对广告兴趣的分布”）。  
- 用来判断变量是否“有关联”（associated）：  
  - 如果一个变量在另一个变量不同类别下的分布明显不同 → 有关联；  
  - 如果差不多 → 可认为独立（independent）。  

详见：[[Concept-Contingency-Table|Contingency Table 列联表]].

---

## 11. Two Quantitative Variables: Scatterplots 两个数值变量：散点图

- 每个观测是一对 (x, y)，在平面上画一个点。  
- 观察：
  - **Direction 方向**：整体从左下到右上（正相关）；从左上到右下（负相关）。  
  - **Form 形态**：线性 / 曲线型。  
  - **Strength 强度**：点云是否紧贴一条线。  
  - **Outliers / unusual points**：远离主趋势的点。  

这是后面**相关与回归**的基础图形。详见：[[Concept-Scatterplot|Scatterplot 散点图]].

---

## 12. Week01 小结 & 复习建议

本周核心：先搭好“数据与描述”的框架：

1. 搞清楚：我们在和什么样的数据打交道？  
   - 元素、变量、观测、数据集；  
   - 测量尺度 4 种；  
   - 定性 vs 定量。  

2. 熟悉基本图形：  
   - 分类：频数表、条形图、饼图、列联表；  
   - 数值：直方图、茎叶图、简单时间序列图、散点图。  

3. 初步感受“shape / center / spread / outliers”四个维度。  

后续几周会在这些基础上，加入：  
- 更精确的数值度量（mean, median, variance, sd, percentiles 等）；  
- 概率与随机变量；  
- 各种分布（均匀、二项、泊松、正态等）；  
- 抽样分布和中心极限定理；  
- 置信区间与假设检验。  
