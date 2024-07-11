---
title: 基于多源传感器的城市人居环境与居民健康感知：中国武汉的案例研究
date: 2023-07-10
authors: [zhangyan]
slug: skill
description: >
  Just for test
categories:
  - 科研技巧
---

测试用

<!-- more -->

![cover_image](http://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8s5fKt6qCegsIU9vROtvoHyOHoCiazCu2nrSCTzfpuSzsMDpeXkKs1ibw/0?wx_fmt=png)

#  基于多源传感器的城市人居环境与居民健康感知：中国武汉的案例研究

张岩  [ 城市感知计算 ](javascript:void\(0\);)

**城市感知计算**

微信号  sensingcity

功能介绍  认识世界和改造世界，分享地理信息系统科普知识与学术研究，欢迎加好友学术交流。

__ __

__ _ _ _ _

给大家分享一篇最新录用在BAE的一篇文章，文末有对应的PPT分享。

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8sfOd8COqBbavrw39h5Bl6G4It2Mhbsc1Giahol8zxNicbkDHoakD7yxQ/640?wx_fmt=jpeg)

关于新冠疫情的文章已经太多太多了，像一些比较容易的研究如疫情确诊与气候，温度之类的研究已经做的很充分了，但是利用不同的数据在不同的区域甚至会得出截然相反的结论。其原因在于研究的地理尺度过大，且考虑因素过于单一。我的想法是从地学的角度出发，融合社会感知网络，遥感网络，传感器物理感知网络已经一些统计数据，对疫情的驱动力并进行拟合。我的研究尺度是社区级的，在武汉市进行实验，利用语义分割计算了社区街景，爬取链家网的社区属性数据，利用遥感计算社区的LAI指数，利用POI对社区周边的便利性进行表示，使用组里部署的传感器记录疫情期间的环境变化，以及利用这些数据构建了驱动模型。然而，任何建模都会有一个问题，你怎么确定你的模型是合理，正确的？在听取信息管理学院的一次讲座中，我了解了SEM模型，这是一种类似于测量平差的统计模型，我使用这种模型来解决信度的问题。我们的模型可以解释了28.9％社区确诊人数的方差，这个比例虽然不高，但是我认为是合理的，我们是从社区空间异质性，经济异质性的角度入手的，疫情还会受到非常多的因素，如防疫政策，社区人口年龄分布与工作类型。
**此外，在大家买房时推荐大家购买新建的社区，容积率更好的社区，天空率越高也就是观感越明亮的社区，根据我们的研究这些社区会对疫情有着非常好的抵抗能力。**

  

撰写这篇文章时，阅读了国内很多微信公众号创作者的分享
(如小猿猴Giser,Yuan的数据分析,小明的数据分析笔记本等)，传感器数据得到了林欣和程博文的帮助。陈栋博士提供了传感器的具体参数，与马洪亮博士讨论了湿度与空气质量的关系，室友王培晓博士提供了武汉市的疫情数据支持，在论文的Acknowledgments部分一并感谢。

COVID-19大流行无疑对世界经济，特别是城市经济产生了巨大的影响。我们希望在社区范围内讨论城市生活环境与确诊病例数的关系，研究社区感染的驱动力和传播途径。我们选取武汉市650个有COVID-19病例的社区作为研究对象。我们利用深度学习语义分割技术计算街景的绿视率指数（VGI）和天空率（SVF），并利用偏最小二乘结构方程模型（PLS-
SEM）研究疫情的驱动力。同时利用传感器记录的温湿度信息进行城市感知。我们发现，SVF指数对病毒传播有一定的抑制作用，但与我们的直观认识相反，较高的VGI指数却对疫情传播有一定的促进作用。本文构建的结构方程模型可以解释28.9%的确诊病例数的方差，结果(路径coef.)表明，社区的居住密度(0.517)是大流行病例的主要影响因素，社区生活的便利性(0.234)对其影响很大。社区人居适宜性较优的社区（如建设时间、价格）在面对大流行事件时更安全。SVF和VGI对疫情结果的影响是否意味着阳光可以有效阻断病毒的传播？这种不同社区的空间异质性对我们探索COVID-19的环境传播很有帮助。

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8Uem6vqgzAj2yD9V49cNYiaGqN2Cu5L1qNqTbW5Dz3aU5mRkjjkVZRYQ/640?wx_fmt=jpeg)

