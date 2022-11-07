<div align=center>
<img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/IFTS_logo.png" width=256 height=161/>
</div>

-------
## 简介

IFTS是基于Python开发的智能光通信开源仿真工具，旨在满足科学家，光通信工程师及相关领域研究人员对于光通信仿真工具包的需求。与传统通信仿真工具不同的是，IFTS提供了基于Pytorch的仿真版本，并集成多种神经网络算法，这使得仿真平台可借助GPU和神经网络对仿真进行加速，天然兼容光通信的智能化算法设计。

## 特点

* 基于Python开发。易于上手，可根据自身需求扩展其功能。
* 提供高效仿真。GPU并行计算与AI信道模型，加速智能仿真平台。
* 开源免费。IFTS作为开源通信工具包，致力于助力光通信智能化研究。
* 使用智能算法。聚焦光通信领域前沿，融合AI框架。

## 可用功能

IFTS提供了对完整光通信系统的传输仿真，内部可分为信道、发射端、接收端、信号和工具包等模块，是一款全面高效的光通信仿真工具包。以下为IFTS提供的模块的简要介绍，具体内容请用户参阅IFTS发布网站中的 **[用户手册说明](https://ifibertrans.sjtu.edu.cn/manual/)**。

### 信号模块

信号模块包含了与信号相关的操作，例如信号序列的生成、信号的调制与解调、信号相关的性能计算等，实现了仿真平台对信号部分的仿真，为其他模块提供了基础。

### 信道模块

信道模块用于构建仿真信道环境，支持光纤信道以及AWGN信道传输。其中光纤信道仿真可进一步分为仿真信道器件模块以及仿真信道传输模块，实现的功能按照信号处理流程依次为：波分复用、信道传输、解复用和相干接收。本平台支持的仿真光纤传输方法包括分布式傅里叶算法(split-step fourier method,SSFM)以及AI信道模型方法。

### 发射机模块

发射机模块实现对发射端的仿真，主要涉及到信号的脉冲整形。

### 接收机模块

接收机模块实现对接收端的仿真，主要内容包括接收端的多种DSP算法，如载波相位估计、自适应滤波、色散补偿、IQ平衡等算法。

### 工具包模块

工具包模块包含了代码中需要使用的各种功能性函数，例如进制转换、重采样、滤波器设计、滑动平均、数值计算等，为仿真提供了基础性的帮助。

## 结果展示

IFTS提供了对完整传输过程的仿真，并可以通过画图实现其中结果的可视化。下面对部分结果进行了展示，更多内容请用户参阅IFTS发布网站中使用说明的 **[代码运行](https://ifibertrans.sjtu.edu.cn/use.html)** 内容。


<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/WDM_PSD.png" width = "50%" height = "50%" ></div>
   	
<center>图1.波分复用信号功率谱密度图</center>


最后，我们希望借助IFTS提供算法验证平台，降低光通信智能化研究的门槛，打通信息壁垒。我们欢迎相关领域的专家下载、使用和改进IFTS，共同推动光通信的智能化发展。

<br>

<p align="right" > By  智能光纤系统实验室LIFE智能光通信团队   &emsp; &emsp; &emsp;     </p>

<p align="right" > 上海交通大学区域光纤通信网与新型光通信系统国家重点实验室 </p>

## Introduction

IFTS is an open source simulation tool for intelligent optical communication based on Python, which aims to meet the needs of scientists, optical communication engineers and researchers in related fields for optical communication simulation toolkits.Different from the traditional communication simulation tools, IFTS provides a simulation version based on Pytorch, and integrates a variety of neural network algorithms, which makes the simulation platform can accelerate the simulation with the help of GPU and neural network, naturally compatible with the intelligent algorithm design of optical communication.

IFTS is published on **[the website of IFTS](ifibertrans.sjtu.edu.cn)** of the Laboratory of Intelligent Fiber Ecosystem(LIFE), Shanghai Jiao Tong University.We hope to provide an algorithm verification platform with the help of IFTS, reduce the threshold of intelligent optical communication research, and break through the information barriers. Experts in related fields are welcome to download, use and improve IFTS, and submit your optimization and modification to this git repository, so as to jointly promote the intelligent development of optical communication.

<br>

<p align="right" > By  Intelligent optical communication team of LIFE   &emsp; &emsp; &emsp; &emsp; &emsp;     </p>

<p align="right" > State Key Laboratory of Advanced Optical Communication Systems and Networks </p>
