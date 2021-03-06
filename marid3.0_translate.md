
![iab](http://oz3on0sof.bkt.clouddn.com/iab.jpg)
  
# 移动富媒体互动广告标准(MRAID)

## VERSION3.0  
 
## 7月 2017
 
# 移动富媒体互动广告标准 (MRAID) 版本3.0
 
MRAID 版本 3.0 (MRAID 3.0) 具有重要的新功能, 可以提高用户的广告体验。新的 MRAID 使广告能够测量可见和可, 检测 MRAID 环境, 并获取位置数据以提供最佳的体验。此外, 还有当处于广告加载中的向导, 以便向用户展示广告。视频播放器的广告接口定义 (VPAID) MRAID 的附录现在已完全包含在 MRAID 规范中。
 
本 MRAID 归 iab科技实验室 (IAB Tech Lab) 移动富媒体互动广告标准(MRAID)工作小组版权所有。
 
## 关于iab科技实验室
 
实验室技术研究室是一个独立的、国际性的、研究和开发的联合体, 负责生产和帮助公司实施全球工业技术标准。由数字出版商和广告技术公司以及市场营销、机构和其他在互动营销领域有兴趣的公司组成, 实验室的技术实验的目标是减少与数字广告和市场营销相关的摩擦。供应链, 同时有助于安全和安全的产业增长。
 
本文件在实验室网站上:https://www.iab.com/mraid 
下列实验室成员公司参加了上述工作组: 

AccuWeather.com         	     DoubleVerify 	        Shazam 

AdColony 	                     Flashtalking 	        Sizmek 

Adform 	                         FOX Networks Group 	Taboola 

AdGear Technologies, Inc. 	     FreeWheel              The Media Trust Company 

Adobe 	                         Google 	            The New York Times Company 

Adsiduous Media 	             Gruuv Interactive 	    Thinknear by Telenav 

ADTECH 	                         Hulu 	                Time Inc. 

AdTheorent 	                     IAB 	                Tremor Video 

ADVR                             Improve Digital International B.V. Turner Broadcasting System

AerServ 	                     Innovid 	 	 

Alliance for Audited Media (AAM) Integral Ad Science 	Vdopia 

Amazon 	                         Leaf Group 	        Vertebrae 

AOL 	                         Liquidus 	            Verve 

BabyCenter 	                     LogoBar Enterprises 	ViralGains 

Bazaarvoice 	                 MGID 	                Visible Measures

Bonzai 	                         Microsoft Advertising 	Westwood One 

Cedato                           Technologies Ltd 	MoPub/ Twitter Inc. 	White Ops 

Celtra 	                         mPlatform 	            Yahoo 

Conversant Media 	             NinthDecimal 	        Yieldmo 

Cyber Communications Inc. 	     PadSquad 	            YuMe 

Digital Advertising Consortium Inc. Pixalate            Zynga  

Dominion Enterprises 	         RhythmOne 	             
 

# 目录
<pre> 
执行摘要	7
受众	7
1介绍	8
1.1定义	8
1.2范围	9
1.3 MRAID 如何工作	9
1.4 版本	10
1.4.1 更新 MRAID 3.0	11
2概述	12
2.1网络技术支持	12
2.1.1Ad 服务器	13
2.1.2广告渲染	13
2.2广告控制	13
2.3接口	14
2.4 脱机请求和度量	15
2.5 DAA 广告标记实现	16
3 初始化和设置	16
3.1初始化概述	16
3.1.1检查 MRAID Ad 是否已加载	17
3.1.2声明 MRAID 环境详细信息	17
3.1.3识别	19
3.1.4MRAID 事件的实施	20
3.1.5加载和显示间隙广告	24
3.1.6使用 iframe	24
3.1.7视区和默认容器设置	24
3.1.8用于初始显示的标准图像	25
3.1.9事件处理	25
4特点及操作	25
4.1可见	25
4.1.1轮询率和事件阈值	26
4.1.2实施注意事项	27
4.2用于显示的 Ad 控件	29
4.2.1广告状态以及它们是如何更改的	29
4.2.2检查屏幕和广告的位置和大小	30
4.2.3更改广告的大小	31
4.2.4open()、expand () 和resize()之间的差异	31
5MRAID 方法	34
5.1getVersion ()	34
5.2addEventListener ()	34
5.3removeEventListener ()	35
5.4open ()	35
5.5close ()	36
5.6unload ()	38
5.7useCustomClose () (已弃用)	38
5.8expand ()	39
5.9isViewable () (已弃用)	41
5.10playVideo ()	41
5.11resize ()	41
5.12storePicture ()	42
5.13 createCalendarEvent ()	43

5.14 VPAID 方法	44

5.14.1 initVpaid ()	44
5.14.2 vpaidObject.subscribe ()	44
5.14.3 vpaidObject.startAd ()	44
5.14.4 vpaidObject.unsubscribe ()	44
5.14.5 vpaidObject.getAdDuration ()	44
5.14.6 vpaidObject.getAdRemainingTime ()	45
6属性	46
6.1 支持	46
6.2 getPlacementType	47
6.3 get/set orientationProperties	47
6.4 getCurrentAppOrientation	49
6.5 getCurrentPosition	50
6.6 getDefaultPosition	50
6.7 getstate	51
6.8 get/set expandProperties	51
6.9 getMaxSize	53
6.10 getScreenSize	53
6.11get/set resizeProperties	54
6.12 getlocation	56
7 事件	57
7.1Error	57
7.2ready	58
7.3sizeChange	59
7.4stateChange	59
7.5exposureChange	60
7.6 audioVolumeChange	62
7.7 viewableChange (已弃用)	65
8 使用设备功能	65
8.1设备方向	65
8.2存储图片	66
8.3 日历事件	67
8.4 视频	68
9 VPAID 事件和方法	69
9.1MRAID 广告中的 VPAID 互动	69
9.1.1 在 MRAID 上下文中初始化 VPAID	70
9.1.2 发送和接收 VPAID 事件	71
9.1.3 如果不支持 VPAID	71
9.1.4 VPAID AdClickThru 事件	72
9.1.5 VPAID AdPaused, AdPlaying 事件	72
9.1.6 支持自动启动视频	72
9.2 点击行为与可见	73
9.3 计数印象	74
10术语词汇	75
11附录: W3C CalendarEvent 接口	77

</pre>

## 执行摘要

MRAID 是移动富媒体互动广告标准的缩写。它可以在广告和移动应用程序之间进行间接通信, 这样广告就能执行丰富的交互式体验。

如果没有 MRAID, 广告开发人员就必须专门为每个专有系统设计交互式广告, 以供其服务。这种开发的成本将会让品牌无法在移动应用中有效地做广告。 

MRAID 提供了一个调用库, 该广告可以用来与 MRAID 兼容的应用程序进行通信。随着越来越多的移动应用能够处理 MRAID 的广告, 广告开发者可以依靠更可预测的广告体验。 

MRAID 3.0 提供了更新, 以改善移动广告执行功能, 帮助跟踪可见, 提供清晰的初始化和广告准备, 并与实验室 VPAID (视频播放器广告界面定义) 的广告与互动视频, 以及其他增量升级。 

为了使用这些升级, 广告开发人员必须采用新功能来支持相关的广告功能, 应用程序开发人员必须升级他们的移动应用程序来支持这些新功能, 或者查看他们的 MRAID SDK 提供程序以进行更新。

随着手机使用的增加, 对高质量广告的需求也越来越大。买家希望改进跟踪, 而应用程序出版商希望改善广告体验。实施和/或升级到 MRAID 3.0 提供了支持改进跟踪和更好的性能更高质量的广告。

## 受众

MRAID 是一个协议, 广告设计者和广告开发商使用开发的广告能够与 MRAID 兼容的应用程序. 应用程序开发人员或他们的 SDK 提供者必须提供一个技术组件, 应用程序应该设置一个容器并且响应 MRAID。

虽然此规范为广告开发人员和应用程序发布商或其 SDK 提供商提供技术指导, 但在移动广告活动中工作的任何人都应该熟悉此文档。
 	 
## 1	介绍

MRAID 指定了一个 API, 它能够在丰富的广告交互体验和它所服务的本地移动应用程序之间进行交互。MRAID 实现的应用程序, 通常提供作为一个 SDK, 启动一个容器, 广告将显示和控制器, 广告使用的接口与应用程序容器。

MRAID 兼容的 ad 调用函数, 提供信息, 并根据此规范进行行为。MRAID 兼容的本机应用程序提供信息, 响应 MRAID 调用, 并按照本规范中的定义进行行为。 

### 1.1	定义

MRAID 涉及移动部分, 共同工作, 以产生互动的广告经验。为了清楚地表示这些移动部件, 以下关键字被定义为在本文档中使用。

主机:移动应用程序的组件, 提供空间 (容器) 来显示广告和广告可以通过 MRAID API 访问的服务 (控制器)。主机可以作为 SDK 实现, 也可以是应用程序的固有功能。

MRAID 实现:为广告提供 MRAID 功能的主机的功能。这包括 JavaScript 属性, 通过该特性, ad 可以检测到 MRAID 的存在、启用 MRAID 和调用 MRAID 服务。

sdk:软件开发工具包的缩写。在 MRAID 的情况下, SDK 指的是提供给移动应用程序发布者的实现代码和指令。

SDK 提供程序:在本文档中, SDK 提供程序是一个移动广告技术服务提供商, 它为移动应用程序发布者开发 MRAID 实现代码和指令。

广告容器:为 ad 显示保留的应用程序中的受限区域。应用程序发布者可能会在 app 内容 (内嵌) 内安排广告容器, 或保留容器以显示内容 (间隙)。应用程序中可能有多个容器可用。

web:移动操作系统的技术, 它显示 web 内容并执行 JavaScript。MRAID 不需要使用 web, 但在典型的 MRAID 主机中, ad 容器包含一个 web, 其中 ad 是 top-level 中的 web HTML 文档。

本机层:与本地应用程序有关的通信和操作的技术层。

特设:就本文档而言, 广告包括所有的创意、库引用、代码和其他文件, 包括任何 MRAID 功能, 用于在移动环境中显示 MRAID 广告。

### 1.2	范围

每个 MRAID 实现都为开发人员提供了独特的功能集。本文档说明了针对这些功能的设置、启动、功能、属性、事件和预期行为。但是, 某些操作细节被排除在外。此文档超出范围的功能示例包括:

●	从广告服务器、广告网络或本地资源检索广告

●	报告

●	IDE 集成

●	安全/隐私

●	国际化

●	错误报告

●	记录

●	计费和付款

●	广告维度与广告行为

●	将资源下载到本地文件系统以进行缓存或脱机使用
 
SDK 提供程序必须包括在面向广告单元的区域中呈现 web 内容的能力。对于大多数环境, 此功能已作为 web 提供, 但开发人员可能需要开发其他功能来支持这些规范。

MRAID 不限于本文档中描述的功能。鼓励开发人员进行创新, 并在市场中包含区分它们的功能。但是, 为了维护功能的互操作基线, 附加的功能集必须在MRAID 命名空间之外实现。为了支持功能, 可能需要了解额外的功能集和集成。

### 1.3	MRAID 如何工作

作为两个系统之间的协议, 每个系统都必须具备跟踪呼叫和响应期望的能力。在最简单的 MRAID, 两个系统涉及的是广告和移动应用程序。一个系统拨打对方的电话, 另一个则作出回应。然而, 广告和应用程序实际上并不直接沟通。 

移动广告活动服务 (供应商) 构建交互组件, 以尽量减少对移动应用程序开发人员的影响。Ad 技术专家是一个可以实现 MRAID 特定功能的个人或平台。广告技术专家还可以帮助广告设计者或广告开发人员使用 MRAID 来实现交互功能。广告设计者或广告开发人员会用所有预期的功能来制作广告, 而 ad 技术专家使用脚本将功能标准化以 MRAID 规范。供应商还可以为简化流程的技术设计提供一些建议。

同样, 在 app 方面, 一个供应商在一个简单的 JavaScript 标记启动的容器中开发组件进行交互。容器是可以使用标准化协议在类似浏览器的环境或 web 中进行通信的地方。该应用程序可以启动一个 "侦听器", 以便跟踪交互或响应广告发送的某些事件。 

下图说明了 MRAID 系统的工作部件。

![](http://oz3on0sof.bkt.clouddn.com/img.png)
  
### 1.4	版本

在 MRAID 中保持完全向后兼容是该项目的目标之一。在 MRAID 3.0 更新中, 工作组维持了2.0 版中确定的六项关键目标:
<pre>
●	高互操作性:在一个 MRAID 容器中开发的广告可以在多个平台和操作系统的 MRAID 容器上运行。
●	优雅退化: 利用所有 MRAID 功能开发的广告也有能力在需要时优雅地降级。这一点尤其重要, 因为 MRAID 继续在版本更新中包括设备访问。
●	渐进复杂性:使用 API 的广告设计应该简单, 只需在必要时添加复杂性。
●	用于广告操作的一致方法:MRAID 为广告提供了一个一致的沟通方式, 关于他们需要扩大和打开
应用程序的嵌入式浏览器 (如果嵌入式浏览器不存在, 则为浏览器)。
●	一致的退出控件:MRAID 广告将始终有一个一致的控制, 允许用户退出广告体验, 并返回到应用程序或内容。
●	出版商的灵活性:尽管 MRAID 兼容的 sdk 必须支持所有 MRAID 功能, 但 app 出版商或广告销售商可以自由允许或禁止使用 MRAID 启用的功能的广告。即, MRAID 支持丰富的媒体广告功能, 但并不意味着所有的富媒体广告的卖家都必须支撑所有这些功能。
</pre>

版本1.0

MRAID 版本1中包含的方法和事件为富媒体广告提供了最低级别的要求, 主要是显示可以在固定容器中更改大小的 HTML 广告 (例如, 从横幅扩展到更大/全屏大小) 和间隙广告。

版本2.0

MRAID 2.0 扩展了 MRAID 1.0 的功能, 使广告设计者能够更充分地控制可扩展的广告使用调整大小 ()方法.版本2.0 还提供了支持 ()功能作为一种标准的方式来查询设备有关某些功能。其他功能包括: 一致的视频创意处理, 添加到设备日历的条目, 并存储在设备照片卷的图像。

MRAID 视频附录

在2.0 版发布后, 工作组起草了一份增编, 以便在 MRAID 背景下利用实验室的视频播放器-广告界面定义 (VPAID)。视频附录提供了有关如何启动 VPAID 以及主机如何使用选择 VPAID 事件跟踪这些交互的指导。

#### 1.4.1	更新 MRAID 3.0
<pre>
MRAID 3.0 来与对文件的整顿, VPAID 附录的综合化到 MRAID 2.0, 可见变动和其他特点设计为增强富有的移动广告经验。MRAID 3.0 中的更新如下:
●	可见:可见的措施必须考虑到目前的 web 是否是有鉴于的因素。在 MRAID 3.0,isViewable ()已弃用, 但仍保留在此版本中以进行向后兼容性。相反, 建议包括使用exposureChange 事件以更好地传达广告的可见性。
●	MRAID 检测和初始化:以前的 MRAID 版本对于 ad 最初如何检测它是否在 MRAID 兼容的 web 中运行不明确。MRAID 3.0 中的更新介绍MRAID_ENV对象, 以便于在初始化时早期传递版本和其他相关属性。
●	修订的 MRAID 事件执行:此版本为主机与 ad 之间的状态正确通信以及事件序列的明确实现提供了指导。
●	可测量:一个新的事件, 用于检测是否可以听到音频和音量的变化。
●	位置:新添加到支持功能, 以指示是否启用了对位置的访问, 如果是, 则提供有关该位置的信息。
●	预加载和广告准备:以前版本的 MRAID 缺乏关于通告广告的资源是否已加载并准备好显示的指导, 有时会导致空白屏幕显示和用户体验不佳。MRAID 3.0 为主机提供指导, 如何检查广告准备前显示和如何预间质广告适当。 
●	卸载方法:介绍了一种新的方法在运行时异常的情况下为 ad 提供一个优美的退出机制。当 ad 不希望继续显示给用户时, 它使 ad 指示主机解除 web。
●	两部分广告弃用: 虽然两部分广告仍可使用, MRAID 2.0 的现有功能继续支持这些广告, 但添加到 MRAID 3.0 的新功能并没有设计为支持两部分广告。
●	VPAID 事件: MRAID 2.0 的增编为启动 VPAID 和报告某些事件提供了支持。MRAID 3.0 集成了此附录, 并为主机提供了可选的遵从性, 以支持使用 MRAID 和 VPAID 开发的广告。
●	useCustomClose ():此方法在 MRAID 3.0 中被否决。
</pre>

## 2	概述

MRAID 的目的是利用标准化的 web 技术, 在本机应用程序中使用。本概述提供了有关如何在 MRAID 操作中使用这些技术的背景信息。  

### 2.1	网络技术支持

对于互操作性, MRAID 只应使用与 web 兼容的语言来标记和编写脚本语言。虽然 MRAID 是代码不可知的, 但假设是使用了 HTML、JavaScript 和 CSS。广告设计者应该能够在 web 浏览器中开发和测试广告单元。如果设计器使用的标记、样式和函数仅与一个浏览器 (如 CSS3 在 WebKit 上) 兼容, 则该 ad 应针对兼容设备。

当较新的 web 标准在浏览器之间提供一致性时, 广告设计者会被鼓励使用它们。此类协议的示例可能包括 sms: 和电话: 

自 MRAID 2.0 出版以来, HTML5 已经发布, 应该尽可能多地使用。广告设计者应该意识到, 尽管一致性有所提高, 但预期的协议和实现在所有设备和平台上仍可能缺乏真正的互操作性。 

#### 2.1.1	广告 服务器

用于移动富媒体广告的广告服务器应该支持带有 JavaScript 的 HTML 广告。
 
#### 2.1.2	广告渲染

一个 MRAID 兼容的应用程序必须能够显示任何 HTML 广告。该过程涉及调用一个 HTML 文件, 其中包含用于启动用于执行 ads 的呈现引擎的 JavaScript 标记。在这个 HTML 文件中, 渲染引擎是 "web"。 

只要有可能, web 应包含设备 web 浏览器的功能。例如, iOS 开发人员可以使用WKWebView.移动应用程序可能会启动多个 webviews, 使它们彼此独立。一个广告可以建立在不同的 webviews 中的多个组件。 

### 2.2	广告控制
广告设计人员希望广告能利用 MRAID, 必须调用mraid. js在加载广告之前编写脚本 (请参见初始化的3节)。一旦调用, 广告容器就可以将 MRAID JavaScript 插入到广告文件中。 

主机然后保持在后台, 留下广告设计师控制广告显示。当广告需要与应用程序进行交互时, 主机可以用来处理交互。这种在广告和 MRAID 之间的交互可以对广告设计者或应用程序开发者几乎没有影响。

不使用任何设备功能的广告不需要使用 MRAID, 但是, 如果没有 MRAID, 主机将把广告作为一个简单的显示广告来处理。

广告可能利用 MRAID API 中的一些功能包括:
<pre>
●	打开嵌入式 web 浏览器
●	检测曝光变化和 ad 交互
●	将广告从横幅扩展到更大的尺寸
●	触发针对攻丝、震动、位置和其他用户参与活动的动作
</pre>

我们鼓励广告设计者依靠 MRAID 的能力来达到上述效果。即使是简单的显示广告也必须考虑使用 MRAID 来保持一致的超链接行为。

### 2.3	接口

广告 设计器可以访问以下方法、属性和事件:

方法	        |描述 
--------|------
getVersion 	|检查主机正在使用的 MRAID 实现的版本。
addEventListener 	|为指定事件注册侦听器
removeEventListener 	|移除指定事件的侦听器
open| 	广告指定要在新 web 中打开的 URL
close| 	广告调用来降级状态广告容器
useCustomClose	|在 MRAID 3.0 中已弃用。此方法调用将被 MRAID 3.0 兼容的主机忽略
unload 	|广告调用以解除或删除 web, 因为它无法加载或呈现资源。主机可以删除 web、替换为其他文档或用新的广告呼叫刷新
expand 	|广告请求容器扩展
isViewable(弃用)|	广告 查询主机关于广告容器的 on-screen 状态
playVideo 	|广告请求在本地播放器中播放视频
resizez 	|广告请求容器大小更改以适应新的广告大小
storePicture 	|广告 请求提示用户有关在设备上存储图片的信息
createCalendarEvent 	|向用户发送向设备日历中添加事件的 ad 请求提示
VPAID 方法 	|在 MRAID 环境下管理 VPAID 视频广告的方法集合<br>•	initVpaid<br>•	vpaidObject.subscribe<br>•	vpaidObject startAd<br>•	vpaidObject.unsubscribe <br>•	vpaidObject getAdDuration<br>•	vpaidObject getAdRemainingTime

属性 	| null
-----|-----
supports  |	广告 请求有关主机支持的功能的详细信息
getPlacementType 	|广告 请求确认内联或间隙放置
getOrientationProperties 	|广告请求细节关于风景或纵向方向
setOrientationProperties 	|广告 指定允许或锁定方向的首选项 (如果支持), 用于 广告 显示
getCurrentAppOrientation 	|广告 请求应用程序的当前方向
getCurrentPosition 	|广告 请求当前 广告 容器的坐标
getDefaultPosition 	|广告 请求的 广告 容器的默认坐标
getstate 	|广告 请求当前的 广告 容器状态: 加载、默认、扩展、调整大小、隐藏
getExpandProperties 	|广告 请求当前展开属性
setExpandProperties 	|广告 指定新的展开属性
getMaxSize 	|广告 请求最大 广告 容器尺寸可用
getScreenSize 	|广告 请求设备屏幕尺寸
getResizeProperties 	|广告 容器在其调整大小的状态下请求当前维度
setResizeProperties 	|广告 指定用于调整 广告 容器大小的维度
getlocation 	|广告 请求设备的当前坐标

事件 | null
-----|-----
error 	|主机报告错误
ready  	|主机显示 MRAID 库状况
sizeChange 	|主机报告 广告 容器维度已更改
stateChange 	|主机报告 广告 容器的状态已更改
exposureChange 	|主机报告 广告 容器暴露的百分比已更改
audioVolumeChange 	|主机报告音量的改变
viewableChange(弃用)	|主机报告 广告 容器可见的更改
 
### 2.4	脱机请求和度量

在设备没有网络连接的情况下工作的富媒体广告需要能够存储和稍后转发有关用户如何和何时与广告交互的指标。

MRAID 有可能与通用 api 集成, 以方便存储和转发诸如印象、视图和其他广告活动等广告指标;但是, 如何度量这些度量值或如何报告它们的详细信息超出了 MRAID 的范围。 

### 2.5	DAA 广告标记实现 

数字广告联盟 (DAA) 在数字广告中确立了用户隐私的原则。为了配合这些原则适用于移动环境, DAA 已经制定了实施指南, 其中涉及标记的放置, 它向用户提供有关广告的信息和选择退出的选项。 

的移动 DAA 广告标记实施指南 2014年4月被发布了。在移动环境中实施隐私原则于2015年9月1日开始。 

虽然没有添加到 MRAID 3.0 的更新, MRAID 始终有能力支持显示的图标覆盖, 并打开一个窗口, 可以为用户提供有关该广告的更多信息。广告开发商和移动供应商应审查基于兴趣的广告 (国际律师协会) 的移动广告的原则, 作为广告开发和交付战略的一部分。

## 3	初始化和设置

MRAID 在本机应用程序环境中支持复杂的广告交互。此交互要求宿主启动广告执行和显示的容器。以下各节描述了启动过程。

### 3.1	初始化概述

MRAID 控制广告和应用程序之间的互动使用 MRAID 实现, 启动一个容器的广告显示。广告设计者必须包含脚本mraid. js, 但浏览器实际上使用 web 提供 JavaScript 库。

web 必须确保将适当的 JavaScript 库尽快提供给 广告, 然后mraid. js参考。web 确认库已通过发送准备事件.

下面总结了 广告 和 MRAID 容器在初始加载 广告 时所采取的操作, 以及 MRAID API 库的注入 step####by 步骤。

1.	主机为 广告 执行建立 web。
2.	主机使MRAID_ENV在加载 广告 之前可用的对象, 以便 广告 可以识别 MRAID 的符合性。
3.	广告 通过在初始 广告 加载完成之前调用 MRAID 脚本标记来标识 MRAID 的遵从性。有关详细信息, 请参见3.1.1 节。
4.	(可选)主机检测 MRAID 脚本调用。
5.	主机为广告提供 MRAID 的 JavaScript 桥。
6.	主机提供受限的 MRAID 对象, MRAID 状态 = "加载" 和查询状态的能力。
7.	当 广告 使用 createElement mraid. js 时, 广告 必须等待 mraid 在访问 mraid 对象之前完成加载。广告是必要的, 以确保mraid. js可用。广告 必须使用就绪事件来确定完整的mraid. js可用.
8.	广告检查mraid的*mraid.getState()==’loading’*, 如果为真, 则广告侦听 ready 事件通过使用 mraid广告 *mraid.addEventListener('ready')*
9.	主机将 MRAID 库加载到 web 中
a.	将 MRAID 状态更改为 "默认" 并发送stateChange事件.
b.	点燃 MRAID准备事件.
10.	广告 的事件侦听器捕获就绪事件, 并可根据需要访问 MRAID 功能。

#### 3.1.1	检查 MRAID 广告是否已加载

当分析包含广告的 web 中的文档并且其所有子资源(包括广告资源) 已完成加载时, 该广告被视为已加载。当时,*document.readyState*被设置为*complete*并且*load*事件挂载在窗口对象.

此检查可能不需要所有类型的广告, 例如小尺寸横幅广告可能不需要这个。但必须对所有大型广告进行检查, 例如位或广告, 要求在渲染之前加载大量资源。
主机可以检测到 web 及其所有组件 (包括所有广告资源) 是否已通过以下检查完全加载:

●	在 Android 上, 使用*onPageFinished()*处理

●	在 iOS * 检查 web 内的文件, 通过轮询*document.readyState*被设置为*complete*并且*load*事件挂载在窗口对象.
 
在 iOS 中, 主机还可以使用*webViewDidFinishLoad()*, 但此事件有时可能过早触发。*document.readyState*还必须检查以验证 iOS 上的广告负载。
当没有广告加载的时候, 不论什么原因,广告必须告诉SDK没有广告存在。此操作必须使用*mraid.unload()*方法

#### 3.1.2	声明 MRAID 环境详细信息 

在以前版本的 MRAID 中, 给出了广告的指导, 以确定MRAID 广告 (使用mraid. js) 尽快, 但该广告无法访问的信息, 它将加载的容器。在 ad 供应商提供 MRAID 版本和非 MRAID 版本的情况下, ad 服务器需要收集有关环境的详细信息, 这样它就不会浪费宝贵的资源来尝试调用mraid. js对于一个不能支持它的环境。

MRAID 3.0 ad 容器提供了一个 MRAID_ENV 对象, 它使 ad 能够验证该容器是否与其他有关环境的信息 MRAID 兼容, 如 MRAID 版本、SDK 版本以及广告需要操作的其他关键细节有效.即使 ad 不请求通过加载 MRAID. js 脚本访问 MRAID, 也可以使用 MRAID_ENV 对象。

MRAID_ENV 对象声明有关 MRAID 环境和 SDK 容器的特定信息, 并使这些信息在加载后立即可供创作。广告可以使用这些细节来提供更好的用户体验和改进分析。 

下面的脚本是 MRAID_ENV 可能的样子的示例:

``` js
<script> window.MRAID_ENV = {  version: '3.0',  sdk: 'SDK Name',  sdkVersion: '1.0.0',  appId: 'com.iab.myapp',  ifa: '01234567-89ab-cdef-0123-456789abcdef',  limitAdTracking: true,  coppa: false 
</script>
```
MRAID_ENV 属性:

当请求时, 宿主向 ad 提供的 MRAID_ENV 对象中使用了以下属性。

属性	|描述
-----|-----
版本*	|(string)此 SDK 实现的 MRAID 规范的版本。它必须等于 mraid 接口的 getVersion 方法返回的相同值。
sdk*	|(string)运行此 web 的 SDK 的名称。
sdkVersion*	|(string)SDK 版本字符串。如果没有可用的版本, 字符串可能会留空。
appid	|(string)运行此广告的应用程序的包名或应用程序 ID。通常称为appid 
ifa	|(string)用于广告目的的用户标识符。对于 iOS, 这必须是广告的标识 (IDFA)。为Android, 这必须是谷歌广告 ID (AID)。
limitAdTracking	|(布尔值，必须引入在如果设置了IFA的广告)如果启用了限制广告跟踪, 则为 true, 否则为 False
coppa 	|(布尔值，必须引入在用于儿童的广告)若为真就是面向儿童,否则不是
* 必须的

为便于实现, 可以从对象中完全省略未使用的可选字段, 或提供默认值 (字符串类型为空字符串, 0 用于数字类型)。

可选字段必须设为默认值或未设置, 并且必须提供从应用程序出版商明确选择.这个选择可能是全球的应用程序, 或在印象的基础上 (例如, 如果出版商支持直销和匿名库存)。

在有两部分广告的情况下, 主机只使 MRAID_ENV 对象可用于初始广告。第二部分的2部分广告必须使用的广告收到的第一部分, 如果第二部分需要这些细节。

#### 3.1.3	识别

为了利用 MRAID, 广告必须要求mraid. js在加载 HTML ad 时编写脚本, 如第3.1.1 节所述。

请求mraid. js可以通过以下三种方式之一完成:

<pre>
●	使用标记<script src="mraid.js"></script>在 HTML 的创意。
●	使用文档. 写入 ()脚本标签, 从 JavaScript 代码放在创造性。
●	使用 DOM 元素插入脚本标签从 JavaScript 代码放置在创造性。
</pre>

在上述情况下, 可以使用 JavaScript 代码动态注入脚本标记。必须在 ad 加载完成之前注入脚本标记。有关 ad 加载详细信息, 请参见3.1.1 节。 
MRAID 示例广告演示了脚本标记的位置。看到www.iab.com/mraid 用于 MRAID 实现的资源。

广告设计者必须避免使用字符串mraid.js除识别 MRAID 的用途以外的任何目的。使用mraid. js不止一次可能导致多个 MRAID 库的注入, 从而有助于文件大小和降低广告性能。
 
 
下图说明了时间间隔。mraid. js可能要求:

![](http://oz3on0sof.bkt.clouddn.com/tu.jpg)
1.	主机应用程序将广告加载到一个广告容器中。
2.	在 广告容器中, 宿主在页中执行并同步加载 JavaScript 以及任何其他页资源。
3.	广告必须调用mraid. js在广告容器完全加载好之前。
4.	应该监听*window.load()*来查看容器加载是否完成 
确认容器装载已完成
 
 
非 MRAID 的广告应该能够在 MRAID 的 web 中使用或不调用mraid. js.简单 ad 可能使用 MRAID 的一个原因是为超链接交互提供一致的行为。使用 MRAID 时, 所有超链接都必须使用*mraid.open()*.

####3.1.4	MRAID 事件的实施

在 MRAID 中, 用户交互可以触发一系列事件的发生。为了减轻广告创作的负担, MRAID 3.0 规定, 由于用户交互或创造性行动, 这些链式事件将在容器操作之后被触发。 
 
通常, 容器必须在发送任何事件之前执行所有所需的容器大小更改或值更改。这使得广告只需要观看单个事件, 而不是观看多个事件。 
 
例如, 在可扩展广告的情况下, 广告需要stateChange,exposureChange, 并有sizeChange执行扩展的创造性执行的事件. 在以前版本的 MRAID 中, 一个刚搞被强制不仅检查状态是否已更改为 "扩展", 而且还需要检查容器大小是否实际更改了 sizeChange 事件.
 
在 MRAID 3.0 中, 容器必须执行所有需要的更改, 然后触发链式事件。在可扩展的示例中, 事件stateChange, exposureChange和sizeChange都将火。这使得广告只需要观看的事件, 它的期望和需要, 即stateChange事件。

本节更详细地说明了可膨胀和间隙的例子。 
 
## 可扩展广告 

在 MRAID 的典型用例中, 广告以横幅开始, 并在用户启动时扩展到全屏体验。

![](http://oz3on0sof.bkt.clouddn.com/aaa%E3%80%81.png)

当用户点击广告时, 广告使用 MRAID javascript 层请求扩展, 通过调用*mraid.expand()*。MRAID 呼叫请求广告扩展。

容器通知应用程序该广告正在扩展, 以便它可以阻止任何阻止用户交互的内容。然后, 容器调整大小, web 在右上角为关闭事件区域保留一个空间, 并添加一个 "关闭" 按钮。 

当用户点击关闭按钮或广告调用*mraid.close()*,该广告调整其原来的大小和容器通知应用程序, 它可能会恢复正常功能。

exposureChange事件通常会触发, 但如果广告从未注册过侦听器, 则 SDK 可能选择不激发该事件以节省计算资源。
 
 	  
### 间隙广告

间隙广告的操作非常像可扩展的广告, 除了在关闭功能被敲击后调整大小以外, 一个间隙的广告状态被更改为 "隐藏"。由于未再次调用广告, 因此任何已注册的事件侦听器都未注册。
  
 
#### 3.1.5	加载和显示间隙广告
有时, 在所有的资源都被完全加载之前, 一个间隙的广告会显示给用户。结果是部分加载或空白广告。在这种情况下, 用户体验不佳可能会导致用户在其呈现之前忽略该广告。为了防止显示部分加载的广告, 主机必须等待广告完全加载, 然后才能开始显示。 

广告必须加载在一个 web, 是关闭屏幕或隐藏, 直到所有资源加载。请参阅第3.1.1 节以确定何时加载广告。

主机必须在同一 web 中加载和显示间隙广告。主机不能将广告加载到临时 web 中, 然后在新的 on-screen web 中再次加载它以显示它。这样做将导致广告被重新加载, 这可能导致 over-counting 的广告请求和像素跟踪, 并可能导致额外的每广告服务成本的动态广告.

#### 3.1.6	使用 iframe 

由于有可能使用多个平台来服务于广告, 有时 MRAID 广告是一个在 iframe 中服务另一个 MRAID 广告的容器。结果是一系列嵌套的 iframe, 可能在广告交付之前生成。 

当 MRAID 广告包含在嵌套的 iframe 中时, 访问本机 MRAID 实现在技术上是困难的或不可能的。MRAID 不能直接支持嵌套 iframe 中的广告。如果 ad 希望嵌套 iframe 访问 MRAID 功能, 则 ad 的最外层的帧将需要提供自己的机制, 以便通过嵌套的 iframe 访问 MRAID。 

在嵌套 iframe 中工作的解决方案超出了 MRAID 规范的范围。

#### 3.1.7	视区和默认容器设置

MRAID 广告 需要知道为 广告 执行设置的容器的默认设置, 并且能够覆盖默认设置以适合适当的 广告 执行。为了了解容器的默认设置, 广告 可以像查询网页一样查询容器。MRAID 的默认设置包括: 容器的宽度和高度、缩放以及用户是否可以缩放容器。

虽然 MRAID 不在容器上建立任何新的参数或控制, 但广告必须根据需要检查和调整初始显示的参数。
 	 
#### 3.1.8	用于初始显示的标准图像

广告设计者负责提供一个标准的图像用于初始显示。可以使用以下方法提供对此初始资源的访问<img>标记, 在后台加载其他资源时将显示该标签。一旦所有额外的资源准备就绪, 广告中的任何交互式元素都可以取代简单的图像。

#### 3.1.9	事件处理

事件处理是 MRAID 功能的关键。在 web 层和本机层之间进行通信本质上是异步的。通过事件处理, ad 能够侦听特定事件并根据需要响应这些事件。MRAID 提倡广播式的活动, 以最大的一致性支持最广泛的功能和灵活性。

### 4	特点及操作

MRAID 为移动中的广告提供了丰富的媒体交互, 允许扩展、调整大小和丰富的度量跟踪等功能。为了使 MRAID 所提供的所有服务都能顺利运行, 开发人员必须了解广告 和应用程序中的每个交互和预期响应的操作顺序。 

本节介绍这些功能及其操作的详细信息。3节介绍了初始化和设置。5-7 节详细介绍了特定方法、属性和事件。有关在本机级别使用设备功能 (如创建日历事件和存储图片) 的详细信息, 请在8节中介绍。与实验室 VPAID 在本地视频播放器中进行操作和跟踪的集成包括在9节中。

#### 4.1	可见性

在 web 浏览器中显示 广告 时, 广告 中的 JavaScript 代码将检查 DOM 层次结构的属性, 并收集几何度量以确定 广告 的可见。但是, 该技术对于在本机应用程序容器中显示的广告不起作用。JavaScript 代码无法确定相对于本机 UI 的度量, 这在计算 web 是否对用户可见时是必需的。

可见的一个更完整的报告包括监视在接触中的变化, 以及查看用户交互。而不是跟踪可见的活动 web, MRAID 3.0 引入exposureChange事件.有关使用此事件的详细信息, 请参阅7.5 节。
 
MRAID 3.0 可见相关更改的更新遵循以下原则:
<pre>
●	性能:最小化测量对 end-user 体验的影响, 包括动画平滑度和电池寿命。
●	最小的影响:只做额外的需要, 以提供更好的洞察容器可见, 仅此而已。
●	经得起未来考验的:避免指定显式阈值以支持即将到来的度量标准并提供最大的创造性灵活性。
●	向后兼容:当前 MRAID 兼容的容器必须保持兼容, 即不应重新定义现有 api 的含义。
</pre>

可见是一种度量, 它确定广告是否处于用户有机会在其设备上查看广告的位置。

在 2016年, 媒体评级委员会发布了测量移动广告可见的指南。这些准则 应用于在移动 web 和移动应用程序体验中开发跟踪可视广告印象的策略。
使用 MRAID 3.0 事件的指南exposureChange与湄公河公司的移动广告测量准则一致。

isViewable ()方法和viewableChange事件在 MRAID 3.0 中被弃用。为了向后兼容, 这些功能保留在此版本中。 

#### 4.1.1	轮询率和事件阈值

符合更新原则的维护性能, 事件处理exposureChangeMRAID 3.0 中的事件不能干扰平滑的 UI 动画或降低电池寿命。

主机平台上的 MRAID 3.0 实现必须联合更新, 以避免对 JavaScript 进行过多的消息传递。合并的更新必须报告exposureChange事件不迟于200ms 后的广告暴露面积的变化。在使用轮询时, 必须经常查看视图层次结构以捕捉曝光的更改。轮询必须每秒至少发生5次 (每200毫秒)。
 	 
### 示例用法 

下面的过程表示符合的执行exposureChange事件:

1.	ad 容器注册一个侦听器。exposureChange事件.
例如:```mraid addEventListener ("exposureChange", handleExposureChange); ```
2.	exposureChange事件调用 广告的事件处理程序, 并将容器矩形与广告创意的大小进行比较。 例如:

``` js
function handleExposureChange(exposedPercentage, visibleRectangle, occlusionRectangles 
) { if (exposedPercentage >= 50.0) { 
// log visible time ... 
} 
} 
```

3.	当 广告已被取样足够长, 且可见区域达到可见阈值时, 广告必须被视为可查看。如果不需要进一步的测量, 请删除exposureChange侦听.
例如:```mraid removeEventListener ("exposureChange", handleExposureChange); ```

#### 4.1.2	实施注意事项

用户和应用程序开发人员希望他们的应用程序具有最佳性能。广告测量不应降低应用程序的操作. 可见的 MRAID 实现必须考虑以下因素:

### 避免耗时的 JavaScript 工作 

带有 webviews 的应用程序显示 ads 在两个处理器线程上运行: 一个线程用于本机 UI, 另一个线程用于 web 中的 JavaScript。在本机线程等待时避免耗时的 JavaScript 工作。  
 	 
例如, iOS WKWebview 使用的是目标-c 方法:
 
*evaluateJavaScript: completionHandler*

此方法不具有阻止 UI 线程的副作用。这是建议使用, 而不是 web。 
 
### 使用低 api 

本机平台包含的 api 提供了影响可见的 UI 更改的低通知。MRAID 的新实现exposureChange事件必须使用此类通知, 尤其是在低轮询率或补偿生效时。此类事件的一个示例是使用ViewTreeObserver安卓事件。

### 防止阻塞操作 

不要对 OS 应用程序生命周期回调执行阻塞操作。

在 iOS 上, 这些包括以下内容UIApplicationDelegate方法:
<pre>
●	applicationWillResignActive 
●	applicationDidEnterBackground 
●	applicationWillEnterForeground 
●	applicationDidBecomeActive 
</pre>

相应NSNotificationCenter事件还会添加到阻塞操作中。

在 Android 上, 拦截操作包括以下活动方法:
<pre>
●	onPause 
●	onstop 
●	onstartonResume 
 </pre>

操作系统将终止在几秒钟内从调用这些方法返回的应用程序。

排队事件而不阻止本机操作 

有时, 一个广告的 JavaScript 可以是越野车甚至是恶意的。当代码执行时间过长时, 可能会延迟或阻止后续事件。MRAID 实现必须避免在 enqueueing 事件时阻止本机线程。无论是在本机线程中还是在 web 中, 排队事件都必须在以前的 MRAID 事件侦听器返回时传递。

### 4.2	用于显示的广告控件

除了初始显示, 广告设计者可能有许多原因来控制显示。
<pre>
●	应用程序可以在后台加载视图, 以帮助解决延迟问题, 以便请求 广告, 但对用户不可见。
●	广告 可能会超出应用程序内容的默认大小而扩展。
●	一旦用户交互完成, 广告 可能返回到默认大小。
</pre>
部分4.2.1 到4.2.4 解释的控制可用的广告高级广告显示, 如扩展广告和位。

#### 4.2.1	广告 状态以及它们是如何更改的

用于执行 广告 的每个 web 都具有以下状态之一:
<pre>
●	加载:web 尚未准备好与 MRAID 实现的交互
●	默认:应用程序和 SDK 所放置的 广告 容器的初始位置和大小
●	扩大:广告 容器已扩展以覆盖视图层次结构顶部的应用程序内容
●	调整:广告 容器已更改大小, 使用调整大小 ()方法
●	隐藏:间隙性广告关闭时的状态。如果支持, 则在关闭时也可能隐藏横幅广告 
</pre>

调用时更改 web 状态: expand(), resize(),close()和 unload()..下表概述了调用这些方法的效果。

初始状态|	 expand()| resize()|close()|unload()
-----|-----|-----|-----|-----
加载	|无更改	|无更改	|无更改	|不适用 *
默认 (横幅)	|状态更改为"扩大"	|状态更改为"调整"	|状态更改为"隐藏"(如果支持)	|不适用
默认值 (interstitia)	|无更改	|无更改	|状态更改为 "隐藏"	|不适用
扩大	|无更改(状态保持 "扩大")|	触发错误,状态仍然 "扩大"	|状态更改为"默认"	|不适用
调整	|状态更改为"扩大"	|状态保持为 "调整大小", 但具有更新的值	|状态更改为”默认"	|不适用
隐藏	|无更改	|无更改	|无更改	|不适用

* 不适用, 因为卸载 ()方法在不希望向用户显示 ad 时使用。在这种情况下, 主机可以解除或删除 web, 用另一个文档替换它, 或者用另一个广告刷新它.
带有两部分扩展和广告的广告, 位流的状态改变路径略有不同:

### 两部分可扩展广告 

两部分可扩展广告使用两个不同的 webviews, 其中广告组件可以彼此独立扩展。由于 MRAID 广告一次只带一个状态, 只要在屏幕上扩展视图, 两部分可扩展的广告就会进行扩展。 

新的扩展 web 从 "加载" 状态开始, 直到 MRAID 可用。当 "就绪" 事件被激发时, ad 的状态将转换为 "展开"。横幅, 两部分广告的第一部分也改变了它的状态, 从 "默认" 到 "扩展"。

### 间隙广告 

对于间隙广告, web 从 "加载" 到 "缺省", 当间隙闭合时, 状态变为 "隐藏"。

getState ()方法报告上次发送的当前状态。stateChange事件.这些功能分别在6.7 和7.4 节中作了进一步说明。

#### 4.2.2	检查屏幕和广告的位置和大小

MRAID 包括几种方法, 使广告能够检查它的位置和大小, 以及它可以扩展到的最大值。 广告设计者可以使用这些功能为他们的广告增加灵活性, 使其在不同的设备和/或大小不一的屏幕上表现不同。

有关详细信息, 请参见以下各节:
<pre>
●	6.5 getCurrentPosition
●	6.6 getDefaultPosition
●	6.10 getScreenSize
●	6.9 getMaxSize
●	7.3 sizeChange
</pre>

#### 4.2.3	更改广告的大小

MRAID v2 包含三种不同的方法来更改广告的大小:open(), expand(), 或 resize(). 

大小更改的最简单方法是使用open()方法.为了打开超链接, 此方法还可以打开一个新的 web 以不同的大小显示广告的新组件。这种格式的广告称为两部分可扩展广告。

expand()方法用于以相当简单、直接的方式来扩展广告, 它涵盖了应用程序的内容。

resize()方法用于在应用程序操作的对话中以更微妙的方式增长或缩小的广告。该方法为设计者提供了更多的自由度和控制;但是, 广告和应用程序或 web 需要额外的方法和侦听器, 以便在不同的位置做出适当的反应。

#### 4.2.4	open(), expand(), 和resize()之间的差异

虽然这些方法是相关的, 但它们促进了渐进复杂性的方法。区分open(), expand()和resize()帮助广告设计者选择最佳的方法来满足他们的需求。

所有这些方法必须是用户启动的基于实验室新的广告组合定义。用户启动被定义为离散用户操作, 例如单击或点击。 

广告必须确保只有在用户启动时才调用这些方法。广告不能在没有用户操作的情况下启动这些请求。
<pre>
open () 
●	最低公分母
●	用于广告客户登陆页面或微
●	在设备的默认浏览器中打开一个新的 url
●	始终全屏
●	无其他属性
expand () 
●	简单界面
●	维护广告体验
●	全屏
●	少量附加属性
●	支持单部分或两部分的创意
●	MRAID-在固定 (右上) 位置执行 tap-to-close 区域
●	创造性的相对对齐
●	扩展前检查屏幕大小 (getScreenSize)
 
resize () 
●	灵活的界面
●	持续、非的广告体验
●	没有默认值, 可以更改为较大或更小的大小
●	所需的其他属性和方法
●	单部分创意
●	MRAID 强制 tap-to-close 区域, 但广告设计师可以改变禁区的位置在创意区。
●	绝对定位可能
●	支持调整大小的方向
●	检查允许的最大大小 (getMaxSize), 然后再调整大小
●	主机不得拒绝调整大小 ()来自广告的请求
 
</pre>
 
下表总结了这些方法之间的主要差异。

属性	|open () 	|expand () |	resize () 
-----|-----|-----|-----
模式	|Y|	Y	|N
MRAID-强制关闭控制	|N	|Y|	Y
查看器停留在广告体验中	|N|	Y|	Y
两部分创意	|n/a|	Y|	N
单部分创意	|n/a|	Y|	Y
与屏幕对齐	|n/a|	Y|	N
为小创意提供背景	|n/a|	Y|	N
大小	|n/a|	Y|	Y
缩小	|n/a|	N|	Y
应用程序定义的最大面积	|n/a	|N|	Y
完成所需的回调	|n/a	|N|	Y
支持方向性	|n/a	|N|	Y
创意可以控制调整广告的位置	|n/a|	N	|Y
应用程序可以返回到默认状态	|n/a|	N	|Y
 
当扩展的创意小于全屏时, 调用expand() 会导致 web 空白、覆盖或以其他方式掩盖底层应用程序, 这使得扩展的 ad 在本质上是模态的。模式, 部分屏幕扩展不允许在 MRAID, 但部分屏幕, 非扩展可以创建使用resize()方法.

 null|	模式| 	模式 
-----|-----|-----
全屏	|确定-使用expand()|	不可能 
部分屏幕	|不可能 |	确定-使用resize()
 
 	  
## 5	MRAID 方法

MRAID 方法启动一个函数, 通常与广告操作有关, 需要对广告容器进行一些调整或传递信息。例如, 调用expand()提示 SDK 停止应用程序操作并展开广告容器。某些方法包括检查或更新属性 (6 节) 和使用事件 (第7节) 来报告或确认某些操作。

### 5.1	getVersion ()

广告称getVersion ()方法来查询主机支持的 MRAID 版本。主机返回一个版本号字符串 ("3.0" 用于 MRAID 3.0)。 版本号指示主机支持的 MRAID 版本 (1.0、2.0 或3.0 等), 而不是供应商的 SDK 版本。

语法	|*getVersion ()*
-----|-----
参数	|没有
返回值	|一个字符串, 指示 sdk 兼容的 MRAID 版本 (而不是 sdk 的版本)。例如, 如果 SDK 的5.2 版本符合 MRAID 3.0, 则getVersion ()返回"3.0"。
相关事件	|没有
 
注意: MRAID 和 SDK 版本是在3.1.1 节中讨论的 MRAID_ENV 对象中提供的。

### 5.2	addEventListener ()

广告电话addEventListener ()为特定事件注册特定侦听器。ad 可能会注册多个侦听器, 每一个都支持侦听单独的事件。主机为发生的每个特定事件分派一个事件到所有已注册的侦听器。ad 还可以将单个侦听器注册到多个事件, 而不是每个事件的侦听器。
<pre>
MRAID 3.0 中支持的事件有:
●	准备:报表初始化完成
●	错误:发生报告错误
●	stateChange:报告状态更改
●	exposureChange:报告更改曝光
viewableChange (已弃用):报告可查看的更改
sizeChange:报告可查看的更改
</pre>

语法	|addEventListener (事件、侦听器) 
-----|-----
参数	|事件: 要侦听监听器的事件名称的字符串: 要执行的函数
返回值	|没有
相关事件	|没有
 
### 5.3	removeEventListener ()

当广告不再需要特定事件的通知时,removeEventListener ()用于注销到该事件。为了避免出现错误, 事件侦听器在不再需要时必须始终被移除。如果中未指定侦听器函数, 则在侦听属性进行调用, 则将删除侦听该事件的所有函数。

语法	|removeEventListener (事件、侦听器) 
-----|-----
参数	|事件: 要移除侦听器的事件的名称的字符串: 要删除的函数
返回值	|没有
相关事件	|没有
 
### 5.4	open()

广告可以调用open()方法来提示主机在浏览器窗口中打开一个外部移动网站, 它是用户设备上的默认浏览器此方法的目的是处理广告中的点击率。所有 MRAID 广告必须处理点击率使用open()方法.
	
一般执行说明 | open ()方法必须仅用于非 MRAID 广告的外部网页。由于调用而导致的显示页open()无法加载 MRAID 实现的第二个实例, 这意味着close()方法在打开的浏览器中无法操作。打开的窗口只能使用在打开的浏览器中实现的任何关闭控件来关闭。
 
本机浏览器控件 (后退、前进、刷新和关闭) 总是出现在打开的窗口中。SDK 提供程序考虑open()作为可报告事件的函数。

语法	|打开 (URL) 
-----|-----
参数	|url: 要打开的网页的 url 的字符串
返回值	|没有
相关事件	|没有
 
### 链接

当用户单击 HTML 超链接时 (由<a href="””"></a>tag) 在一个 MRAID 的广告中, 有两种可能性: 链接的页面可以在现有的 web 中加载, 或者内容可以打开一个单独的浏览器窗口, 并加载指定的 HTML 链接。

open() 方法必须始终使用本机设备或 OS 行为或用户设置来打开 MRAID广告中的 URL。这将确保用户期望并启用必要的设备控制的经验, 用户需要导航到外部链接并远离它们。

### 5.5	close()

广告使用close()把集装箱的状态降级主机通过根据当前状态更改状态来响应。stateChange7.4 节中描述的事件。

对于扩展或调整大小的状态的广告,close()方法将广告移动到默认状态。对于在默认状态下的间隙广告,close()方法移动到隐藏状态。这些广告状态和状态, 结果从调用close()在第4.2.1 节中描述。

对于处于默认状态的广告, 广告开发人员必须避免使用mraid.close().若要通知容器该广告需要被撤销, 请使用mraid.unload()。 
 
如果广告使用多个resize()调用或resize(),其次是expand(),close()将容器状态返回为 "默认值"。调用close()在这些情况下, 不只是撤消最近调用的resize()或expand().
 
语法	|close() 
-----|-----
参数	|没有
返回值	|没有
相关事件	|StateChange (7.4 节)
 
### 调整大小的广告的关闭控制

与可扩展的广告一样, 调整大小的广告必须有一种方式让观看广告的人将广告返回到其默认状态。MRAID 将两个方面区分为 "关闭" 功能:
<pre>
●	关闭事件区域: 关闭事件区域 是广告创意上的一个领域, 用户可以点击该区域来关闭广告或将其折叠回默认状态。主机为所有 MRAID 大小的广告提供了在一个创造性指定的位置所需的关闭事件区域。
●	关闭指示器: 关闭指示器是标识用户的关闭事件区域的可视提示。对于调整大小的广告, 广告提供了一个关闭的指示器图形, 而主机为关闭事件区域。
</pre>

主机必须始终包括50x50 密度独立的像素关闭事件区域。建议的位置是为广告提供的容器的右上角。当用户点击此指示器时, ad 将返回到其默认状态。 建议的格式是关闭指示器的 "X" 按钮。

useCustomClose ()方法被弃用, 并且广告不能提供自己的自定义关闭指示器。关闭指示器始终由主机提供。这确保了在应用程序中扩展或调整大小的广告的一致体验。

主机也可以决定遵循本机应用程序的经验来关闭或驳回广告。这可能是为了保留在特定应用程序中导航内容的本地用户体验, 例如, 在某些应用程序中, 通过使用全屏内容或在广告的左侧或右侧敲击来完成内容导航。同样的行为也可能用于在内容之间显示的广告。这不适用于可扩展广告或调整广告的大小。他们必须有主机提供密切的指标。

对于 MRAID 2.0 或更旧版本的广告在 MRAID 3.0 集装箱,useCustomClose ()请求将被主机忽略

调整大小的广告必须定位, 使整个关闭事件区域显示在屏幕上。 如果主机检测到大小调整将导致关闭事件区域处于关闭状态, 则主机必须返回一个错误并忽略调整大小的调用, 从而使 广告处于其当前状况。这一要求还意味着, 调整大小的广告必须至少50x50 密度独立的像素, 以确保关闭事件区域的调整大小的创意空间。

关闭控制是强制性的, 由主机在所有情况下提供。

在 Android 操作系统上, "后退" 按钮的用户操作必须被广告解释为 close 方法。

### 5.6	unload ()
此方法的主要目的是允许 广告与宿主通信, 该 广告必须不再显示给用户。广告可以要求主机完全驳回广告使用unload()方法.主机通过取消广告, 然后删除 web 或者用另一个文档替换它, 或者用一个新的广告来刷新它。

广告在其生命周期中任何时候都可以使用此方法, 因为它决定它不再希望继续显示给用户, 并且不需要返回到默认状态。

在遇到错误或运行时异常时, 广告应使用此方法, 这样将不允许它正确地呈现给用户。一些例子的情况下, 广告可能会决定使用unload()方法:
<pre>
•	在初始化过程中, 它可能会遇到与 广告服务器的通信错误, 或者无法正确加载所有必需的资源, 或者它决定不希望在所服务的环境中显示它
•	在生命周期的后期阶段, 它可能会在加载所需的资源或资源时遇到错误, 并确定它不想继续显示给用户
•	预先加载的广告可能会决定它不希望显示给用户。
</pre>
语法	|unload() 
-----|-----
参数	|没有
返回值	|没有
相关事件	|StateChange (7.4 节)
 
unload()为 ad 和主机提供优美的退出机制, 而不会在屏幕上或显示给用户的空白屏幕上造成错误。

### 5.7	useCustomClose () (已弃用)

此方法在 MRAID 3.0 中被弃用
 
### 5.8	expand()

广告使用expand()请求对广告扩展体验的支持, 要么通过改变当前 web 的宽度和高度 (一个部分的创造性), 要么通过在扩展大小的最高层打开一个新的 web (两部分的创意)。如果指定了 URL, 扩展视图可以包含新的 HTML 文档, 也可以重用默认位置的同一文档。 

此选项使广告设计者可以提供可扩展的广告作为一个 onepart 广告 (横幅和面板作为一个创意) 或两部分广告 (横幅和面板是单独的 HTML 创意)。

### 单部分创意 (未指定 URL)

当广告调用expand()在不指定 URL 的情况下, 主机在现有的 web 中展开。这种方法简化了广告设计和报告, 因为最初的创意是不重新加载和没有额外的印象记录。 

### 两部分的创意 (指定的 URL)

当广告调用expand()通过指定的 URL, 主机将打开一个新的 web。提供的 URL 必须是完整的 HTML 页面, 而不是片段或片段。如果第二部分的广告创意需要使用 MRAID, 广告必须要求 MRAID. js 为新的 web。无论扩展部分的 ad 请求是否 mraid, 主机都必须提供 close 事件区域。如果 ad 指定一个关闭指示器图形

expandProperties, 则主机将使用所提供的图形指示关闭。否则, 宿主还会提供关闭指示器图形。

虽然广告处于展开状态, 但默认位置对查看器是模糊的或不可访问的, 因此在扩展状态可用时, 默认位置必须不执行任何操作

### 主机响应

主机响应expand()通过将状态从 "默认" 更改为 "扩展" 使用stateChange7.4 节中描述的事件。主机忽略多个调用以展开和保留 "展开" 的状态状态。
即使扩展的创意可能小于屏幕区域, 主机也会扩展容器以覆盖所有可用的屏幕区域。广告容器中没有填充广告创意的任何区域都可能是透明或不透明的。扩展的广告总是模式化的, 容器必须防止新广告在扩展状态下加载。 

### 潜在问题

扩展的广告可能涉及多个窗口对象, 以防止在展开的状态下操作, 或更改内容 z 顺序 (层位置) 的计时器。这些复杂的应用程序环境可能会干扰用户关闭 ad 的能力。SDK 开发人员必须考虑这些复杂性, 并针对特定的 MRAID 实现进行相应的调整。

### 扩展的创造性的安置

广告设计者决定在屏幕上放置扩展广告创意的位置, 特别是当扩展视图可以放置在多个位置时。对于全屏扩展, 所有 MRAID 实现都提供了广告的全屏视图, 并将广告定位为完全可见。 

当扩展的创意大小大于或小于设备的屏幕大小时, 主机将容器调整为应用程序和设备允许的最大大小。主机可能无法缩放广告以适合屏幕。相反, 广告可能会在扩展的容器中使用 CSS 定位扩展的创意。    
  
![](http://oz3on0sof.bkt.clouddn.com/as.jpg)

语法|展开 ([URL]) 
-----|-----
参数|url (可选): 要在新的叠加视图中显示的文档的 url。如果使用 null 或非 URL 参数, 则当前 ad 的正文将在当前 web 中使用。
返回值|没有
相关事件|StateChange()
 
### 5.9	isViewable () (已弃用)

isViewable ()方法在 MRAID 3.0 中被否决, 并且将在 MRAID 的将来版本中被删除。为了向后兼容起见, 此功能仍保留在 MRAID 3.0 中。

isViewable ()方法返回广告容器当前是否在屏幕上。的viewableChange当广告从 on-screen 移动到屏幕外时, 事件会触发, 反之亦然。

对于 two-piece 可扩展的广告, 当广告 状态被扩展时,isViewable ()返回基于扩展广告可见的答案。

在任何情况下, 广告可能会被载入屏幕, 广告必须检查其可视状态和/或注册viewableChange在采取任何行动之前。

请注意, MRAID 没有定义必须在屏幕上构成 "可查看" 的广告的最小阈值百分比或像素数。

语法	|isViewable () 
-----|-----
参数	|没有
返回值	|true: 容器是 on-screen 的, 用户可以根据既定的值查看<br>false: 容器处于屏幕外, 无法查看
相关事件|viewableChange 
 
### 5.10	playVideo ()

广告使用playVideo ()当一个视频组件的创意需要发挥在设备的本地播放器。要以内嵌方式而不是在本地播放机播放视频, ad 设计器必须改用 HTML5 视频标记。

语法	|Playvideos (URI) 
-----|-----
参数	|url: 字符串, 视频或视频流的 url
返回值	|没有
相关事件	|没有
 
### 5.11	resize()

调用resize()是一个容器大小变化的请求, 可容纳创意大小的变化。调整大小用于连续的更改或尺寸更改小于全屏大小, 并且不影响应用程序操作。

在调用resize(), 则 广告必须指定所需的宽度和高度。

使用调整大小setResizeProperties ().调用resize()之前setResizeProperties将导致错误。

在调用调整大小后, 主机会通过将 广告容器调整为广告的所需大小来响应。

调整大小的操作比应用程序内容更高的 z-index, 这样它就不会推或重定位应用程序内容。如果一个应用程序希望支持内容转换的广告, 如 "推式", 应用程序必须实现应用程序重新定位功能来支持这些功能。
 
### 生成的事件

如果操作成功执行, 主机将发送两个事件: stateChange (7.4 节) 和 sizeChange (第7.3 节)。stateChange 将从 "default" 更新为 "resize"。如果在调用resize() 之前 广告状态为 "expanded", 则主机会发送7.1 节中讨论的错误事件。sizeChange 事件将随调整大小的容器的新宽度和高度一起发送。

一般执行说明|使用expand()而不是resize()广告创意, 扩大到全屏 (或更大) 的大小。因为全屏或更大的扩展包括应用程序内容,expand()提示停止其他应用程序操作。调整大小总是会导致非尺寸的变化, 应用程序的某些部分必须始终保持对最终用户可见。  
 
语法|resize() 
-----|-----
参数	|没有
返回值	|没有
相关事件	|sizeChange stateChange 
 
### 5.12	storePicture ()
 
为用户提供存储图像的选项的广告,storePicture ()可以使用 (如果支持), 将图像放在设备的相册中。该图像可能是广告的一部分或从服务器中检索到。 

广告可以查询主机的设备支持storePicture使用 "支持6.1 节中描述的方法。如果storePicture不受支持, 则广告必须避免调用storePicture ().

如果支持, 主机将通过启动一个控件来请求用户的存储图像的权限来响应。该控件是一个模式操作系统级处理程序, 它为用户提供了确认/取消选项。如果设备缺少此类处理程序, 则主机在支持对象中报告错误值。storePicture功能.

MRAID 实现必须支持使用 HTTP 重定向 (用于跟踪目的) 添加图片;但是, 不需要实现支持 meta-redirects。

如果由于某种原因添加图片的尝试失败或被用户取消, 则主机将发送错误。

语法	|Storepicture (URI) 
-----|-----
参数	|字符串: 图像或其他媒体资源的 URI
返回值|	没有
相关事件	|没有
 
### 5.13	createCalendarEvent()

如果支持, 则广告可以使用createCalendarEvent()打开用于添加事件的设备日历 UI。主机通过在本机设备上填充 "创建日历" 事件工作表来响应。如果未找到事件工作表, 则宿主会为支持对象中的日历功能报告 "false" 值。 

在日历用户界面打开时, 任何广告操作都将挂起。日历事件数据必须以写入 W3Cs 日历规范的 JavaScript 对象的形式传递。有关 W3Cs 日历规范的详细信息, 请参阅附录。

如果创建日历事件的尝试失败或被用户取消, 则主机将发送错误。

语法	|createCalendarEvent (参数) 
-----|-----
参数	|url: 字符串: 图像或其他媒体资源的 url
返回值	|没有
相关事件	|没有
 
### 5.14	VPAID 方法 

MRAID 广告可能包括旨在报告 VPAID 事件的视频。下面的 MRAID 方法用于在 MRAID 上下文中设置 VPAID 事件, 以及获取有关所显示的视频广告的最小信息。有关在 MRAID 应用程序实现中使用 VPAID 的其他详细信息, 请参见9节。

#### 5.14.1	initVpaid () 

一旦广告已经检查了 VPAID 支持mraid 支持 ()方法, 它需要给容器一个vpaidObject容器用来传达有关视频播放的事件和信息。VPAID 对象使宿主能够订阅 VPAID 事件, 启动 ad, 并调用有限的 VPAID 方法集。后initVpaid ()调用, 为了使视频播放开始, 容器必须调用vpaidObject startAd ()。广告不能开始视频播放, 直到videoObject startAd () 被调用。 
 
语法	|initVpaid (vpaidObject) 
-----|-----
参数	|vpaidObject –对在 ad 中存在的 JavaScript VPAID 对象的引用
返回值	|没有
相关事件	|没有
 
#### 5.14.2	vpaidObject.subscribe() 

广告电话后initVpaid (), 主机可以订阅选择 VPAID 事件, 使用vpaidObject.subscribe().有关支持的和不支持的 VPAID 事件的列表, 请参见9.1.3 节。

#### 5.14.3	vpaidObject.startAd () 

当主机确定该应用程序已准备好播放视频广告时, 它可以调用vpaidObject.startAd ()通知 MRAID 广告, VPAID 的创意现在可以发挥。

#### 5.14.4	vpaidObject.unsubscribe() 

当主机不再需要侦听订阅的事件时, 它可以调用vpaidObject.unsubscribe(), 使用事件名称指定不再需要的事件。

#### 5.14.5	vpaidObject.getAdDuration () 

主机使用vpaidObject.getAdDuration ()查询广告的广告总持续时间的视频广告。广告返回广告总持续时间的秒数。

#### 5.14.6	vpaidObject.getAdRemainingTime ()

主机使用vpaidObject.getAdRemainingTime()查询在查询时剩余的总播放时间的广告。广告返回在请求时的广告播放的剩余秒数。
 	  
## 6	属性

本节中介绍的方法使广告能够查询主机有关某些容器属性的信息。在某些情况下,广告可以设置某些属性, 以指示主机如何更新容器以适应广告操作。例如,广告必须先设置调整大小的属性, 然后再调用调整大小的方法。然后, 主机使用 set 属性相应地调整容器。

### 6.1	支持

该广告可以使用支持用于查询主机的功能, 该应用程序可以访问哪些 devicenative 功能。对支持的本机功能的认识有助于在不支持某些功能的环境中对 ad 进行补偿。

广告可以查询主机以支持以下本机功能:
功能	|描述
-----|-----
sms	|该设备支持使用 sms: 发送 sms 消息的协议
电话	|该设备支持使用电话: 协议启动呼叫
日历	|该设备可以创建一个日历条目
storePicture	|该设备支持 MRAID storePicture 方法
inlineVideo	|该设备可以使用<video>标记并在视频标签中指定的大小 (宽度和高度)</video>来播放 HTML5 视频文件。<br>
这并不要求在全屏播放视频。
vpaid	|设备容器支持与 ad 的 VPAID 握手, 以传达 VPAID 9 节中讨论的事件
位置	|该设备支持对 GPS 坐标的访问
 
 	 
应用程序上的 MRAID 实现必须能够在任何能够使用它们的设备上提供所有这些功能, 除非应用程序发布者已经停用了与发布服务器策略冲突的功能。

语法	|支持 (功能) 
-----|-----
参数	|功能: 字符串, 上面表中列出的功能名称
返回值	|true: 支持该功能, 并且有 getter 和事件可用<br>false: 此设备不支持此功能
相关事件	|没有
 
### 6.2	getPlacementType

广告电话getPlacementType ()以确定它是否被加载到内联放置或间隙中。

为了提高效率, 广告商有时会在两个横幅 (内嵌) 和间隙放置中单独进行创作。这些广告可能被设计成不同的行为取决于它的放置方式。

在两部分可扩展广告的情况下, 第二部分扩展创意也必须查询主机的放置类型。

主机返回的是 "内联" 或 "间隙", 如下表中所定义。

语法	|getPlacementType () 
-----|-----
参数	|没有
返回值	|inline: 默认的 ad 放置与显示中的内容内联 (横幅)<br>interstitial: 广告投放在内容之上
相关事件	|没有
 
### 6.3	get/set orientationProperties 

该广告使用orientationProperties查询主机当前的设备方向, 并设置orientationProperties为扩展和位提供广告展示。默认状态下的横幅不能使用orientationProperties.Resizeable 广告可以使用orientationProperties, 但它们不会有任何效果。
 
下面的代码段是orientationProperties对象:
```
orientationProperties object = {   "allowOrientationChange" : boolean, 
 "forceOrientation" : "portrait|landscape|none" 
} 
```

方向对象中提供的两个属性如下所示:

allowOrientationChange: 布尔

设置为 "true", 容器将允许基于方向的变化;设置为 false, 容器将忽略基于方向更改 (例如, 即使设备的方向更改, web 也不会更改)。 默认值为 "true"。 在任何时候, 无论如何设置 allowOrientationChange, ad 都可以通过设置 forceOrientation 变量来请求更改其方向。

forceOrientation: 字符串

设置为 "纵向"、"横向" 或 "无" 的值。 如果forceOrientation设置, 则无论设备的方向如何, 视图都必须以指定方向打开。即, 当用户点击以横向模式扩展广告时,forceOrientation属性设置为 "纵向", 则无论该设备的方向或广告的前向方向如何, 广告都将以纵向方向打开。默认为 "无"。

为了对 ad 行为进行更精细的控制, ad 可以在 ad 处于展开状态后更改方向对象中任一属性的设置。这样一个广告可以从肖像开始, 但指示用户改变方向来玩游戏。游戏需要倾斜, 以便在用户完成之前不允许任何方向更改。 主机必须能够接受更改, 以便在用户与可扩展 ad 的交互过程中扩展属性。

广告必须同时设置两个属性, 以确保正确控制广告的方向。如要强制更改为横向方向, 请设置allowOrientationChange为 "false" 并设置forceOrientation以 "横向" 为例:
```
mraid. setOrientationProperties ({"allowOrientationChange": true}
); 
mraid.expand() 
 
/* 用户更改景观, 开始游戏 */ mraid setOrientationProperties ({"allowOrientationChange": false
} ); 
 
/* 用户已完成游戏 * /
mraid. setOrientationProperties ({"allowOrientationChange": true}); 
 ```
getOrientationProperties方法提示主机返回整个orientationProperties对象.

语法	|getOrientationProperties () 
-----|-----
参数	|没有
返回值|	JavaScript 对象: 包含方向属性
相关事件|	没有
 
setOrientationProperties方法将属性设置为orientationProperties对象.

语法	|setOrientationProperties (属性) 
-----|-----
参数	|属性: 包含值的 JavaScript 对象。allowOrientationChange和forceOrientation.
返回值	|没有
相关事件	|没有
### 6.4	getCurrentAppOrientation
广告电话getCurrentAppOrientation查询主机当前的应用程序方向。

主机将应用程序的当前方向返回为 "纵向" 或"横向" 以及是否锁定了给定的方向。如果锁定, 则forceOrientation选项setOrientationProperties不受支持。

语法	|getCurrentAppOrientation () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: {方向, 锁定}:<br>●	方向: 价值可以是 "肖像" 或 "景观"<br>●	锁定: 布尔值, 指示在当前位置是否锁定了方向。如果 "真" 那么forceOrientation在setOrientationProperties不受支持。
相关事件|没有
 
### 6.5	getCurrentPosition

广告电话getCurrentPosition为 广告容器的当前位置查询主机。

宿主返回 广告容器的当前位置和大小, 以与密度无关的像素来度量。

语法	|getCurrentPosition () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: {x、y、宽度、高度} 在以下位置:<br>●	x = 从矩形左边缘到定义的密度无关像素偏移量getMaxSize ()<br>●	y = 从定义的矩形顶部偏移的与密度无关的像素的数目getMaxSize ();<br>●	宽度 = 与密度无关的像素的容器的当前宽度<br>●	高度 = 当前容器的高度 (以 densityindependent 像素为单位)
相关事件	|没有
 
### 6.6	getDefaultPosition

广告电话getDefaultPosition查询主机的位置和大小的默认广告容器, 以密度无关的像素测量。

无论调用视图处于何种状态, 宿主都将返回广告容器的默认位置和大小的值。

语法	|getDefaultPosition () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: {x、y、宽度、高度} 在以下位置:<br>●	x = 从矩形左边缘到定义的密度无关像素偏移量getMaxSize ()<br>●	y = 从定义的矩形顶部偏移的与密度无关的像素的数目getMaxSize ();<br>●	宽度 = 与密度无关的像素的容器的当前宽度<br>●	高度 = 当前容器的高度 (以 densityindependent 像素为单位)
相关事件	|没有
 
### 6.7	getstate

在任何时候, 广告可以使用getstate查询主机有关 广告容器状态的信息, 并相应地发出请求。

宿主返回 广告容器的当前状态, 这些值用于描述 广告容器是否处于默认和固定位置、扩展或调整大小的状态、较大的位置或隐藏。

语法	|getState () 
-----|-----
参数	|没有
返回值	|字符串: "loading", "default", "expanded", "resized" 或 "hidden"
相关事件	|stateChange
 
### 6.8	获取/设置 expandProperties

广告使用getExpandProperties在当前展开设置中查询主机, 并setExpandProperties设置扩展的宽度和高度, 以及可选地指定自定义关闭指示器的使用。
在广告调用之前expand (), 广告需要确定扩展所需的宽度和高度, 使用setExpandProperties.ad 还可以指定自定义关闭指示器图形, 而不是使用主机默认指示器。主机忽略所有展开属性后设置的expand()被调用。

下面是一个示例expandProperties对象:
```
expandProperties object = { 
 “width” : integer,  
 “height” : integer, 
 “useCustomClose” : boolean, 
 “isModal” : boolean (read only) } 

```

属性	|描述
-----|-----
宽度	|整数–宽度的创造性, 默认为全屏宽度。
高度	|整数–高度的创造性, 默认为全屏高度。 请注意, 在设置扩展属性之前, 宽度和高度值将反映屏幕的实际值。这将允许希望使用应用程序或设备值的广告设计者根据需要进行调整。
useCustomClose	|这是不推荐的。在 MRAID 3.0 主机将忽略此请求<br>布尔-true, 容器将停止显示默认关闭图形, 并依赖于广告创意的自定义关闭指示器<br>布尔值为false (默认), 则容器将显示默认关闭图形。此属性的函数与我们useCustomClose 方法 (5.6 节), 并提供方便的可扩展广告的创造者。
isModal	|布尔值-true, 容器是扩展的 ad 的模式, 在扩展期间必须停止其他操作;假的, 容器不是模式为扩展的广告和其他操作可能继续在扩展期间。此属性对于 广告 是只读的, 无法设置。 
 
当广告调用getExpandProperties, 主机将返回整个expandProperties对象.

语法	|getExpandProperties () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: 包含上表中描述的 ad 扩展的展开属性。
相关事件|	没有
 
广告使用setExpandProperties设置属性expandProperties对象之前启动广告扩展展开 ().

语法	|setExpandProperties (属性) 
-----|-----
参数	|JavaScript 对象: {width, height, useCustomClose} 包含展开的广告的宽度和高度。
返回值	|没有
相关事件	|没有
 
### 6.9	getMaxSize
广告电话getMaxSize查询主机大小的最大值 (以 densityindependent 像素为单位), 广告可以调整该尺寸。

如果应用程序在设备上运行全屏 (覆盖状态栏), 则主机将返回全屏维度。如果应用程序在设备上的屏幕上运行不到全屏, 通常会在应用程序之外为状态栏或其他元素留出空间, 那么主机将返回包含该应用程序的视图的大小。 

语法	|getMaxSize () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: {宽度、高度} 包含 web 的最大宽度和高度 (web 可以调整为不大于给定的宽度和高度)。
相关事件	|没有
 
6.10	getScreenSize
广告电话getScreenSize要查询主机大小的设备屏幕尺寸, 特别是在扩展广告之前 (用于调整大小使用getMaxSize).主机以密度无关的像素返回当前设备屏幕的宽度和高度。 
当设备方向更改时, 此大小会发生变化。例如, 当重新定向到横向模式时, 以纵向模式640x960 的屏幕将变为960x640。
将返回整个屏幕大小, 包括为状态或系统栏以及应用程序无法覆盖的其他功能空间保留的任何区域。为了找出在应用程序上可以使用多少可用大小的广告显示, 广告必须调用getMaxSize ()6.9 节所述。
语法	getScreenSize () 
参数	没有
返回值	JavaScript 对象: {width, height} 包含设备屏幕的宽度和高度, 具体取决于其方向
相关事件	没有
 
### 6.11	get/set resizeProperties
在 广告 执行调整大小之前, 它可以调用getResizeProperties查询主机有关调整广告容器大小的当前设置。然后广告可以调用setResizeProperties若要更新resizeProperties对象.当广告调用时, 宿主使用此对象中设置的属性来调整广告容器调整大小 ().

下面是resizeProperties对象:
```
resizeProperties object = { 
 “width” : integer,  
 “height” : integer, 
 “offsetX” : integer,  
 “offsetY” : integer, 
 “customClosePosition” : string, 
 “allowOffscreen” : boolean 
}  
```
resizeProperties对象可用的属性如下所示:

属性	|描述
-----|-----
宽度*	|整数: 宽度, 以密度独立的像素为单位, 必须调整广告容器的大小
高度*	|整数: 高度, 密度独立像素, 必须调整广告容器的大小
offsetx*	|整数: 从当前左上角位置到所需的大小调整的广告容器的左上角位置的水平增量。正整数向右移动;负整数向左移动。
offsety*	|整数: 从当前左上角位置到所需的大小调整的广告容器的左上角位置的垂直增量。正整数向下移动;负整数向上移动。
customClosePosition	|这在 MRAID 3.0 中被否决。主机将始终在右上角添加关闭指示器。
allowOffscreen	|布尔: 指示调整大小的广告容器是否必须允许部分绘制或完全外。<br>●	true:允许外定位;主机必须避免重新定位广告容器, 尽管导致外放置。<br>●	false:外定位必须避免, 主机必须尝试重新定位广告容器

属性	|描述
-----|-----
null|以便它在指定的区域中显示。maxsize属性.

需要;如果未提供任何值, 则使用setResizeProperties在广告调用之前resize(),然后主机保留原始设置并发送错误。

### 在重新定位外时调整结果大小时

allowOffscreen属性设置为 "false", 则主机尝试将大小调整后的创造性与维度中定义的maxsize对象.例如, 如果广告位于屏幕的顶部, 并且广告希望以50像素为单位向上调整大小, 则主机在执行调整大小之前将广告50像素向下移动。 

当allowOffscreen在同一操作中设置为 "true", 则广告的调整大小部分将从屏幕顶部以外的50像素扩展到视图之外。

allowOffscreen属性无法解决所有定位问题。例如, 如果广告在横向方向上成功调整了大小, 然后再进行方向更改, 则会导致更大的广告, 即 "false"allowOffscreen是无效的。

调整广告的大小必须先测试质量, 然后再服务于应用程序以显示。如果广告提供主机无法成功执行的大小调整值, 则主机将发送错误。

### 检查和设置大小调整属性

广告使用getResizeProperties查询主机的当前调整大小属性。主机返回resizeProperties对象.

语法	|getResizeProperties () 
-----|-----
参数|	没有
返回值	|JavaScript 对象: {宽度、高度} 包含大小调整属性
相关事件|	没有
 
广告使用setResizeProperties更改中的值。resizeProperties对象.主机中的值将替换resizeProperties使用广告提供的值来对象。

语法|	setResizeProperties (属性) 
-----|-----
参数	|JavaScript 对象: 包含已调整大小的广告的宽度和高度、关闭位置、偏移方向 (所有像素都与密度无关), 以及广告是否可以调整屏幕的大小。
返回值	|没有
相关事件|	没有
 
### 6.12	getlocation 

在广告活跃的时候知道设备的位置可以提高广告的创造性, 但不是所有的应用程序都支持对位置细节的访问。支持功能在 MRAID 3.0 (见第6.1 节) 确定是否支持 "位置"。

如果支持, 则使用具有以下属性的位置对象来提供位置值:

属性	|描述
-----|-----
lat	|设备的纬度坐标
lon	|设备的纵向坐标
type 	|位置数据源;通过 lat/lon时推荐<br>1: GPS/定位服务<br>2: IP 地址<br>3: 用户提供 (如注册数据) 
精度|估计的位置精确度在米;当指定了 lat/lon并从设备的位置服务 (即类型 = 1) 派生时建议使用。请注意, 这是从设备报告的准确性。查阅操作系统特定文档(例如, Android, iOS) 的精确解释 
lastfix|建立此地理定位修复后的秒数。请注意, 设备可能会在多个回迁中缓存位置数据。理想情况下, 此值必须从实际修复时起 
ipservice	|服务或提供商, 用于确定地理定位从 IP 地址, 如果适用 (即, 类型 = 2)。
 
如果支持, 则广告使用getlocation查询主机的设备位置。主机返回位置对象, 其中详细介绍了设备位置数据以及数据来自何处。

语法	|getLocation () 
-----|-----
参数	|没有
返回值	|JavaScript 对象: 上表中描述的位置对象。
相关事件|	没有

HTML5 API 的位置不能用来取代上述。

当 lat 和lon属性不可用或不允许按用户权限使用时, 必须将 "-1" 的错误信息传达给getLocation ()方法.

## 7	事件

事件用于报告已发生的操作或确认 web 状态的更改。主机发送事件以将活动与 广告 通信。广告 必须创建侦听器, 以便在发生特定事件时通知它们。  
### 7.1	错误

当主机无法执行 广告 调用的函数时, 主机将发送一个错误, 描述发生错误时所尝试的操作。广告 必须注册侦听器才能接收错误事件。任何数量的侦听器都可以监视不同类型的错误, 以便广告可以根据需要进行响应。  

一个错误事件提供两个参数: 一个用于错误消息, 一个用于在发生错误时试图执行的操作。两个参数都是可选的, 消息选项通常用于调试前的创造性。

下列任何 MRAID 操作都可能导致错误:
<pre>
•	addEventListener	• getVersion
•	createCalendarEvent	• isViewable
•	close	• open
•	expand	• playVideo
•	getCurrentPosition	• removeEventListener
•	getDefaultPosition	• 调整
•	getExpandProperties	• setExpandProperties
•	getlocation	• setResizeProperties
•	getMaxSize	• storePicture
•	getPlacementType	• supports
•	getResizeProperties	• useCustomClose
•	getScreenSize	 
•	getstate
</pre>
虽然广告可能会注册任何上述操作导致的错误, 但最常见的错误是由于使用resize(),storePhoto (), 并createCalendarEvent ().广告必须为这些错误注册侦听器, 并准备相应地作出反应。

由于主机可以同步处理错误 (在 real-time 中) 或异步 (时间), 因此广告开发人员必须考虑在接收时必须如何处理错误详细信息。

语法	|"error" function(message, action) 
-----|-----
参数	|消息: 字符串, 所发生的错误的说明操作: 字符串, 发生错误时试图执行的 MRAID 操作的名称
触发的	|任何出错

### 7.2	准备

在加载广告之前, 主机必须使 MRAID 库可用于 广告, 以便广告可以在主机发送的事件上进行调用和注册侦听器。至少,广告容器必须支持getState (), 并
广告dEventListener ()尽快。如果没有这两个函数,广告就无法为主机就绪事件注册侦听器。 

理想情况下, 只有在容器中支持所有 MRAID 函数, 并且主机准备好从广告接收任何 MRAID 调用后, 才会发送就绪事件。

广告必须等待主机发送就绪事件检查, 显示容器在执行任何富媒体操作之前已就绪。如果主机已在广告注册前发送就绪事件, 则广告必须使用getState ()与就绪事件结合使用, 如下面的示例所示:
```
function showMyAd() {  ... 
} 
 
if (mraid.getState() === 'loading') {     mraid.addEventListener('ready', showMyAd); 
} else { 
    showMyAd(); 
} 
```
主机发送准备在加载、初始化广告容器并准备接收来自广告的调用时的事件。因此, MRAID 的 JavaScript 库可供广告使用。

语法|	准备" 
-----|-----
参数	|没有
触发的	|容器已完全加载、初始化, 并且可以从广告的任何调用
 
### 7.3	sizeChange

主机发送sizeChange每当 广告 容器维度因方向、广告 大小调整请求或 广告 扩展请求而发生更改时发生。该事件包括与密度无关的像素的新宽度和高度。
语法	|"sizeChange"function(width, height) ) 
-----|-----
参数	|宽度: 数字, 视图高度的宽度: 数字, 视图的高度
触发的	|由于调整大小、展开、关闭、方向或应用程序注册 "size" 事件侦听器而导致的 广告 容器宽度和高度尺寸的变化。

### 7.4	stateChange
主机发送stateChange每当 广告 容器状态因响应 广告 调用或环境更改而更改时, 该事件随更新状态一起发生。

在任何时候, 广告容器的状态可能是:
<pre>
●	loading 
●	default 
●	expanded 
●	resized 
●	hidden 
</pre>
广告 容器状态可能会因以下原因而更改: 主机启动 (加载)、userinitiated 关闭或其他应用程序交互 (如窗口调整大小和方向更改) 以及 广告 调用expand(), resize(), 和close().有关 广告 容器状态及其更改方式的详细信息, 请参见4.2.1 节。

广告可以使用getstate, 6.6 节中讨论了如何查询主机的当前 ad 容器状态。

语法	|"stateChange"函数 (状态) 
-----|-----
参数	|状态: 表示 "加载"、"默认"、"展开" 的字符串,
"调整大小" 或 "隐藏"
触发的	|open (),close(), 或应用程序做的事情, 改变了 web 的状态
 
### 7.5	exposureChange 

exposureChange事件在 MRAID 3.0 中引入, 以更准确地反映可见。

在两部分广告中不支持曝光更改事件。

当 广告 注册侦听器时,exposureChange事件时, 主机将该事件异步发送给 广告 的所有侦听器。在初始事件之后, 主机报告exposureChange任何时候暴露的区域发生变化。一个exposedPercentage值 0.0 (零) 表示当前的 广告 容器未在视图中或已移动到背景中。当 广告 容器或其任何父视图被滚动、转换或剪切时, 可能会发生曝光更改。主持人还报告exposureChange由于应用程序或 UI 转换而更改 广告 的可见性时发生的事件。

主机必须发送exposureChange当 广告 视图的裸露区域更改时, 即使可见百分比不变, 也会发生事件。这些事件的例子包括调整大小, 显示或隐藏一个间隙, 横幅扩展到全屏, 和横幅广告被附加到窗口。这些曝光更改会提示 广告 根据更新的 广告 大小重新计算可见的度量值。

主机可以执行 "exposureChange"通过本机事件处理或在本机层中进行轮询。有关要求, 请参见 "轮询率和事件阈值" 一节。

语法	|"exposureChange" function(exposedPercentage、visibleRectangle、occlusionRectangles) 
-----|-----
参数	|exposedPercentage: 在屏幕上可见的 广告 百分比, 介于0.0 和100.0 之间的 floating-point 数字, 如果不可见, 则为0。0
<br>visibleRectangle: 广告 容器的可见部分, 如果不可见, 则为 null。 它有字段{x、y、宽度、高度}, 在x和y是可见区域左上角的位置, 相对于 广告 容器的当前范围的左上角, 以及宽度和高度可见区域的大小。 如果可见区域是矩形的, 则此参数是可见部分的边界框, 而occlusionRectangles参数描述边界框中的不区域 
<br>occlusionRectangles: 一个矩形数组, 描述visibleRectangle如果未使用或相关的遮挡检测, 则不可见或为 null。 数组的每个元素都有字段{x、y、宽度、高度}, 在x和y是遮挡区域左上角的位置, 相对于 广告 容器的当前范围的左上角, 以及宽度和高度是闭塞区域的大小。 矩形不能重叠, 它们必须从最大区域排序到最小区域。 在常见情况下, 可见区域为矩形, 此参数为 null。 如果实现可以检测到矩形的曝光, 则此参数将被设置 
 
触发的	|web 的暴露面积的变化。请参阅下面的详细信息, 了解触发exposureChange事件.
 
示例函数
```
{ 
 "exposedPercentage": 78, 
 "viewport": { 
    "width": 375, 
    "height": 667 
 }, 
 "visibleRectangle": { 
    "x": 27.5, 
    "y": 65, 
    "width": 300, 
    "height": 50 
    "occlusionRectangle":  
      { 
        "x": 27.5, 
        "y": 65, 
        "width": 50, 
        "height": 50 
      } 
```

 
exposureChange 事件的触发器

当所有这些属性都为真时, 广告被认为是公开的:
<pre>
●	设备未处于休眠或锁定状态, 且屏幕处于已上。
●	应用程序在前台。
前台应用程序是设备屏幕上的活动应用程序, 可供用户输入。在 Android 上, 活动是调用*Activity.onResume()*和*Activity.onPause()*方法.在 iOS 上, 应用程序是在前景之间的UIApplicationDidBecomeActiveNotification和UIApplicationWillResignActiveNotification事件.
●	广告 视图至少有一个像素 on-screen, 同时考虑到应用程序的视图层次结构中的剪辑和滚动。(此计算不需要考虑视图层次结构中的 Z 顺序遮挡。 请注意, 这是从 MRAID 2.0 规范的变化, 它没有任何像素阈值的可见广告。
●	没有用于阻止 广告 的模式接口。 模式接口可以包括 MRAID 功能, 如在应用程序浏览器或应用程序商店显示通过mraid.open(), 通过视频播放mraid playVideo (), 相册访问通过mraid.storePicture ()和日历访问通过mraid.createCalendarEvent (), 以及其他应用程序的模式屏幕。
</pre>

如果这些条件中的任何一个不举行, 广告是看不到, 没有暴露。

主机报告曝光更改, 如下所示:

条件|	报告的曝光更改
-----|-----
广告容器暴露 	|exposureChange 事件具有非零百分比参数
广告 容器处于视图之外或其他活动视图的后面 	|exposureChange 事件有零 exposedPercentage 参数
广告 容器从暴露到视图之外的更改 	|主机发送 exposureChange 与零 (0) exposedPercentage 参数
广告 容器从视图更改为暴露 	|主机发送非零 exposedPercent 参数的 exposureChange
广告 容器状态或大小更改, 但暴露百分比保持不变 	|主机发送与先前报告的 exposedPercent 参数相同的 exposureChange 事件
 
### 7.6	audioVolumeChange 
主机使用audioVolumeChange报告音频音量百分比的变化。音频音量可以通过将设备音量乘以任何浇口因素来计算, 其中可能包括应用程序音频焦点、应用程序特定的音量级别、设备静音和其他因素。如果应用程序无法播放音频, 或者无法确定音频音量, 则此事件报告 null 而不是百分比。 

语法	|"audioVolumeChange"function(volumePercentage) 
-----|-----
参数	|volume_Percentage: 最大音频播放音量的百分比, 0.0 和100.0 之间的 floating-point 数字, 如果不允许播放, 则为 0.0, 如果无法确定音量, 则为 null
触发的	|广告音频回放音量的变化
  
当一个广告注册audioVolumeChange事件时, 主机异步向该 ad 的所有侦听器发送具有初始音频音量级别的事件。在该初始事件之后, 主机报告audioVolumeChange如果音频音量更改, 则为事件。

当用户更改设备卷或使设备静音时, 通常会出现音量更改的原因。当音频焦点因应用程序或 UI 转换而更改时, 宿主还会报告卷更改。可以报告具有相同百分比值的多个音频更改事件。

宿主可以通过本机事件处理或在本机层中通过轮询来确定音频级别。如果本机层使用轮询, 则它必须发送audioVolumeChange事件不晚于1.0 秒后的音频更改。
音量变化事件是广告控制之外的有效音量。广告也可能对音量有一定的控制, 比如静音控制。直接在 广告 中发生的卷控制不反映在audioVolumeChange事件.
在某些情况下, 当 广告 不播放音频时, 主机可能无法访问音频级别。另外, 主机可能无法辨别音频是否已静音或不播放, 例如当静音开关打开时, 但耳机仍然工作。在这种情况下, 主机报告volume_Percentage在广告播放之前的空, 然后另一个audioVolumeChange只有在播放开始后才具有数字音量级别的事件, 并且主机可以检测音量级别。

### 示例用法

当主机提供audioVolumeChange事件除了在 MRAID 的其他功能, 广告将能够确定可。广告 可能使用以下伪代码:

1.	注册侦听器。audioVolumeChange事件.例如,mraid addEventListener ("audioVolumeChange", handleVolumeChange); 
2.	audioVolumeChange当达到阈值时, 处理程序可以比较具有可阈值和日志时间的卷:
<br>
```
function handleVolumeChange(volume_percentage) {    if (volumePercentage && volumePercentage >= 10.0) { 
       // log audible time ... 
   } } 
```
3.	当 ad 的取样时间足够长以满足所需的可指标时, 请删除audioVolumeChange侦听.例如,mraid removeEventListener ("audioVolumeChange", handleVolumeChange); 

### 实施说明

此 JavaScript 事件驱动的 api 是在状态 api 上选择的 例如

“getAudioVolume ()", 原因如下:
<pre>
●	直接从本机层获取值
“getAudioVolume () "JavaScript 中的状态调用将涉及阻止 web 执行线程, 这会对性能产生负面影响。为了防止 "getAudioVolume ()"通过阻止 JavaScript 线程的状态调用, 本机层将必须检查音频级别 (并缓存结果) 是否有创意使用过该值。通过使用事件接口, 只有对管理音频量感兴趣的广告才会产生确定值的成本。
●	事件接口避免了 JavaScript 层中的轮询循环。
●	添加 "getAudioVolume ()"状态 API 除了“audioVolumeChange事件接口是多余的。JavaScript 的创造性可以很容易地实现这样一个功能的基础上, 其处理程序为事件。
</pre>

### android 

在 Android 上, 类android.media.AudioManager提供对设备音频级别的访问。该值必须由显示 ad 的 web 的音频焦点状态来封闭。下面的伪代码将返回设备音频音量。
```
Double getAudioVolumePercentage() { 
   if (!adHasAudioFocus()) return null;    AudioManager audioManager = (AudioManager)         getContext().getSystemService(Context.AUDIO_SERVICE)    int currentVolume =  
       audioManager.getStreamVolume(AudioManager.STREAM_MUSIC);    int maxVolume =  
       audioManager.getStreamMaxVolume(AudioManager.STREAM_MUSIC)
; 
   return new Double((100.0 * currentVolume) / maxVolume); 
} 
```

该方法adHasAudioFocus ()在伪代码将调用 MRAID 实现的音频焦点和活动背景检查的处理。

### ios 

在 iOS 上, 类AVAudioSession提供对设备音频音量级别的访问。 但是, 只有当应用程序具有音频焦点 (活动音频会话) 时, 音量级别才有效。 下面的伪代码将返回设备音频音量。
```
-(NSNumber*)getAudioVolumePercentage {    if (![self adHasAudioFocus]) return nil;    return @(100.0 * [AVAudioSession 
sharedInstance].outputVolume); 
} 
```
该方法adHasAudioFocus在伪代码将调用 MRAID 实现的音频会话和应用程序背景检查的处理。

### 7.7	viewableChange (已弃用)

viewableChange事件在 MRAID 3.0 中被弃用, 并且可能在未来版本的 MRAID 中被删除。但是, 主机仍然必须支持viewableChange在 MRAID 3.0 中, 以保持向后兼容性。主机发送viewableChange当广告容器从 on-screen 移动到屏幕外或从屏幕上移到 on-screen。在任何情况下, 容器可能被载入屏幕, 广告应检查其可视状态和/或注册viewableChange在采取任何行动之前。

语法	|"viewableChange"function (布尔值) 
-----|-----
参数	|true: 容器是 on-screen 的, 用户可查看<br>false:容器处于屏幕外, 无法查看
触发的	|应用程序视图控制器中的更改

## 8	使用设备功能

MRAID 旨在提供与移动设备功能 (如地理位置、方向、图像存储、日历和本地视频播放器) 的交互。以下各节提供了用于开发使用这些功能的广告的指南和示例。

### 8.1	设备方向

广告不应使用窗口. 方向确定方向或 orientationChange 事件以确定方向的变化。在较新的 OS verisons 上, 主机无法控制 web 报告的方向更新, 有时 web 报告方向不准确。 
 
而不是窗口. 方向要确定方向, 广告必须使用mraid getCurrentPosition(), 并比较宽度和高度值以标识纵向或横向布局。而不是使用orientationChange当布局更改时, 广告必须使用它作为提示来检查报告中的宽度和高度值。sizeChange以验证 广告 方向。

getOrientationPropertiesMRAID 3.0 中提供的功能应用于在 广告 不管理 广告 大小时确定方向。有关使用的详细信息, 请参阅6.3 节。orientationProperties对象.

### 8.2	存储图片

富媒体广告设计者可能希望将图片添加到正在运行的设备的照相机卷或相册中。这可以方便的一些功能, 包括存储优惠券后赎回。
### storePicture方法
storePicture方法将在设备的相册中放置图片。该图片可能是本地的或从互联网上检索。 为了确保用户知道正在将图片添加到相册中, MRAID 要求 SDK/容器使用 OS 级别的处理程序来显示模式对话框, 要求用户确认或取消添加每个图像的相册。 如果设备没有本机 "添加照片" 确认处理程序, 则 SDK 必须将该设备视为不支持storePicture.

此方法将存储由 URI 指定的图像或其他媒体类型。

MRAID 兼容的容器将支持通过 HTTP 重定向 (用于跟踪目的) 添加图片;然而他们不一定支持元重定向。
<pre>
如果由于某种原因添加图片的尝试失败或被用户取消, 则会触发错误。storePicture (URI)参数: 
●	url 字符串: 图像或其他媒体资源的 url相关活动: 
●	没有
</pre> 
### 8.3	日历事件

#### createCalendarEvent方法

createCalendarEvent方法打开设备 UI 以创建新的日历事件。该广告在用户界面打开时暂停。 为确保创建日历事件始终是用户启动和授权的, MRAIDcompliant 容器必须调用设备的本机 "创建日历事件" 表, 并预先填充由 ad 提供的数据。 如果设备不支持这样的 "创建日历事件" 工作表, 则 SDK 必须将该设备视为不支持添加日历事件。

日历事件数据必须以写入 W3C's 日历规范的 JavaScript 对象的形式传递。 见附录。

如果创建日历事件的尝试失败或被用户取消, 则会触发错误。
<pre>
createCalendarEvent (参数)参数:
●	参数: JavaScript 对象 {...}-此对象包含日历项的参数, 该项是根据日历条目的 W3C 规范编写的。 见附录。
返回值:
●	没有
相关活动:
●	没有
</pre>	 

例如, 以下内容将为玛雅添加一个日历事件<br>
世界末日/末日在 2012年12月21日, 发生 "无处不在" 和开始在东部时间午夜和结束在东部时间午夜在2012年12月22日。
```
createCalendarEvent({description: “Mayan Apocalypse/End of 
World”, location: ‘everywhere’, start: ‘2012-12-21T00:0005:00, end: ‘2012-12-22T00:00-05:00’}) 
```
 
### 8.4	视频

移动设备上的视频可以在线播放 (在当前的 web、应用程序或移动网页中), 或者在设备上打开本地播放机。 对于许多广告应用程序, 内联播放是首选: 它不太破坏观众的经验, 并在一个 web 的回放使 HTML5 报告有关的指标, 有多少的创造性被视为。当在本地播放机中查看视频时, 这些度量标准通常很难访问或不可用。

广告 设计者必须记住, 设备/OS 限制可能会阻止内联视频播放 (这在运行 Android 2.x 和更早版本的设备时尤其如此)。

但是, MRAID 兼容的容器必须支持在可能的情况下进行内联回放, 并允许广告设计者指定视频创意必须在内联播放还是在单独玩家中播放。 Ad 设计人员可以使用 "支持 (" inlineVideo ")" 方法来确定运行创意的设备是否会显示内嵌视频。

为了启用视频的内联视频播放和自动播放, MRAID 兼容的 sdk 必须始终将任何必要的启用标记插入到 web 中, 具体取决于设备的操作系统。
对于 iOS 设备, 必须使用以下标记:

●	web mediaPlaybackRequiresUserAction = false;<br>
●	web allowsInlineMediaPlayback = true;

对于 Android (蜂窝, 冰淇淋三明治和以上) 设备, SDK 必须调用硬件加速, 这依赖于有关的视图以及如何将其添加到 WindowManager 中:

●	getWindow().setFlags(WindowManager.LayoutParams.FLAG_HARDWAR
E_ACCELERATED, WindowManager.LayoutParams.FLAG_HARDWARE _ACCELERATED); 

 
对于 Android 2.x 和更早的设备, 它是不可能播放视频内联;本机播放机始终由 playVideo 方法调用。

### playVideo方法

使用此方法可以通过设备的本地外部播放器在设备上播放视频。 请注意, 这纯粹是操作系统现有外部播放器的一种方便方法, 并不意味着一个单独的、SDK-based 的视频播放器。要播放视频内联 (在支持该功能的设备上), 请使用 HTML5 视频标记。
<pre>
playVideo (URI)参数: 
●	uri 字符串, 视频或视频流的 uri返回值: 
●	没有
</pre>

## 9	VPAID 事件和方法

MRAID 处理富媒体广告和应用程序或 web 之间的交互。当 广告 包含视频组件时, 宿主可以向 广告 表明它对视频播放事件感兴趣, 以及跟踪和用户体验的视频定时。 

实验室的数字流式视频播放器-广告 接口定义 (VPAID) 是一个接口, 它处理广告和视频播放器之间的通信。MRAID 2.0 的增编为启动 VPAID 和报告某些事件提供了支持。MRAID 3.0 集成了此附录, 并为主机提供了可选的遵从性, 以支持使用 MRAID 和 VPAID 开发的广告。

MRAID 的 VPAID 集成不处理与播放器的 广告 交互。集成使 MRAID 主机能够侦听 VPAID 事件。  

### 9.1	MRAID 广告中的 VPAID 互动

下图说明了 VPAID 视频在 MRAID 创意中的交互过程。
  
![](http://oz3on0sof.bkt.clouddn.com/aaab.jpg) 

### 9.1.1	在 MRAID 上下文中初始化 VPAID

MRAID/VPAID 广告初始化使用3节中描述的初始化机制.一旦容器返回 "就绪" 事件或将容器的状态设置为 "默认", 则 ad 可以检查容器是否支持 VPAID。
VPAID 的支持可以使用mraid 支持 ()方法使用 "vpaid" 的值, 格式如下:

mraid 支持 ("vpaid") 

支持 MRAID 3.0 中的 VPAID 是可选的, 但是支持 MRAID 3.0 的应用程序需要返回一个布尔值: 如果支持 VPAID 或不支持 false, 则为 true。
### 9.1.2	发送和接收 VPAID 事件

广告 验证主机是否支持 VPAID 时, 广告 必须调用mraid initVpaid (vpaidObject)将 VPAID 对象传递给容器。

主机然后订阅 VPAID 事件和调用vpaidObject startAd ().

广告可以启动视频创意, 并酌情发送 VPAID 事件。
### 9.1.3	如果不支持 VPAID
如果不支持 VPAID, 则 VPAID 支持的调用将返回 false, 导致错误, 或返回未定义的结果。当这种情况发生时, 创意必须开始的广告体验, 而无需等待vpaidObject.startAd ().  支持的 VPAID 方法和事件 

并非所有 VPAID 事件都在 MRAID 上下文中受支持。为了避免与 MRAID 或冲突的命令重叠, 仅支持以下 VPAID 方法和事件。当宿主支持 VPAID 集成时, 使用 vpaidObject 调用 VPAID 方法 (例如,vpaidObject.subscribe()订阅 VPAID 事件)。有关在 MRAID 中使用 VPAID 方法的详细信息, 请参见5.14 节。 
<pre>
支持的 VPAID 方法 
●	subscribe() 
●	unsubscribe() 
●	getAdDuration ()
●	getAdRemainingTime ()
●	startAd () 	
不支持的 VPAID 方法 
●	handshakeVersion
●	initAd ()
●	resizeAd ()
●	stopAd ()
●	pauseAd ()
●	resumeAd ()
●	expandAd ()
●	collapseAd ()
●	skipAd
支持的 VPAID 事件 
●	AdClickThru
●	AdError
●	AdImpression
●	AdPaused
●	AdPlaying	不支持的 VPAID 事件 
●	AdDurationChange
●	AdExpandedChange
●	AdInteraction
●	AdLinearChange
●	AdLoaded
●	AdVideoComplete
●	AdVideoFirstQuartile
●	AdVideoMidpoint
●	AdVideoStart
●	AdVideoThirdQuartile 	
●	AdLog
●	AdRemainingTimeChange
(在 VPAID 2.0 中已弃用)
●	AdSizeChange
●	AdSkippableStateChange
●	AdSkipped
●	AdStarted
●	AdStopped
●	AdUserAccept 邀请
●	AdUserClose
●	AdUserMinimize
●	AdVolumeChange
</pre>
 
此处未列出的任何 VPAID 方法或事件在 MRAID 中不受支持。列出的方法和事件应该有助于跟踪 MRAID 创意的任何视频部分的交互。 

### 9.1.4	VPAID AdClickThru 事件

VPAID广告创意使用AdClickThru事件来传达如何处理点击的 URL。VPAID 提供了三参数来定义 url (url)、用于跟踪目的的 id (id), 以及用于标识播放器或广告创意是否必须打开 url (playerHandles) 的布尔值。MRAID 容器必须忽略这些参数, 而广告必须使用mraid 打开 ()提供有关如何处理视频点击的主机说明。

### 9.1.5	VPAID AdPaused, AdPlaying 事件

在 VPAID,AdPaused和AdPlaying事件用于响应播放器命令,pauseAd ()和resumeAd ().但是, 在 MRAID 上下文中, 不发出命令, 因此AdPaused和AdPlaying事件被用来在发生这些事件时通知主机。

### 9.1.6	支持自动启动视频

为了支持最佳的交互式视频体验, 容器 web 必须支持内嵌视频和 autostart 视频。广告创意中的视频元素必须能够在没有用户交互和内嵌的情况下开始播放。
对 iOS 的 autostart 支持参数的引用已经包含在为内嵌视频提供的附加信息下的 MRAID 规范中。

支持此附录的容器必须将 autostart 支持添加到 web。

如果给定设备、操作系统或应用程序不支持 autostart, 则容器必须返回mraid 支持 ("vpaid")作为 "假", 使广告创意既可以播放非交互式版本的视频内容, 又允许用户手动启动视频播放, 或采取其他一些操作。

但是请注意, 需要手动播放的视频广告应该是一个边缘案例-广告商必须确保发布者/网络广告服务器的目标是不支持 autostart 的 OS 版本, 以确保这种情况发生。

### 9.2	点击行为与可见

当用户单击某个广告时, 该容器将在 app中打开一个新的浏览器窗口，例如：SFSafariViewController 或 WKWebView 在 iOS 或自定义标签的 Android 或使用 mraid 将用户发送到设备的默认浏览器open()方法.在这个新窗口中, 容器缺少任何方法来传达从 广告 的 web 到新的浏览器窗口的转换。同样, 容器不能指示用户何时关闭新的浏览器窗口并返回到第一个。由于在新的浏览器窗口中的盲点, 创意可能不知道什么时候暂停任何动画或视频元素。 MRAID 3.0 使用新exposureChange事件来报告曝光的变化。此事件将通过报告exposedPercentage和occlusionRectangle参数.
<pre>
点击过程应按以下方式管理:
1.	在请求要显示的 URL (这可以是从主广告单位, 或从互动参与状态), 广告单位调用mraid.open()。 
2.	容器在应用程序内或默认设备浏览器中打开一个新的浏览器窗口, 并激发exposureChange ()。这个新的浏览器窗口应该包含一个关闭按钮, 也可能包含其他控件, 如后退按钮或返回到 app 指示器。
3.	呼吁mraid.open(), 创意也必须点燃 VPAIDAdClickThru如果已向主机注册了 VPAID 对象, 以便集成层可以使用 VPAID 跟踪单击, 则为事件。
4.	如果广告暂停视频, 广告必须发射 VPAIDAdPaused事件.
5.	当新浏览器窗口关闭或用户从默认设备浏览器返回应用程序时, 容器必须发送exposureChange ()报告新exposedPercentage和新occlusionRectangle值.然后, 创意可以按设计恢复执行。如果视频播放恢复, VPAIDAdPlaying必须发送事件。
</pre> 
### 9.3	计数印象

MRAID 和 VPAID 是管理广告和移动应用程序或移动 web 应用程序之间交互的技术规范。两个规范都不作为测量指南。但是, 这两种规范都是为支持测量准则而设计的。 

当广告是使用 VPAID 事件来统计印象的视频时, 报告必须反映出对数字视频广告印象的最新实验室指南的遵守情况。

以下摘自数字在-流视频印象 测量准则: 

只有当广告计数器 (日志记录服务器) 接收并响应来自客户端的跟踪资源的 HTTP 请求时, 才可以计算出有效的数字视频广告印象。计数必须发生在流的启动后, post-buffering, 而不是链接的数字视频内容本身。 

具体地说, 在启动缓冲区时不应进行度量, 而应该在广告本身开始出现在用户的浏览器上 (最接近于看到的机会) 时进行度量。 

必须使用 VPAID 来计算流式视频广告的印象

AdImpression事件.如果广告被视为一个丰富的媒体广告, 印象可以算在adload使用 MRAID 的响应。在 MRAID, VPAIDAdImpression不需要事件, 并且 ad 容器必须等待它。

MRAID 的视频广告, 可以计算使用 VPAID 事件, 只是那些中断的内容和填充大多数的广告容器, 如间隙视频广告。MRAID 广告与视频组件, 运行内联必须使用 MRAID 事件计数广告。

下表列出了在 MRAID 广告中包含视频组件的六常见方案, 并指定了 VPAID 可用于计算视频印象的时间。
			
格式 	|说明或示例 	|MRAID placementType 	|报告 VPAID 事件？ 
-----|-----
视频间隙, non-dismissible 	|例如：pre-app 的广告或视频之间的间隙之间的两个级别的游戏 |	interstitial  |	是的 
skippable |例如：在 iPad 上的一个640x480 位置, 它占据了超过3/4 的屏幕并在视频内容之前播放|interstitial  |	是的
带端卡的后滚|例如, 一个15秒的 post-roll 视频与交互式的终端卡, 显示和保持在屏幕上, 直到用户关闭广告 |	interstitial | 	是的
单击时播放视频的简单横幅  |报纸应用中的300x250 横幅 	|inline 	|不
在点击展开和播放视频的横幅 |一个320x50 的静态横幅, 在点击时调用 mraid.expand() 并在元素中播放视频<video>。视频结束后, 广告就崩溃了。对于用户来说, 经验与使用 mraid (playVideo) 的旗帜几乎是一样的;基本 tap-to-video</video> 	|inline 	|不 
一个横幅, 在点击扩展, 并提供了一个视频网格 |类似于以前, 但当扩大, 而不是立即播放视频, 创意包含了一个网格的海报图像, 为不同的视频。用户在关闭前可以选择和播放多次 	|inline 	|不 
 
 
## 10	术语词汇

在整个 MRAID 规范中使用了以下术语。

广告视图/容器:显示广告创意的约束区域。出版商要么将广告容器放在内容中 (用于内联放置), 要么放在内容上 (用于间质性的安置), 并呈现广告创意。 该容器提供屏幕上的区域、MRAID 控制器以及用于显示广告的基于 web 的视图。 广告 容器通常 (虽然不一定) 由 sdk 提供。应用程序可能包含来自单个 SDK 的多个 广告 容器。

关闭事件区域:关闭事件区域 是广告创意上的一个 tappable 区域, 它将导致 广告 返回到其默认状态 (在可扩展/resizeable 广告 的情况下) 或从屏幕上移除 (在间隙中)。

关闭指示器:关闭指示器是用户对关闭事件区域位置的直观提示。

控制器:提供 广告 设计器访问 MRAID 方法和事件的 JavaScript 代码。广告创意使用控制器来执行与 广告 容器的 advertisingrelated 交互, 并间接地与应用程序和设备。

与密度无关的像素:通过 MRAID API 在容器和创造性之间传递的所有长度值都是与密度无关的像素。

与密度无关的像素是从物理屏幕像素的抽象, 这意味着在不同屏幕密度的设备上简化应用程序和内容开发。

使用密度无关的像素意味着, 例如, 视网膜显示 iphone 和老式 iphone 将返回相同的尺寸/措施, 尽管有不同数量的物理像素。1密度独立像素对应大约1/160 英寸 (1 设备像素在设备与大约 160 DPI)。
 
在 iOS 上, 这些必须映射到 "点";在 Android 上, 以 "密度无关的像素"。

注意: 只有当视区比例为1.0 时, 一个与密度无关的像素才会匹配 1 CSS 像素。要在 CSS 像素和与密度无关的像素之间进行映射, 创造性必须使用以下公式:
css_pixels * viewport_scale = density_independent_pixels

内嵌广告:显示在屏幕上的广告, 伴随着其他种类的内容, 例如, 网页上的横幅或应用程序。

间隙广告:在内容顶部显示的完整页面模式广告--"路障" 或 "叠加"。必须取消该广告, 用户才能返回到发布者的内容。此类广告可能出现在游戏级别、视频剪辑或其他动态内容之前或之后。(一个广告, 是 in-between 网页, 并在许多杂志的应用, 被认为是一个内嵌广告下 MRAID。

物理像素:设备屏幕上的实际像素。 例如, retinadisplay 的 iPhone 测量960x640 物理像素。 MRAID API 长度值总是以密度无关的像素 (上面定义的) 而不是物理像素来计算的。

sdk:软件开发工具包。 可重用的代码块 (库) 集成到 publisher 应用程序中, 以启用广告/广告容器。 一个 SDK 本身不是一个可视化组件。

Webview:显示广告创意的基于 html 的查看器。web 用于执行 HTML 和 Javascript 启用的广告的渲染。
 
![](http://oz3on0sof.bkt.clouddn.com/ab.jpg)
 
## 11	附录: W3C CalendarEvent 接口

取自: W3C 日历 API, 4.3 和4.4 节

W3C 2011年4月19日工作草稿这个版本:
<pre>
http://www.w3.org/TR/2011/WD-日历-api-20110419/ 最新发布版本:
http://www.w3.org/TR/calendar-api/ 最新编辑的草稿:
http://dev.w3.org/2009/dap/calendar/ 编辑:
理查德帝, Opera 软件作为A 
苏雷什 Chitturi运动研究 (RIM) 
版权 ©2011W3C® (麻省理工学院, ERCIM, 京), 保留所有权利。W3C责任, 商标 和文档使用 规则适用。
</pre>  

### 4.3CalendarEvent接口
CalendarEvent接口捕获日历事件对象。
当前使用 DOMString 的日期和时间是已知不足 用于表示带有时区的事件。该小组正致力于解决这一缺陷, 研究 TZDate 对象的开发, 以解决这一问题。
[NoInterfaceObject] 接口
```
CalendarEvent { 
    readonly attribute DOMString           id; 
             attribute DOMString           description;              attribute DOMString?          location;              attribute DOMString?          summary;              attribute DOMString           start;              attribute DOMString?          end;              attribute DOMString?          status;              attribute DOMString?          transparency;              attribute CalendarRepeatRule? recurrence;              attribute DOMString?          reminder; 
}; 
```
### 4.3.1 属性

描述类型 DOMString 事件的描述。

{描述: "与 Joe 的团队会面"}没有例外。 
 
结束类型 DOMString, 可为 null

事件的结束日期和时间。有效的日期或时间字符串.

{结束: ' 2011-03-24T10:00:00-08:00 '}//事件结束于 2011年3月24日 @ 6pm (UTC)
没有例外。 
 
id类型 DOMString, 只读
给定 CalendarEvent 对象的全局唯一标识符。每个
从日历引用的 CalendarEvent 必须包含非空 id 值。
当日历事件添加到日历中或在其中出现时, 实现必须维护此全局唯一的资源标识符。
实现可以使用 IANA 注册的标识符格式。该值也可以是非标准格式。
没有例外。 
 
位置类型 DOMString, 可为 null

事件位置的纯文本说明。

{位置: "呼叫 # + 4402000000001"}没有例外。 
<pre>
复发的类型CalendarRepeatRule、可空
此事件的重复或重复规则
{重复周期: {频率: "每日"}//事件每天发生, 从不过期 {定期: {频率: "每周",//事件每周发生..。
daysInWeek: [2, 4],//... 每星期二和星期四
过期日期: "2011-06-11T12:00:00-04:00"}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "每周",//事件每周发生... 每星期三
(如果我们说 "开始" 属性是 2011年3月24日 @ 2pm (星期三)
上面显示, 不提供 daysInWeek 属性)
过期日期: "2011-06-11T11:00:00-05:00"}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "每月",//事件每月发生... daysInMonth: [-5],//每月月底前5天 
到期日期: "2011-06-11T20:00:00 + 04:00"}}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "每月",//事件每月发生... 在每个月的第二十四天
(如果我们说 "开始" 属性是 2011年3月24日 @ 2pm
上面显示, 不提供 daysInMonth 属性)
到期日期: "2011-06-11T20:00:00 + 04:00"}}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "逐年",//事件每年发生... 在每年3月的第二十四天
(如果我们说 "开始" 属性是 2011年3月24日 @ 2pm
上面显示, 不提供 daysInMonth 属性)
到期日期: "2011-06-11T16:00:00 + 00:00"}}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "逐年",//事件每年发生... daysInMonth: [24] 每第二十四天..。
monthsInYear: [3, 6],//... 在每年3月和6月
过期日期: "2011-06-11T16:00:00Z"}//事件过期时间为 2011年6月11日 @ 4pm (UTC)
{重复周期: {频率: "逐年",//事件每年发生... daysInYear: [168]//////. 每年第168天到期: "2011-06-11T21:45:00 + 05:45"}}//事件过期时间为 2011年6月11日 @ 4pm (UTC)没有例外。 
 
提醒类型为 DOMString, 则为事件提醒。
此属性可以指定为正有效的日期或时间字符串.
, 表示 one-time 提醒或以毫秒表示的负值, 表示相对关系与日历事件的开始时间。
建议使用相对提醒来设置经常性事件的提醒。
{提醒: "2011-03-24T13:00:00 + 00:00"}//提醒一次在 2011年3月24日 @ 1pm (UTC)
{提醒: "-3600000"}//在每次发生此事件之前提醒1小时没有例外。 
 
开始类型 DOMString
事件的开始日期和时间。有效的日期或时间字符串.
{开始: "2011-03-24T09:00-08:00"}//事件开始于 2011年3月24日 @ 5pm (UTC)
没有例外。 
 
状态类型 DOMString, 可为 null
用户的事件状态的指示。
此参数可以设置为下列常量之一:
"待定"、"暂定"、"确认"、"取消"。{状态: "待定"}//事件正在等待用户操作没有例外。 
 
摘要类型为 DOMString, 则为事件的摘要可为 null。
{摘要: "议程: \n \n\n 介绍 \n AoB"}没有例外。 
 
透明度类型 DOMString, 可为 null
要为事件设置的显示状态的指示。
此参数可以设置为下列常量之一:
"透明"、"不透明"。
{freebusy: "透明"}//标记事件在日历中透明没有例外。 
 
</pre>