**本文的技术路线**

**  
**

**01**

本文回答的研究问题如下。

  

(RQ1):不同经济属性的社区在面对公共卫生事件时，其抗风险能力是否存在差异？

  

(RQ2):不同社区指标之间存在怎么样的交叉影响？SEM模型对COVID-19大流行确诊病例的解释力如何？

  

(RQ3):大流行的主要环境驱动因素是什么？除此之外，温度和湿度的影响是否显著？

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8rVrd4Iq3yBLMRN20iakGMaRJVcI1jCDTxnTNpxJeDJj6huVPRnZPG1w/640?wx_fmt=jpeg)

不同社区迥异的环境

这是否会影响流感大流行的

**02**

城市街景建立了城市图像与地理实体之间的映射关系，为解决城市传感的大规模推演提供了新的契机。它可以帮助我们了解周围环境，进行地理计算。关于居住环境健康影响的研究很多，如利用街景数据将老年抑郁症与街景绿化关联起来，归一化差异植被指数(NDVI)对心理健康的积极影响。发展中国家绿化暴露与抑郁症之间的相关性，研究不同社区之间的社会不平等性，以及城市对多个情感维度（安全感、活泼度、美感、财富感、无聊感、抑郁感）的感知。然而，大量的研究者将研究方向集中在城市环境中的精神疾病或精神状态上，而很少有研究者研究不同社区之间（如贫民窟与富人区）疫病（SARS、COVID-19、MERS）传播程度的差异，以及与人居环境的耦合效应。

  

我们的分析对象是社区，因变量是确诊大流行的数量，旨在揭示其异质性。模型指标包括物理指标、社会经济指标、空间位置指标、生态环境指标和人口密度指标.基于社会传感、传感器网络和遥感影像的自然环境、建筑环境和社会环境的相关研究数据。
本文的优势在于：除了城市街景，我们还利用多种被证明与病毒传播相关的评价指标(如气候条件、社区周边环境)，从地理信息系统(GIS)的视角建立了一套相对完整的以人为中心的风险暴露评估体系，利用可观测变量值对社区的安全性进行评估。我们认为暴露模型的过程是一个不断发展的耦合确认的案例和人类居住区和系统。基于已建立的指标评价体系，利用结构方程模型（SEM）对COVID-19进行了案例研究。

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI87q0cC4Tic4jd0pe39mfyL595pCAQeWACzbCxAEibXclLSicDiaf1w4u8Hg/640?wx_fmt=png)

街景语义分割

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8q5axb7qboFPgPribPhFFb0JA07W4B1RGLQCQBdHB7GZcFCcFO8F6nYw/640?wx_fmt=png)

街景分类HH,HL,LH,LL

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8UCeyWPRu3738PIq8uyqjQLJww43sicXjAG6yHIWGnsmXuGciaCKSdicEQ/640?wx_fmt=png)

利用遥感影像验证街景分割的可靠性（正相关）

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8UTGOUjBSdAQahvRTdJSxECncpodrH1nBYpoeDBZm5RiaV6YibBFCmIDg/640?wx_fmt=jpeg)

**03**

如表2所示，本文以房价、物业费、建设年限、可视绿化指数、绿视率系数、人口密度、社区住房、社区建筑、确诊人数、周边教育POI数、商铺POI数、交通POI数、医院POI数和公园POI数为指标变量，整理并计算出研究区域内650个社区的十四个评价指标。根据表现变量，我们在PLS-
SEM中采用了4个不同的环境变量和2个物理变量。

我们认为，社区的居住密度对确诊病例有绝对的影响，而以社区房价为代表的适宜性指数对社区的VGI和SVF有影响(一般认为社区越好，管理和环境越好)。同样，社区的周边环境也会对社区的VGI/SVF产生影响。我们假设上述潜变量都对社区的确诊病例数有影响。根据既定的评价指标，在此假设基础上构建了PLS-
SEM，我们将在下一节讨论我们模型的合理性和可靠性。

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8ANcGuXPvhdacibNm7mSxoOhqxIqJW3CI2d1tEtUOXkBkSkSLbVibM7gg/640?wx_fmt=png)

指标相关性与两两拟合

**04**

