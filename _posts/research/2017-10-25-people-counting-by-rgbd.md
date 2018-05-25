---
layout: research
title: People counting by RGB-D camera
date: '2015-01-01 01:30:13 +0800'
categories: research counting
tags: counting
published: true
---
The purpose of this project is to counting the people passing through the bus by RGB-D camera accurately.

This project starts from 2015.01 to 2017.05. 

#### designed a software and hardware system
We have designed a software and hardware system. 

The software system includes: calibration, one-camera counting, double camera counting, recording, auto testing. The hardware system. 

The hardware system includes: designed RGB-D camera, redesigned mini-computer. Besides, we also integrated our algorithm into the camera. 

#### published a dataset 
\[[github](https://github.com/shijieS/people-counting-dataset.git)\]

We have published a dataset, called **P**eople **c**ounting **d**ata**s**et (PCDS). It is divided into 4 sub-categories: N+C+, N+C-, N-C+, N-C- according to the sunlight and crowed, as shown in the following table.



|          |  N+C+  |  N+C-  | N-C+ | N-C- |
|:--------:|:------:|:------:|:----:|:----:|
| sunlight | strong | strong | weak | weak |
| crowed   |   yes  |   no   |  yes |  no  |
| entering |  937 |  616 |  5427 | 2704 |
| exiting  | 1149 |  668 |  6647 | 2760 |
| total    | 2086 | 1284 | 12074 | 5464 |

There are total up to 5,464 videos in this dataset. The detail number of people entering and exiting the bus in each category can be referred from the following table.

#### published a paper 
\[[pdf](https://www.researchgate.net/publication/324492648_Benchmark_data_and_method_for_real-time_people_counting_in_cluttered_scenes_using_depth_sensors) \]

We have written a paper to clarify our algorithm. This paper's name is "Benchmark data and method for real-time people counting in cluttered scenes using depth sensors".

Besides, two patent has been published, as follows:
- 宋焕生,**孙士杰**,张朝阳,刘瑞芝,张文涛,崔华,李钢,李怀宇,张向清,李莹,潘强,王璇,杨燕妮,孟乔,孙亚,李婵. 一种基于轨迹分析的人数统计方法[Z]. CN106600643A: 长安大学,2017.
- 宋焕生,**孙士杰**,刘瑞芝,张文涛,张朝阳,崔华,李钢,李怀宇,张向清,李莹,陈艳,王璇,杨燕妮,孟乔,潘强,李婵,孙亚. 一种基于RGB#D相机的人数统计方法[Z]. CN106570883A: 长安大学,2017.
- 宋焕生,**孙士杰**,庞凤兰,刘瑞芝,李倩丽,王璇,张文涛. 一种基于3D轨迹分析的目标检测识别算法[Z]. CN106127137A: 长安大学,2016.
- 宋焕生,**孙士杰**,刘瑞芝,张朝阳,张文涛,李莹,张向清,李怀宇,崔华,李钢,陈艳,王璇,李婵,孙亚. 一种复杂场景下的人数统计方法[Z]. CN106228560A: 长安大学,2016.
- 宋焕生,**孙士杰**,张朝阳,刘瑞芝,王璇,陈艳,李怀宇,崔华,张文涛,张向清,李莹,严腾,郑宝峰,张斌. 一种基于三维映射表的三维点云快速重建方法[Z]. CN105913488A: 长安大学,2016.
