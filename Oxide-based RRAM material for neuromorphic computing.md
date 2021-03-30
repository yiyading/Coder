## 本文主要内容

*文章类型：review*

*本文发布于 20 February 2018 引用202篇文献*

基于不同氧化物的RRAM用于神经形态计算：
1. 首先介绍RRAM的发展，传导的物理基础，神经形态计算的基础
2. review不同氧化物材料制造的RRAM并关注他们在神经形态计算中的应用

## Introduction

RRAM使用resistive switching（RS，电阻开关）现象存储数据，发展历程（正时间线）
1. 金属氧化物RRAM被提出
2. 64-bit RRAM array被提出
3. 3-dimension RRAM array被提出（2007）
4. HP首先提出了RRAM用于神经网络和逻辑电路的概念（2008 nature）—— memristor的概念

RRAM可用作low-power计算，可用于神经形态计算中的突触设备

refe 14-16是关于RRAM物理机制，材料，性能和应用的Paper

## Summary and outlook

不同氧化物RRAM在神经形态计算中的应用，罗列不同氧化物RRAM涉及到的参数。

器件模拟突触的空间变化和时间变化是挑战，

基于MgO的磁隧道结memristor被用于突触实现

## RRAM design and physical mechanism

RRAM的结构之一：metal-insulator-metal(MIM)；insular可采用不同氧化物

LRS或HRS的表征：两层metal中间的insulator中的filament
1. filament形成，进入LRS状态（set：HRS->LRS）
2. filament消失或被摧毁，进入HRS状态（reset：LRS->HRS）

RRAM MIM结构：
1. Symmetric：两端metal相同     ————        对称结构表现为单极开关行为
2. Asymmetric：两端metal不同    ————        非对称结构表现为双极开关行为

通过RRAM中不同的resistive switching mechanisms可以解释和建模RRAM的传导机制

RRAM MIM电极：
1. 活性电极
2. 惰性电极
3. 创新电极

1. capacitor（电容）模拟neuron bodies（神经元）
2. long wire（长电线）模拟axon（轴突）
3. short wire（短电线）模拟dendrite（树突）
4. memristor（忆阻器）模拟synapse（轴突）

突触的权重指突触的连接强度。

## Neuromorphic computing










# 文章结构

本文中心是氧化物RRAM在neuromorphic computing中的应用，基于此拓展一些RRAM的发展历程和物理机制使文章饱满并作为支撑论点。

在叙述氧化物RRAM在neuromorphic computing中的应用时，选取突触（synapse）作为应用场景，分别叙述不同氧化物制备的突触器件。

氧化物RRAM在neuromorphic computing中的应用————行文格式为总分总
> 先总结本文使用哪些氧化物RRAM为例子，再具体说明，再对other氧化物综述一下。

本文没有具体的实验，通过大量的文献引用来陈述观点。Introduction中主要介绍RRAM的发展现状，为后续论述提供论点支撑


#####

RRAM是memristor的一种