在指标相关性图中突出的是VGI与病例的正相关，SVF与VGI在置信度为p=0.05时呈负相关，这与以往的研究不一致。一个可能的解释是，高绿化率阻挡了部分阳光。相应的，SVF越高，阳光就越多，阳光对疫情的传播有一定的阻挡作用。这个结论不能排除一些其他原因。较高的植被覆盖率通常与长期建立的群落和古树有关，这些群落可能位于城市的旧社区。换句话说，这些社区可能没有必要的基础设施，也没有得到很好的管理。所以，这些社区的cases较多。除此以外，还有人口密度、社区人口的占有率、社区人口的年龄分布、社区周围的环境、温度和湿度等因素的干扰。有学者研究了阳光和病毒之间的传播机制，在一定程度上支持了我们的结论。我们将在下一节详细分析人类居住区与流行病传播之间的相互作用机制。

此外，社区
房价越贵，小区的超高层建筑越多，小区的VGI越高。我们用建筑年份的中位数来划分社区数据。红色代表较新的社区(建设年份为2005年以后)，绿色代表较老的社区(建设年份为2004年以前)，新社区和老社区的SVF分布在置信度为p=0.01的情况下没有通过t检验，说明这两种类型的分布有显著差异。
除此之外，与我们的常识一致（即住户越多，确诊病例越多），新社区往往人口较多，而人口较多带来的确诊病例风险更大。但是，社区竣工年份与确诊病例数呈现负相关关系，这可能受到其他因素的影响（如社区越新，SVF值越高）。2015年前后，新建社区的数量明显减少（这可能与当时房地产市场的降温有关）。随着中国城市化进程的放缓，人们的关注点已经从房子的大小转移到社区的品质上。人们愿意为更好的绿化和更低的社区容积率支付更高的价格。显然，武汉也顺应了这一趋势，新建小区的SVF和VGI较高。

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8blnXpXibMG7U3ZPvO0uyltHGlZ0ME6koBW1Blfzv3O4tENicdOk3E9kw/640?wx_fmt=png)

模型结构

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8wRKktgp2B1XrISSPr5ag0qnOg1xIRKYicS2naqetN7jCNQuNn6XyGIA/640?wx_fmt=jpeg)

模型信度效度评估

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8GBxBPhetMC7NSxyl4AU0lqB3jUCxaMhdUHDVqPWJtyKDtBNoxhjDwg/640?wx_fmt=jpeg)

模型路径系数

**05**

SEM的路径分析结果如上所示，可观测变量用矩形表示，潜变量用圆圈表示，变量之间的关系用箭头表示。fee和density的因子载荷接近于零，说明该变量的设置对模型结构影响不大。我们对模型进行了调整，去掉了这两个变量，使其更加合理。

PLS-
SEM模型解释了28.9％的诊断结果的方差。在疫情背景下，缓冲区内的医院、教育、公园数量的因子载荷分别为0.783、0.714、0.661。此外，社区的居住密度在房屋（0.938）和建筑（0.627）两个观测值下可以得到最好的解释。

潜变量之间存在不同的路径：在p=0.01的置信水平下，社区周围的便利性与确诊病例数呈正相关（路径系数=0.234,p=0.01），仅低于居民密度指数。便利度与SVF/VGI之间的路径系数（-0.162/-0.023）表明社区周边大量的POI会对社区景观产生负面影响。兴趣点越多，意味着社区周边越繁华，摩天大楼越多，从而降低影响社区的VGI和SVF。另一方面，社区周边有商场和交通站点的地区，人口流动会更加频繁，这也会增加居民接触病毒的风险。

好消息是，适宜性和天空率对抗击疫情有一定的积极影响，如足够的物业管理水平、足够的楼间距和足够的日照，导致在p=0.05的置信条件下，这些社区的确诊病例下降。植被覆盖率的差异不能导致该病毒存活率的差异，但可以导致病毒传播方式的差异（更容易或更难传播），并进一步导致不同社区的covid-19病例数的差异。社区人居环境的适宜性(楼龄较新)将对社区环境的天空率(0.174)和社区生态的绿化率(0.063)产生正向影响。

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8IoFBdkiayJB1VfXU8NdZKKhtqSzv47IsQFCp4VPgJicibACvRaxFW2j3Q/640?wx_fmt=png)

确诊人数随温湿度的波动

**06**

