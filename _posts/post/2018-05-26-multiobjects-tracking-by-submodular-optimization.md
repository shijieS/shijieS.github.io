---
date: '2018-05-26 22:38 +0800'
published: true
layout: post
categories:
  - idear
tags:
  - tracking
comments: '1'
---
The paper is available [here](https://www.dropbox.com/s/h9l7f3d16g2f2ko/08303708.pdf?dl=0)

This method is detection based method for the MOT. The interesting idear of the method is formularating the mot tracking problem as a **submodular optimization problem**. The experiment has been done on *MOT chanllenge 2015*. It uses deformable part model to obtain the inital detections of frames.


#### The process of the method.

{% include image.html file="20180526223354.png" alt = "" caption="flowchart of the proposed method" class="round" %}

The proposed method follows 3 steps:

1. gernerate the low-lever trajectories by two methods (overlap criteria strategy associates and network flow strategy). The first strategy focus on the spatial constraints between two adjacent frames. The second strategy considering the appearance similarity.

2. use the designed submodular function to connect low-level trajectories.

3. occlusion handling for short-term occlusion

#### Detail
1). divide the video by 10 frames

2). use "overlap criteria method" to connect the detected boxes (this method is very simple, just connect the detected box if $$iou > 0.6$$).

3). make "network flow" as interlinear program (ILP) and solved it by IBM CPLEX Optimizer.

4). use histogram to calculate the appearance similarity and $$y$$ of the node in tracklite to get the forward motion error and backforward motion error. Then use submodular optimization to connect low-level tracklets. 

5). use the same similarity to connect the connect trajectory, by the following condition

$$
\left\{\begin{matrix}
Similarity(T_{trajectory}^i, T_{trajectory}^j) \geq \tau \\ 
Frame_i \cap Frame_j = \emptyset \\ 
minFrame_i - maxFrame_j \leq \tau_f, if i \leq j\\ 
minFrame_j - maxFrame_i \leq \tau_f, if i > j

\end{matrix}\right.
$$

Its algorithm is listed as follows,
{% include image.html file="20180527211803.png" alt = "" caption="tracking algorithm" class="round" %}



#### Result
Experiment is processed on mot2015. Its rank at 33rd. The detail is shown as follows,

{% include image.html file="20180527020956.png" alt = "" caption="result on mot chanllenge 15" class="round" %}
