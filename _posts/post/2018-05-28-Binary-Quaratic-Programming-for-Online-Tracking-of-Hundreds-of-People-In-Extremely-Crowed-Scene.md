---
date: '2018-05-28 10:32 +0800'
published: true
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
LB \leq x \leq UB & \\
A_{eq} x = b_{eq} & \\
Ax \leq b
\end{matrix}
$$
where $$f=\left[\begin{matrix} f_1 \\ f_2 \end{matrix}\right], A_{eq} \in \mathbb{R}^{n_{eq}\times n}, b_{eq}\in \mathbb{R}^{n_{eq}\times 1},b\in \mathbb{R}^{n_{ieq}\times 1}, A \in \mathbb{R}^{n_{ieq}\times n}$$. 

$$n$$ is the number of decision variable, $$n_{eq}$$ is the number of equality constraints, $$n_{ieq}$$ is the nubmer of inequality constrains.


Lots of function :(. It's simple to understand. We just remember two keys: 1) the objective function is quaratic, 2) the constraints of objective function is linear.

We introduce an example of problem.

A manufactureer has done empirical modeling of their production system and has determined that their production cost is determined by the equation: 

$$
\begin{matrix}
\mathop{cost} = 0.4x^2 - 5x_1 + x_2^2 - 6x_2 + 50 & s.t. \\
10 \le x_1 < 1000 & 
10 \le x_2 < 1000 &
\end{matrix}
$$
where $$x_1$$ and $$x_2$$ are the decision variable, in this case, the rate at which they should run Unit1 and Unit 2 respectively. Find the optimal combination of $$x_1$$ and $$x_2$$ that minimizes the cost.

{? include image.html file="20180528120320.png" caption="3D graph of cost function" class="round" ?}