文章的最后进行了传感器记录的数据与疫情确诊/康复人数的对比，由于政府抗疫政策的坚决执行，武汉的疫情控制很快，我们的研究不具有典型性。
在传感器记录期间，气温从5摄氏度上升到20摄氏度。湿度与温度之间似乎存在滞后负相关关系，但这不是本文的重点。康复的峰值值与确诊的峰值值之间有半个月的滞后时间，说明在良好的治疗环境下，患者可以在半个月以上恢复。更重要的是，确诊人数与传感器记录的中位温度的Pearson系数显示为-0.372(p=0.000)，环境温度与康复人数之间存在显著的正相关系数(0.183)(p=0.182)。同时，湿度与确诊病例的Pearson相关指数为0.102(p=0.332)，说明病毒在一定程度上对潮湿阴凉的环境有偏好，这在一定程度上支持我们的结论。

1.文章访问链接：https://pan.baidu.com/s/1xE9DWMoUvmyrNqTa1tPs

提取码：6ozr

2.打一个广告，发表在ceus上的文章见刊了，现在可以免费下载和访问，请大家多多引用:

https://www.sciencedirect.com/science/article/pii/S0198971521000363

3.黄敏师兄最新发表的论文，请大家多多引用:

https://www.tandfonline.com/eprint/4GEWSIKYRVYWKTAYH8IX/full?target=10.1080/15481603.2021.1909304

4.最后是文章对应的PPT讲解

![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01XlicBQNgIw78mibz8PC53fXIpaBr3FcRxxWLpJiaYhUhZ6weIiaXzypnjg/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01E1ALN0TibXhdia3vic68wgLynZprURZDI5pz9WibSpmQ6JqjOw8r8wUNibA/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01ONSGUJSzn7ccTUZQSBfGQslLD5F3XpGLhKWrjG7SJpm3oMQxZ3gIEA/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01vwIBaLuWMfMkUQcyDWbiaia0AhxXZxUUic27lHHNHibynjaPxciaxDtYaLA/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01jZkGp5k1vrOe0LEfxMicvHZK0rvZKEBHEWZ9Aia8TROibjJNYulGS1LdA/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01Xe1kZhMv44Fs63mn6oyGBGU5302CAMXEFG62viavlXp4mMoFXfWZ2Rw/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01SFGzlOonRSHCrNGB6gWFACeMOia8yPfDer852IzKoSjmcyo6hHpwVfQ/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01tRY35ria7rffsT8BvjktaUDqQphys7YF1fbpHgkhsK5FqVX92iahquVg/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01VvojmVOicsrNFceIicwvhicgahG27COUa3Rw5QAeq54gt3ZjZjWxWx8ibg/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01NY3Ltj9qsDqQvR3bCSDRtJZBsMz6w5NrHcddqpaUp92aoB2Hk8sx6g/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01BKVYerjciauwS8dYcruuGiatOJjaKhZAIibuBlgfmOQRfnz2tKsnIgYxw/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01O4v7WPhgwulIppkYdMwRxkMmbic075xTsugm0lqm0d3yaXUicpqQYBAw/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01PRQiahe8CpowEW4icPwK59u8LBT9iap28sF7w9YQiaJz73CeNH6aGeIaoA/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01JNSeYrsic3NicUia2gvNBz679TlhM279vm8MxnAicmqryI9pz6UQW3D1Pg/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01thKQiaKT3QIsSvrmfzWyuIyt3J3rcn3xqtZwV29DwWCYe5SYjWaXibIQ/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01gCAeY8RUCpmu2RkVkdZrQyZkj5aZEz7piaAVZJ9FPSJlo1ibnPichao6A/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01rsebSuQGkZtI72QWLNPgJZ2OZBybFy9v2HDRgictVVSzNvxkiaKxcpHw/640?wx_fmt=png)
![](https://mmbiz.qpic.cn/mmbiz_png/S9HsqSVeUqvhibgxRFpckz5IpKdPbHD01tcOjc0YJ3domyClSpmUqyDXjBEX99gRGy8Jm4pxddn1hWIpJSDJKag/640?wx_fmt=png)

  

![](https://mmbiz.qpic.cn/mmbiz_jpg/S9HsqSVeUqu4kY25G9jleXR4kc0XnmI8GC3jEb4yrfPknvYn32bKeK9lxIJc118PHZwdBibSRZV8xq08yQuR8Sw/640?wx_fmt=jpeg)

**协同感知与智能推理**

预览时标签不可点

微信扫一扫  
关注该公众号





****



****



  收藏

