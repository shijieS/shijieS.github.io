---
date: '2018-05-28 10:32 +0800'
published: false
layout: post
categories:
  - idear
tags:
  - tracking
comments: '1'
---
paper is availabe at [here](https://www.dropbox.com/s/3e9ript3iw07cbv/1603.09240.pdf?dl=0)

introduction

Before that, we should understand the Quaratic Programming (QP).
The QP has a quaratic objective function and linear constraints. Its solver in matlab (a function called quadprog) uses the formulation shown below.

$$
\begin{matrix}
\mathop{min}_\limits x \frac{1}{2} x^T H x + f^T x & s.t.\\
LB \seq x \seq UB & \\
A_{eq} x = b_{eq} & \\
A_{ieq} x \neq b_{ieq} \\
Ax \seq b
\end{matrix}
$$
where $$x=\left[x_1 \\ x_2 \right]$$, $$H=\left[h_{11} & h_{12} \\ h_{21} & h_{22}\right]$$, $$f=\left[f_1 \\ f_2 \right]$$, $$A_{eq} \in \mathbb{R}^{n_{eq}\times n}$$, $$b_{eq}\in \mathbb{R}^{n_{eq}\times 1}$$, $$A \in \mathbb{R}$$.

Lots of function :(. It's simple to understand. We just remember two keys: 1) the objective function is quaratic, 2) the constraints of objective function is linear.

We intro