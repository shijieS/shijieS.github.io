---
layout: post
title: Translate visio to eps used in latex
date: {}
categories:
  - Tools
published: true
tags:
  - tools
comments: '1'
---

Translate visio to eps used in latex

---

- 目录
{:toc}

### Description
I have try many software for drawing which can be used in latex, such as TikZ<sup>[1](#ref.1),[2](#ref.2)</sup>, but I find it is inconvenient for me to draw by TikZ. I have used visio and it is easy to use. So I try combine visio and latex to finish my following thesis. 

### Process<sup>[3](#ref.3)</sup>

#### Open My visio and draw some flow chart
{{ site.url }}
- ![]({{ site.url }}/assets/img/20170212-1.jpg)
  
#### Select your element to printed
- ![]({{ site.url }}/assets/img/20170212-2.jpg)
  
#### Set the option for print and print it
- ![]({{ site.url }}/assets/img/20170212-3.jpg)
  
#### Open the pdf by Acrobat and cut it
- ![]({{ site.url }}/assets/img/20170212-4.jpg)
  
#### Save as eps
- ![]({{ site.url }}/assets/img/20170212-5.jpg)
  
#### insert into latex
```
\begin{figure}[h]
	\centering
	\includegraphics[width=0.4\linewidth]{img/1.eps}
	\caption[short title]{long title}
	\label{fig:1}
\end{figure}
```

### Reference
[1. TIKZ](http://www.texample.net/tikz/) <a id= "ref.1"></a>

[2. TIKZ EDT](http://tikzedt.org/index.html)<a id= "ref.2"></a>

[3. visio画的图形怎么转换为.eps格式](http://jingyan.baidu.com/article/f0e83a259ad7c222e5910107.html) <a id = "ref.3"></a>
