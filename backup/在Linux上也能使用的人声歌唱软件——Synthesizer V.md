
![7034ee2751c49341fc427c4122473607](https://user-images.githubusercontent.com/11361630/131871852-319615bb-f591-4910-9d21-c9e9be1a0ae5.jpg)

> Synthesizer V（简称 Synth V）是由以华侃如（Kanru Hua，sleepwalking）为首的 Dreamtonics Co,. Ltd. 团队开发的电子音声合成引擎（V 表示第五代）。该引擎采用了自主研发的基于人工神经网络及拼接合成算法的 LLSM （底层语音模型） 技术，仅使用少量采样数据即能生成自然的声音。
><p align="right">——<a href="https://zh.moegirl.org/Synthesizer_V">萌娘百科 Synthesizer V 条目</a> </p>

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [零、前言](#零-前言)
- [一、安装](#一-安装)
  - [1. Synthesizer V 编辑器](#1-synthesizer-v-编辑器)
    - [1.1 下载地址](#11-下载地址)
    - [1.2 安装说明](#12-安装说明)
      - [1.2.1 图形界面设置方式](#121-图形界面设置方式)
      - [1.2.2 命令行设置方式](#122-命令行设置方式)
  - [2. 声库](#2-声库)
    - [2.1 下载地址](#21-下载地址)
    - [2.2 安装说明](#22-安装说明)
- [二、配置](#二-配置)
  - [1. 设置快捷打开程序](#1-设置快捷打开程序)
  - [2. 设置中文界面](#2-设置中文界面)
  - [3. 数位音频工作站（DAW）挂载 VSTi 插件](#3-数位音频工作站daw挂载-vsti-插件)
    - [3.1 复制 VSTi 文件至相应路径](#31-复制-vsti-文件至相应路径)
    - [3.2 宿主端设置](#32-宿主端设置)
    - [3.3 SynthV 连接设置](#33-synthv-连接设置)
- [三、使用](#三-使用)
  - [1. 导入伴奏](#1-导入伴奏)
  - [2. 绘制音符](#2-绘制音符)
  - [3. 输入歌词](#3-输入歌词)
  - [3. 导出](#3-导出)
- [四、预告](#四-预告)

<!-- /code_chunk_output -->

# 零、前言 

本文使用Markdown格式写作完成，其他平台格式可能会有错误。推荐在博客查看。 
[个人博客链接](https://breathiness.github.io/#/posts/3) 
昨天我们刚刚~~攻略了大书库~~更新了 ZSH 简介。 
这期稍就微偏离一下预订的轨迹，跳过美化篇。直接进入音乐制作篇。 

![](https://img.moegirl.org/common/9/9e/%E7%9C%9F%E6%91%B8%E9%B1%BC.gif)

让我来介绍一下，如何在 Linux 系统内使用虚拟歌姬。

想必大家或多或少都有听说过初音未来、洛天依等虚拟歌手。她们那略带机械感的人声给人留下了非常深刻的印象。 
![enter image description here](https://img.moegirl.org/common/8/89/Hatsune.Miku.full.2020130.jpg)
她们的声音是通过一款名为 VOCALOID ~~术力口~~ 的人声歌唱软件。制作而成。  
![5b9aeafeaa006ee6c1121297b048bac5](https://user-images.githubusercontent.com/11361630/131871965-2262a841-3f98-4f72-95fb-6594a4dea987.jpg)

>~~顺带一提，我的 ID 的由来就是 VOCALOID 的十参中的呼吸声。~~
>~~呼吸声（BRE、Breathiness）~~
>~~数值越高，气声则会越大。~~

然而很遗憾的是，主流的人声歌唱软件 VOCALOID、UTAU、CeVIO 等并没有 Linux 版本。我在很长一段时间都是靠虚拟机来使用相关的软件。
![utau-nolinux](https://i.loli.net/2019/12/29/3f49ajiURXTFZuq.png)
但偶然间我在查找闇音レンリ的资料时，发现了一款名为 Synthesizer V 的软件。 
看了一下相关的视频，声音很自然。即使是无参也有非常不错的效果。确实有点强。 
然后在下载界面非常惊讶地看到居然有 Linux 版本。 
于是我就下载试用了一段时间，体验还挺不错。 

关于各引擎间的差别，可以看看 B 站的这篇专栏。
《【科普】SynthV 和 VOCALOID 和 UTAU 到底有何不同？（字数较多请注意）》
[https://www.bilibili.com/read/cv3594471](https://www.bilibili.com/read/cv3594471)

# 一、安装
在 Synthesizer V 官网的下载界面即可下载到 Synthesizer V 编辑器以及三个免费声库的安装包。

## 1. Synthesizer V 编辑器

### 1.1 下载地址

![](https://i.loli.net/2019/12/23/duAz6D5gy4qJcrs.png)

Windows (28 MB)
[![Windows 下载免费试用](https://img.shields.io/badge/Windows-%E4%B8%8B%E8%BD%BD%E5%85%8D%E8%B4%B9%E8%AF%95%E7%94%A8-%2315E879?style=for-the-badge&logo=windows)](https://synthv-download.oss-cn-hangzhou.aliyuncs.com/synthv-setup.exe)

Linux 64-bit (33 MB)
[![Linux 下载免费试用](https://img.shields.io/badge/linux-%E4%B8%8B%E8%BD%BD%E5%85%8D%E8%B4%B9%E8%AF%95%E7%94%A8-%2315E879?style=for-the-badge&logo=linux)](https://synthv-download.oss-cn-hangzhou.aliyuncs.com/synthv-editor.zip)

macOS (21 MB)
[![macOS 下载免费试用](https://img.shields.io/badge/macOS-%E4%B8%8B%E8%BD%BD%E5%85%8D%E8%B4%B9%E8%AF%95%E7%94%A8-%2315E879?style=for-the-badge&logo=apple)](https://synthv-download.oss-cn-hangzhou.aliyuncs.com/synthv-setup.pkg)

***

**Synthesizer V 编辑器 (Build 018)**

在独立编辑器中轻松创建多音轨项目，或通过 VST 接口将编辑器连接到 DAW（数字音频工作站）软件。自 2018 年八月发布技术预览版以来，合成引擎不断改进，声音更脆，失真更小。图形界面也引入了许多新功能，为您的下一个创作提供新的可能性。请参阅发布说明，查看完整更新列表。

与编辑器一同发布的还有暗亮配色方案、12 个预设声门效果和一个示例项目。

[Synthesizer V 安装说明](https://synthesizerv.com/resources/installation-guide-zh-cn.pdf)

>仅包含 Windows 版

* VST 是 Steinberg Media Technologies GmbH 的商标。

系统要求| |
------------ | -------------
处理器 | Intel Core 处理器或同等规格的 AMD 处理器
内存 | 1 GB +
操作系统 | Microsoft Windows 7 或更高规格 (32/64 bit)
Ubuntu | 16.04 或更高规格 (64 bit)
macOS | 10.11 (El Capitan) 或更高规格
可用硬盘空间 | 500 MB （若安装一个语音数据库）

**购买许可**
以 80 美元从零售商购买。
***
[![平行四界 （中国大陆地区）](https://img.shields.io/badge/%E5%B9%B3%E8%A1%8C%E5%9B%9B%E7%95%8C-%EF%BC%88%E4%B8%AD%E5%9B%BD%E5%A4%A7%E9%99%86%E5%9C%B0%E5%8C%BA%EF%BC%89-%2315E879?style=for-the-badge&logo=vue.js)](https://item.taobao.com/item.htm?id=584877681596)

>支持支付宝和大陆银行卡。

[![ANiCUTE （国际）](https://img.shields.io/badge/]ANiCUTE-%EF%BC%88%E5%9B%BD%E9%99%85%EF%BC%89-%2315E879?style=for-the-badge&logo=paypal)](https://www.anicute.com/pages/VOLOR)

>支持信用卡和 Paypal 付款。

* 可能有额外税率。

### 1.2 安装说明

官方提供的安装说明仅包含 windows 版本。 
所以这里简单介绍一下 Linux 版本的安装方式。虽然 Linux 版本并不能直接用包管理器来快速安装。但是安装方式也非常简单。只需要将 synthesizer-v-editor 文件设置为可执行文件即可。 

#### 1.2.1 图形界面设置方式

首先将下载好的压缩包解压到某个文件夹中。 
如果你的系统有自带的文件管理器的话可以在文件管理器中右键，在文件属性中将允许文件作为程序执行选项勾上。 

![synthv-作为程序执行](https://i.loli.net/2019/12/29/fExLv3StyZPwmUD.png) 

这时候应该就可以在文件管理器中双击来打开了。 
#### 1.2.2 命令行设置方式
但是上面的方法偶尔会有一些小问题。比如双击后不知道什么原因，完全没有反应。 
所以我通常会在命令行中设置。 

1. 在终端中移动到解压完成的文件夹
`
cd 公共/synthv-editor
`
2. 将文件设置为所有人都可执行
`
chmod a+x ./synthesizer-v-editor 
`

![synthv-chmod](https://i.loli.net/2019/12/29/knzBSVfvwRKbLXT.png) 

3. 运行
`
sh /home/breathiness/公共/synthv-editor/synthv-editor
`

## 2. 声库
### 2.1 下载地址
![](https://i.loli.net/2019/12/23/fOAM98FkEZeomYG.png)
**艾可**
**AiKO**

- Synthesizer V 正式版 首位中文虚拟角色歌手
- 对任何事情都充满干劲，虽然偶尔粗心大意，却不会因遇到挫折而垂头丧气，并且对每天都有一点进步的自己感到开心。
- 沾水钢笔的造型头饰，以及艾可代表色（#FDD000）为主体的大蝴蝶结，都隐藏着神奇的能力，墨水瓶造型的魔法耳机，据说能听到这世界所有形式的声音。

> 艾可为付费音源，可在平行四界淘宝店购买 

[![平行四界 （中国大陆地区）](https://img.shields.io/badge/%E5%B9%B3%E8%A1%8C%E5%9B%9B%E7%95%8C-%EF%BC%88%E4%B8%AD%E5%9B%BD%E5%A4%A7%E9%99%86%E5%9C%B0%E5%8C%BA%EF%BC%89-%2315E879?style=for-the-badge&logo=vue.js)](https://item.taobao.com/item.htm?id=584877681596) 
[![ANiCUTE （国际）](https://img.shields.io/badge/]ANiCUTE-%EF%BC%88%E5%9B%BD%E9%99%85%EF%BC%89-%2315E879?style=for-the-badge&logo=paypal)](https://www.anicute.com/pages/VOLOR)

![](https://i.loli.net/2019/12/23/Omgl19WphLBxqPi.png)
**爱莲娜 芙缇**
**Eleanor Forte**
Eleanor　光
Forte　强力、强音记号

- 第一款英语声库。曾经使用的开发代号：ENG-F1。
- 主要的形象是头与胸部的蝴蝶结上附着的封蜡，代表著书信的各种工艺。
- 在麦克风架与鞋子的底部都有蜡封章花样。代表着将人与人连接起来的牵红线，在小指上打上红线蝴蝶结。在裙子上有着钢笔笔尖的形状等等。
- 身为新技术的结晶仍保有古风。诚心、努力、择善固执。
>* 该释出的玄武声库为非完整体验版，不代表最终品质。

[![windows](https://img.shields.io/badge/Windows-95MB-%252315E879?style=for-the-badge&logo=windows)](https://res.animen.com.tw/synthv/eleanor-setup.exe) [![linux](https://img.shields.io/badge/linux-94MB-%252315E879?style=for-the-badge&logo=linux)](https://res.animen.com.tw/synthv/synthv-eleanor.7z) [![macOS](https://img.shields.io/badge/macOS-102MB-%252315E879?style=for-the-badge&logo=apple)](https://res.animen.com.tw/synthv/eleanor-setup.pkg) 
[![注册免费声库](https://img.shields.io/badge/免费注册声库-%252315E879?style=for-the-badge)](https://synthesizerv.com/zh-cn/download/form.html?product=eleanor-forte)

![character_genbu_pic](https://i.loli.net/2019/12/29/qESWBM9U6GXIwbe.png)
**玄武**
**GENBU**
- 日语男性声库
- 平常的性格比较粗暴，但是歌声温柔甜美。
- 总是会重重拿起轻轻放下，容易屈服的类型。
- 很会照顾人。

[![windows](https://img.shields.io/badge/Windows-98MB-%252315E879?style=for-the-badge&logo=windows)](https://res.animen.com.tw/synthv/genbu-setup.exe) [![linux](https://img.shields.io/badge/linux-89MB-%252315E879?style=for-the-badge&logo=linux)](https://res.animen.com.tw/synthv/synthv-genbu.7z) [![macOS](https://img.shields.io/badge/macOS-98MB-%252315E879?style=for-the-badge&logo=apple)](https://res.animen.com.tw/synthv/genbu-setup.pkg) 
[![注册免费声库](https://img.shields.io/badge/免费注册声库-%252315E879?style=for-the-badge)](https://synthesizerv.com/zh-cn/download/form.html?product=genbu)

![](https://i.loli.net/2019/12/23/XfibxY2JsdSFnWM.png)
**闇音レンリ**
**Yamine Renri**
- 日语女性声库，经授权由 Yuzuri 的 UTAU 版本重制。
- 她最喜欢星星和月亮，还有有花边的衣服。
- 浏览 [闇音的官方网站](https://renrivoice.wixsite.com/renri-voice) 以了解更多信息。
>* 该释出的闇音レンリ声库为非完整体验版，不代表最终品质。

[![windows](https://img.shields.io/badge/Windows-392MB-%252315E879?style=for-the-badge&logo=windows)](https://res.animen.com.tw/synthv/renri-setup.exe) [![linux](https://img.shields.io/badge/linux-386MB-%252315E879?style=for-the-badge&logo=linux)](https://res.animen.com.tw/synthv/synthv-renri.7z) [![macOS](https://img.shields.io/badge/macOS-392MB-%252315E879?style=for-the-badge&logo=apple)](https://res.animen.com.tw/synthv/renri-setup.pkg) 
[![注册免费声库](https://img.shields.io/badge/免费注册声库-%252315E879?style=for-the-badge)](https://synthesizerv.com/zh-cn/download/form.html?product=yamine-renri)

### 2.2 安装说明
在下载好声源后将压缩包直接解压到编辑器的文件夹，即可安装完成。 
![2019-12-12-221946_1920x1080_scrot](https://i.loli.net/2019/12/28/dMmnxrAKzG7Dvey.png) 
虽然此时已经安装完成，但还需要申请一个注册码。否则还是无法使用声源。 
在授权管理器页面的状态会显示未注册。 
![2019-12-12-220752_1920x1080_scrot](https://i.loli.net/2019/12/28/6vBQlgkbiSRIMKV.png)
进入注册免费声库的页面，填写你的一些信息。 
![2019-12-12-231628_1920x1080_scrot](https://i.loli.net/2019/12/28/zNxpKwcWM5TFOfb.png) 
之后注册码会以邮件的形式发送至你留下的电子邮箱。 
将邮箱中的注册码填入授权管理器中的激活窗口进行激活即可。 

# 二、配置
## 1. 设置快捷打开程序

按照前面的安装说明虽然可以正常打开 
但是这种情况每次要打开 synthv 都要先打开命令行，然后输入一大串文本。而且不能关闭终端，非常麻烦。 
于是我在我的 Fish 的配置文件中添加了这一行。Zsh 也是同样的写法。 
`
alias synthv="/home/breathiness/公共/synthv-editor/synthesizer-v-editor"
`
然后就可以通过在命令行输入 synthv 就能直接打开了。 
而因为我使用的是 i3wm 版的 manjaro。自带有配置好的 dmenu。直接按`super`+`D`即可输入`synthv`来打开软件了。 
>实际上只要输入名字中一部分就能定位到了。 

## 2. 设置中文界面 
在 settings 栏中选择 Preferences 选项。或者按快捷键`Ctrl`+`Alt`+`P` 

![synthv-setting](https://i.loli.net/2019/12/29/XdKAfjCbqGuwyEV.png)

## 3. 数位音频工作站（DAW）挂载 VSTi 插件 

虽然我很少会用到这种方式，但还是介绍一下吧。 

>此说明以 REAPER 作为演示宿主软件 
>REAPER 在 Linux 下的使用可以查看 @啦哆咪 的文章 
>[啦哆咪 用Linux做音乐](https://lado.me/)

### 3.1 复制 VSTi 文件至相应路径

在设置页面可以看到，REAPER 的默认 VST 文件夹为`/home/breathiness/.vst`以及`/home/breathiness/.vst3` 
![synthv-reaper-vsti 文件路径](https://i.loli.net/2019/12/31/jcfWeQhHTBiIC3A.png)

将 synthv 程序文件夹中后缀为 `.so` 的文件复制到上面的 VST 文件夹中，即可安装完成。
![synthv-reaper-vsti 文件复制](https://i.loli.net/2019/12/31/6u7vBQiFLCNlUPg.png)

### 3.2 宿主端设置 
在轨道中点击 `Fx` 按钮，然后在 VSTi 选项中选择 VSTi:Synthesizer V VSTi(Dreamtonics)(32 out) 
![synthv-reaper-reaper 设置](https://i.loli.net/2019/12/31/cs7om5guMjSLOz8.png)

此时还是 disconnected 的状态，并没有连接完成。此时需要记住右边 port:XXXXX 中的五位数字。 
![synthv-reaper-vsti 安装完成](https://i.loli.net/2019/12/31/Oo7R31CmX4JQslx.png)

### 3.3 SynthV 连接设置 
在 SynthV 的设置栏中选择“连接到插件宿主”，将之前记录下的五位数字填入端口号码。确认即可。 
![synthv-reaper-vsti 连接到宿主软件](https://i.loli.net/2019/12/31/4kXypSmCNu3Edwt.png)

此时回到 REAPER，显示 connected。就证明已经连接完成了。 
![synthv-reaper-vsti 连接完成](https://i.loli.net/2019/12/31/SDMrdofpwJLhPk8.png)

# 三、使用 
## 1. 导入伴奏 

通常我们会需要配合伴奏来制作人声。所以会先导入伴奏。 

>伴奏的格式需要为 WAV，MP3 是导入不了的。 

![synthv-导入伴奏](https://i.loli.net/2019/12/30/JVDPcGRK7lIfb9t.png)

## 2. 绘制音符 

鼠标双击即可在对应位置绘制音符。通过鼠标拖动可以调整音符的位置。 
在音符末尾拖动，可调整音符的长度。 
除了使用鼠标编辑，也可以使用 MIDI 键盘来进行输入。 

## 3. 输入歌词

双击音符即可修改那个音符的歌词，按 TAB 键可跳到下一个音符。 
也可以框选多个音符，然后右键选择输入歌词选项。可直接输入多个歌词。 
歌词支持直接输入文字或罗马音。 
![synthv-输入歌词 1](https://i.loli.net/2019/12/30/x3eNX9rKmu78iwR.png) 

## 3. 导出 

在项目栏选择渲染到文件。
![synthv-渲染](https://i.loli.net/2019/12/30/RXUAM8N5WO1ZxEg.png) 

渲染设定直接默认即可。 
![synthv-渲染 1](https://i.loli.net/2019/12/30/Q6j3HTKADShaCEw.png) 

>此时渲染的音频为不带伴奏的纯人声

# 四、预告 

下期我们介绍一下如何获取无人声伴奏，或者宿主软件（REAPER）的配置和使用方法。 
![audacity-伴奏导入](https://i.loli.net/2020/01/01/qtX1mvVzicsRAk7.png)

---
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享署名-非商业性使用-相同方式共享 4.0 国际许可协议</a>进行许可。