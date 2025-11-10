# Week06 – Confidence Intervals for Proportions  
# 第六周：比例的置信区间（一元总体比例 z 区间）

> 对应 PPT：Class 6 – A Confidence Interval for a Proportion, Margin of Error, Choosing Sample Size。fileciteturn2file5

---

## 1. Motivation: What Can We Say About a Proportion? 我们到底能说什么？

例子：PPT 中调查美国成年人是否认为经济在变好：  
- 样本 3559 人，p-hat = 0.42（42%）。fileciteturn2file5  

我们希望说：“有 X% 的美国成年人认为经济在变好。”  
但：  
- 我们观察到的只是样本比例 p-hat，而不是总体比例 p；  
- 再抽一个样本，p-hat 会不同。  

所以：  
- 不能直接说 “p = 0.42”；  
- 也不严谨地说 “p 很可能就是 0.42”；  
- 更好的做法：给出一个区间，并说明“我们对这个区间有多大信心”。  

这就是 **置信区间（confidence interval）**。  
原子笔记：[[Concept-Confidence-Interval|Confidence Interval 置信区间]].

---

## 2. Sampling Distribution 回顾：p-hat 的近似正态

利用第 5 周的结论（p-hat 的抽样分布）：fileciteturn2file4  

- 若样本量 n 足够大且条件满足，则：  
  - p-hat 约 ~ Normal(mean = p, sd = sqrt(p(1−p)/n))。  
- 在实际构造区间时，我们用 p-hat 代替未知的 p，得到标准误差估计：  
  - SE(p-hat) = sqrt( p-hat (1 − p-hat) / n )。  

这让我们可以画出 p-hat 周围“± 若干个 SE”的区域，表示总体比例 p 很可能落在其中。

---

## 3. One-Proportion z-Interval 单样本比例 z 置信区间

假设：  
- 样本来自满足独立、随机、10% 条件的总体；  
- 成功-失败条件：np-hat ≥ 10 且 n(1−p-hat) ≥ 10。fileciteturn2file5  

则：  
1. 点估计：p-hat。  
2. 标准误差：SE(p-hat) = sqrt(p-hat(1 − p-hat)/n)。  
3. 对于给定置信度（如 95%），由标准正态得到 **临界值 z***：  
   - 90% → z* ≈ 1.645  
   - 95% → z* ≈ 1.96  
   - 99% → z* ≈ 2.576。fileciteturn2file5  
4. 置信区间：  
   - p-hat ± z* × SE(p-hat)。  

例：PPT 中的政治民调 PSI（Political Science, Inc.）：  
- 500 人中 220 人支持某候选人 → p-hat = 220/500 = 0.44。  
- 想要 95% 置信区间 → 使用 z* = 1.96，代入公式得到区间 [0.3965, 0.4835]。fileciteturn2file5  

---

## 4. Interpreting Confidence Intervals 如何正确解读置信区间

经典错误：  
- “p 有 95% 的概率落在这个区间里。” ❌  

正确解读：fileciteturn2file5  

> 我们对该区间 **有 95% 的信心**，认为总体比例 p 落在这个区间内。  
> 如果我们重复进行很多次同样的随机抽样，每次都构造一个 95% 置信区间，那么从长期来看，大约有 95% 的区间会覆盖真实的 p。  

PPT 用模拟 20 个样本的图说明：  
- 有一些区间会“miss”（不覆盖真实 p）；  
- 但大多数（约 95%）区间会“hit”。  

所以：**置信度是关于方法的长期成功率，不是一个具体区间中“p 在不在”的概率。**  

---

## 5. Margin of Error 误差界（ME）：置信度 vs 精度

置信区间可写成：  
- estimate ± ME（估计量 ± 误差界）。fileciteturn2file5  

这里：  
- ME = z* × SE(p-hat)。  

直观理解：  
- ME 越大，区间越宽 → 精度越低，但更“稳妥”。  
- 要提高置信度（从 90% → 95% → 99%），需要更大的 z*，因此 ME 变大、区间更宽。  

PPT Polling Question：  
- n = 100，p-hat = 0.50。  
- 标准误差 SE = sqrt(0.5 × 0.5 / 100) = 0.05。  
- 95% CI 的 z* ≈ 2 → ME ≈ 2 × 0.05 = 0.10。  
- 置信区间约为 (0.40, 0.60)。fileciteturn2file5  

原子笔记：[[Concept-Margin-of-Error|Margin of Error 误差界]].

---

## 6. Choosing Sample Size 如何为给定精度设计样本量

目标：  
> 在给定置信度（如 95%）下，使得置信区间的 ME 不超过目标值（比如 3%）。fileciteturn2file5  

对比例的情况：  
- 我们有：ME = z* × sqrt( p(1−p) / n )。  
- 给定 ME 和 z*，可以反解所需样本量 n。  
- 难点：真正的 p 未知。  

两个做法：  
1. 若有历史经验或试验样本，可用 p*（估计值）代替 p。  
2. 如果完全不知道 p，取 p = 0.5 作为最保守（因为 p(1−p) 在 0.5 时最大），得到最大所需样本量。  

PPT 中例子：某公司希望在 95% 置信度下，将 ME 控制在 3% 以内，需要的样本量大约为 1068。fileciteturn2file5  

另一个例子：PSI 想要 99% 置信度且 ME=0.03，有一个历史 p* = 0.44 → 计算得到所需样本约 1817。fileciteturn2file5  

---

## 7. Assumptions & Conditions 再次强调适用条件

在使用 One-Proportion z-Interval 前，务必检查：fileciteturn2file5  

1. **Independence Assumption 独立性假设**  
   - 抽样方式应保证个体之间近似独立。  
2. **Randomization Condition 随机化条件**  
   - 样本应来自简单随机抽样，或随机实验中的随机分组。  
3. **10% Condition**  
   - 若是不放回抽样，样本容量不超过总体的 10%。  
4. **Success/Failure Condition 成功-失败条件**  
   - 样本中成功数和失败数都至少约 10。  

这些条件本质上是为了保证：p-hat 的抽样分布近似正态，从而 z 区间是可行的。

---

## 8. Week06 小结 & 展望

这一周正式把“抽样分布”升级为“区间估计”：

1. 从单一估计值 p-hat → 区间 [L, U]，定量表达我们对总体比例 p 的不确定性。  
2. 学会写出、解释和使用 One-Proportion z-Interval：  
   - p-hat ± z* × SE。  
3. 理解误差界 ME 的含义以及与置信度、样本量的三方权衡。  
4. 能够根据目标精度设计样本量。  

**后续课程（Week7+）** 将把类似思想推广到：  
- 总体均值 μ 的置信区间（已知 σ / 未知 σ → z / t 区间）；  
- 以及进一步的假设检验（例如 “行为是否发生改变？” “新政策是否有效？”）。  
