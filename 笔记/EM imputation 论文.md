---
title: "EM imputation 论文"

---

#Research

# Tell It by Myself...

该论文首先描述了发布的横向预测器中缺失值的规模和起源，然后解释了为什么在进行大规模机器学习研究时需要进行插补。文章中提到了一种名为期望最大化（Expectation-Maximization，EM）的插补方法。简单来说，这种方法是通过观察到的值来预测缺失值。如果缺失值与观察到的值之间没有相关性，那么它们的关系斜率就是零。在这种极端情况下，使用横向平均值进行插补与使用最小二乘法（OLS）没有区别，甚至可能更有效。

然而，如果数据中存在缺失值，那么如何计算协方差就成了一个非常棘手的问题，因为不清楚在数据的任意子集中缺失的情况下应该如何计算协方差。EM方法和相关的形式主义就是为了处理这个问题。

我认为这篇文章的方法对于我们的研究可能非常有用，特别是在处理包含大量缺失数据的问题时。EM算法提供了一种有效的解决方案，可以帮助我们更好地理解和处理这些问题。

然而，我也注意到这种方法需要对数据的分布做出一些假设，这可能在某些情况下限制了它的应用。此外，虽然EM算法在处理缺失数据方面表现出色，但它并不适用于所有类型的问题。例如，对于一些复杂的模型或者数据不满足常见分布假设的情况，我们可能需要考虑使用其他方法，如广义矩方法（GMM）。

总的来说，我认为这篇文章提供了一种有价值的工具，可以帮助我们处理缺失数据问题。我期待进一步探讨这个主题，并在我们的研究中应用这些方法。

---

公式（5）在论文中并未明确给出，但从上下文中我们可以推断，这可能是指公式（7）和公式（8）。

公式（7）是一个回归方程，用于预测缺失值：

ˆxmiss_i, j, t = ˆβ′_ni, j, txobs_i, t

这里，ˆxmiss_i, j, t 是向量 xmiss_i, t 的一个组成部分，而 ˆβ′_ni, j, t 是插补斜率向量。

公式（8）给出了如何计算插补斜率向量：

ˆβ′_ni, j, t = ˆΣj, obs|i, t ˆΣ−1_obs|i, obs|i, t

这里，ˆΣobs|i, obs|i, t 是 ˆΣt 的子矩阵，对应于股票 i 的观察预测器，而 ˆΣj, obs|i, t 是 ˆΣt 的子向量，对应于预测器 j 与观察预测器之间的协方差。

这两个公式的核心思想是，我们的插补预测缺失值（公式（7）的左侧）基于它们与观察值的协方差（公式（8）的右侧），就像在最小二乘法（OLS）中一样。如果没有缺失数据，公式（8）将只是将预测器 j 对所有其他预测器进行回归的斜率。然而，缺失数据对于 OLS 来说是一个非常棘手的问题，因为在数据的任意子集中存在缺失时，如何计算协方差并不明确。EM 算法和相关的形式主义就是为了处理这个问题。

# Reference 

相关链接：[EM 算法经典论文](EM%20算法经典论文)
