<div align=center>
<img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/IFTS_logo.png" width=256 height=161/>
</div>

-------
# 简介

IFTS是基于Python开发的智能光通信开源仿真工具，旨在满足科学家，光通信工程师及相关领域研究人员对于光通信仿真工具包的需求。与传统通信仿真工具不同的是，IFTS提供了基于Pytorch的仿真版本，并集成多种神经网络算法，这使得仿真平台可借助GPU和神经网络对仿真进行加速，天然兼容光通信的智能化算法设计。

### 注：当前阶段您还无法从GitHub中直接获取IFTS源代码，当前GitHub仅为我们提供了一个平台进行交流。如果您想使用与下载IFTS，您可以访问我们的 **[IFTS发布网站](https://ifibertrans.sjtu.edu.cn/)** ，从网站中获取IFTS。 


# 特点

* 基于Python开发。易于上手，可根据自身需求扩展其功能。
* 提供高效仿真。GPU并行计算与AI信道模型，加速智能仿真平台。
* 开源免费。IFTS作为开源通信工具包，致力于助力光通信智能化研究。
* 使用智能算法。聚焦光通信领域前沿，融合AI框架。

# 可用功能

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

# 结果展示

IFTS提供了对完整传输过程的仿真，并可以通过画图实现其中结果的可视化。下面对部分结果进行了展示，更多内容请用户参阅IFTS发布网站中使用说明的 **[代码运行](https://ifibertrans.sjtu.edu.cn/use.html)** 内容。

### 波分复用

IFTS支持在信道中传输波分复用信号，如图1为三通道的信号功率谱密度示意图。

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/WDM_PSD.png" width = "50%" height = "50%" ></div>

<div align="center">

图1.波分复用信号功率谱密度图
</div>

### 光纤信道

当前版本的智能光传输仿真平台中，除了利用分布式傅里叶算法（SSFM）实现传输时光纤信道的仿真以外，IFTS还提供了利用生成式对抗网络（GAN, Generative Adversarial Networks）对光纤信道进行建模的NN信道仿真。NN信道仿真在保证准确率的同时能够实现光纤信道仿真的加速。如图2和图3分别为单通道，80km,入纤功率10.0dBm的条件下，采用SSFM与AI信道模型与进行传输仿真得到的收端经色散补偿后的信号星座图。

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_LC_SSFM.png" width = "50%" height = "50%" ></div>

<div align="center">

图2.分步傅里叶方法仿真传输信号收端色散补偿星座图
</div>

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_LC_GAN.png" width = "50%" height = "50%" ></div>

<div align="center">

图3.GAN模型传输信号收端色散补偿星座图
</div>


### 信号恢复

发射端发送的光信号在经过光纤信道传输后不仅存在幅度的衰减，还存在由于光纤线性与非线性导致的信号畸变。仿真平台接收端采取一系列DSP算法，包括低通滤波，IQ平衡，色散补偿，自适应滤波，同步，载波相位估计等模块进行修正补偿，完成接收端信息恢复。如图4为收端DSP处理后的复原信号星座图。

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_CPE.png" width = "50%" height = "50%" ></div>

<div align="center">

图4.收端DSP处理后的复原信号星座图
</div>

# 常见问题

## 如何下载和使用IFTS

当前阶段我们未将IFTS上传至GitHub中，所以您目前暂时无法从GitHub中直接下载与使用IFTS。您可以访问我们的 **[IFTS发布网站](https://ifibertrans.sjtu.edu.cn/)** ，登录网站后下载与使用IFTS，并参阅相关文档。

## GitHub平台的作用

虽然当前您无法直接从GitHub上获取IFTS，但是GitHub为我们提供了一个平台进行交流。您可以将您在IFTS基础上修改的代码或新增的测试通过GitHub issue进行提交；或将您遇到的Bug通过GitHub进行描述与反馈。我们将非常感谢您对IFTS的贡献。当然，我们更乐意您能够通过IFTS发布网站的[社区](https://ifibertrans.sjtu.edu.cn/community.html)与我们进行沟通与交流。

## 如何引用IFTS

如果您使用我们的智能光传输仿真平台后认为IFTS对您的的研究工作有所帮助，并且将IFTS用于出版物、报告或demo演示等，我们将非常感谢您的引用。我们提供了两种引用格式如下所示：

#### MLA格式

---
   Zekun Niu, Hang Yang, Lyu Li, Minghui Shi, Chuyan Zeng, Chenhao Dai, Guozhi Xu, Haochen Zhao,
   and Lilin Yi. “Intelligent Fiber Transmission Simulation.” Intelligent Fiber Transmission 
   Simulation Platform of Shanghai Jiao Tong University, LIFE, 2022, ifibertrans.sjtu.edu.cn/.
   
---

#### BibTeX格式

---
   @misc{IFTSv0.1,
   author = {Zekun Niu and Hang Yang and  Lyu Li and Minghui Shi and  Chuyan Zeng and Chenhao 
   Dai and Guozhi Xu and Haochen Zhao and Lilin Yi},<br>
   title = {Intelligent Fiber Transmission Simulation},<br>
   howpublished = {Available at \url{ifibertrans.sjtu.edu.cn}},<br>
   year = 2022
   }

---

## 使用许可

IFTS使用GNU通用公共许可证（GNU General Public License）。用户选择下载并使用本项目，即视为用户同意并遵循该协议。详细请见[LICENSE](https://ifibertrans.sjtu.edu.cn/use.html)

<br>
总而言之，我们希望借助IFTS提供算法验证平台，降低光通信智能化研究的门槛，打通信息壁垒。我们欢迎相关领域的专家下载、使用和改进IFTS，共同推动光通信的智能化发展。

<br>

<p align="right" > By  智能光纤系统实验室LIFE智能光通信团队   &emsp; &emsp; &emsp;     </p>

<p align="right" > 上海交通大学区域光纤通信网与新型光通信系统国家重点实验室 </p>



-------
# Introduction

IFTS is an open source simulation tool for intelligent optical communication based on Python, which aims to meet the needs of scientists, optical communication engineers and researchers in related fields for optical communication simulation toolkits.Different from the traditional communication simulation tools, IFTS provides a simulation version based on Pytorch, and integrates a variety of neural network algorithms, which makes the simulation platform can accelerate the simulation with the help of GPU and neural network, naturally compatible with the intelligent algorithm design of optical communication.

### Note: At present, you cannot directly obtain IFTS and its code from GitHub. Now, GitHub only provides us with a platform for communication. If you want to use and download IFTS, you can visit our **[IFTS publishing website](https://ifibertrans.sjtu.edu.cn/)**  to obtain IFTS.

# Characteristic

* Python based development. It's easy to use, and can be expanded based on user's own needs.
* Provide efficient simulation. GPU parallel computing and AI channel model is used to accelerate intelligent simulation platform.
* Open source and free. As an open source communication toolkit, IFTS is committed to assisting the intelligent research of optical communication.
* Use intelligence algorithms. Focus on the forefront of optical communication, and integrate AI framework.

# Available Features

IFTS provides transmission simulation for complete optical communication system, which can be divided into modules such as channel, transmitter, receiver, signal and tool box. It is a comprehensive and efficient optical communication simulation kit. The following is a brief description of the modules provided by IFTS. For details, please refer to the **[user manual](https://ifibertrans.sjtu.edu.cn/manual/)** on the IFTS publication website 。

### Signal Module

The signal module includes the operations related to the signal, such as the generation of signal sequence, signal modulation and demodulation, signal related performance calculation, etc., which realizes the simulation of the signal part of the simulation platform and provides the foundation for other modules.

### Channel Module

The channel module is used to build the simulation channel environment and support fiber channel and AWGN channel transmission. The fiber channel simulation can be further divided into the simulation channel device module and the simulation channel transmission module. The functions realized according to the signal processing process are wavelength division multiplexing, channel transmission, demultiplexing and coherent receiving. The simulation optical fiber transmission methods supported by the platform include the distributed split-step fourier method (SSFM) and AI channel model method.

### Tx Module

The Tx module realizes the simulation of the transmitter, which mainly involves the pulse shaping of the signal.

### Rx Module

The Rx module realizes the simulation of the receiver, which mainly includes a variety of DSP algorithms on the receiving end, such as carrier phase estimation, adaptive filtering, dispersion compensation, IQ balance and other algorithms.

### ToolBox Module

The toolbox module contains various functional functions that need to be used in the code, such as base conversion, resampling, filter design, sliding average, numerical calculation, etc., which provides basic help for simulation.

# Results Presentation

IFTS provides a simulation of the complete transmission process, and the results can be visualized by figure. Some of the results are shown below. For more information, please refer to the **[code running instructions](https://ifibertrans.sjtu.edu.cn/use.html)**  on the IFTS distribution website. 

### WDM

IFTS supports the transmission of WDM signals in the channel. Figure 1 shows the schematic diagram of signal power spectral density of three-channel.

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/WDM_PSD.png" width = "50%" height = "50%" ></div>

<div align="center">

Fig 1.Power spectral density diagram of WDM signal
</div>

### Fiber Channel

In the current version of IFTS, in addition to using SSFM algorithm to realize the simulation of optical fiber channel during transmission, IFTS also provides NN channel simulation to model fiber optic channels using Generative Adversarial Networks (GAN). NN channel simulation can realize the acceleration of fiber channel simulation while ensuring the accuracy. In Figure 2 and Figure 3, the signal constellation of the receiver after dispersion compensation is obtained by using SSFM and AI channel model and transmission simulation under the condition of single channel, 80km and 10.0dBm power, respectively.

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_LC_SSFM.png" width = "50%" height = "50%" ></div>

<div align="center">

Fig 2.Dispersion compensation constellation of SSFM model
</div>

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_LC_GAN.png" width = "50%" height = "50%" ></div>

<div align="center">

Fig 3.Dispersion compensation constellation of GAN model
</div>


### Signal Recovery

The optical signal sent by the transmitter not only has amplitude attenuation after transmission through the fiber channel, but also has the signal distortion caused by the linear and nonlinear affection. The receiver of the simulation platform adopts a series of DSP algorithms, including low-pass filtering, IQ balance, dispersion compensation, adaptive filtering, synchronization, carrier phase estimation and other modules to correct compensation and complete the information recovery at the receiver. Figure 4 shows the constellation diagram of restored signal after receiver DSP.

<div align=center><img src="https://github.com/FiberTransOfLIFE/IFTS/blob/main/img/Constellation_After_CPE.png" width = "50%" height = "50%" ></div>

<div align="center">

Fig 4.Constellation of recovered signal after receiver DSP
</div>

# FAQs

## How to install and use IFTS

At the current stage, we have not uploaded IFTS to GitHub, so you cannot directly install and use IFTS from GitHub. You can visit our **[IFTS publishing website](https://ifibertrans.sjtu.edu.cn/)**, log in to the website, install and use IFTS, and refer to relevant documents.

## The role of GitHub

Although you cannot directly obtain IFTS from GitHub, GitHub provides us with a platform for communication. You can submit your modified code or new test based on IFTS through GitHub issue; Or describe and feed back the bugs you encounter through GitHub. Of course, we would like you to communicate with us through the [community](https://ifibertrans.sjtu.edu.cn/community.html) of IFTS publishing website.

## How to reference IFTS

If you use our transmission simulation platform and think that IFTS is helpful to your research work, or you use IFTS for for a publication, presentation or a demo, we will appreciate your reference. We provide two reference formats as follows:

#### MLA format

---
   Zekun Niu, Hang Yang, Lyu Li, Minghui Shi, Chuyan Zeng, Chenhao Dai, Guozhi Xu, Haochen Zhao,
   and Lilin Yi. “Intelligent Fiber Transmission Simulation.” Intelligent Fiber Transmission 
   Simulation Platform of Shanghai Jiao Tong University, LIFE, 2022, ifibertrans.sjtu.edu.cn/.
   
---

#### BibTeX format

---
   @misc{IFTSv0.1,
   author = {Zekun Niu and Hang Yang and  Lyu Li and Minghui Shi and  Chuyan Zeng and Chenhao 
   Dai and Guozhi Xu and Haochen Zhao and Lilin Yi},<br>
   title = {Intelligent Fiber Transmission Simulation},<br>
   howpublished = {Available at \url{ifibertrans.sjtu.edu.cn}},<br>
   year = 2022
   }

---

## Use License

IFTS uses the GNU General Public License. If the user chooses to install and use our project, it is deemed that the user agrees and follows this agreement. See [LICENSE](https://ifibertrans.sjtu.edu.cn/use.html) for details.

<br>

In a word, we hope to provide an algorithm verification platform with the help of IFTS, reduce the threshold of intelligent optical communication research, and break through the information barriers. Experts in related fields are welcome to download, use and improve IFTS, so as to jointly promote the intelligent development of optical communication.
<br>

<p align="right" > By  Intelligent optical communication team of LIFE   &emsp; &emsp; &emsp; &emsp; &emsp;     </p>

<p align="right" > State Key Laboratory of Advanced Optical Communication Systems and Networks </p>

