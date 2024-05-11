<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [前言](#前言)
- [前期准备](#前期准备)
  - [视频下载](#视频下载)
    - [直播源](#直播源)
      - [ffmpeg](#ffmpeg)
      - [OBS](#obs)
    - [视频源](#视频源)
      - [YouTube-dl (Linux)](#youtube-dl-linux)
      - [缓存视频合并 (Android)](#缓存视频合并-android)
  - [素材制作](#素材制作)
    - [相关知识收集](#相关知识收集)
      - [歌曲信息](#歌曲信息)
      - [歌词注释](#歌词注释)
    - [封面图片处理](#封面图片处理)
      - [B 站封面下载](#b-站封面下载)
      - [GIMP 使用](#gimp-使用)
- [视频制作](#视频制作)
  - [简单剪辑](#简单剪辑)
    - [ffmpeg](#ffmpeg-1)
    - [Olive](#olive)
  - [字幕制作](#字幕制作)
    - [Aegisub](#aegisub)
- [后期压制](#后期压制)
  - [压制参数](#压制参数)
    - [视频码率](#视频码率)
  - [压制软件](#压制软件)
    - [ffmpeg](#ffmpeg-2)
    - [HandBrake](#handbrake)
- [后记](#后记)

<!-- /code_chunk_output -->

# 前言
最近我在 DD 时听到了一首我非常喜欢的歌 
【waku 麻吉】第二期--《惑姬的酒馆》
http://www.bilibili.com/video/av78489736
这期节目的中间惑姬 Waku 翻唱的一首《Bartender Angel》 
一听就爱上了。有种想要单曲循环的冲动。但是这首歌并没有人剪辑出来。而且组里制作好的成品会加上一个片头。感觉会影响我单曲循环的感觉。所以我决定自己把这段视频剪辑出来，并且烤了 
所以这次要介绍的是我如何从零开始学习视频制作 
注：本文所使用的软件全部为开源软件，并且全部支持 Linux 系统 
# 前期准备
## 视频下载
首先在制作字幕之前，需要先获取原视频。
### 直播源
#### ffmpeg
如果你想要录制直播素材，可以使用我们万能的 ffmpeg 
首先在直播页面获取视频推流链接 
然后在命令行使用以下命令进行下载 

    ffmpeg -i "视频链接" -c copy output.mp4

要结束录制按 `Q` 即可
#### OBS
如果你想要包含直播弹幕一起录制的话可以使用 OBS 进行录制 
首先在设置页面调整好视频录制的参数 
将在捕捉源里添加浏览器页面 
然后点击开始录制即可 
### 视频源
#### YouTube-dl (Linux)
但是很明显，我已经错过了直播。只能从录播中获取
在电脑下载视频可以使用 YouTube-dl 工具 
常用使用方式：
1.下载视频

    youtube-dl 视频链接
![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/youtube-dl.png) 

2.自动下载最高画质视频 (YouTube)

    youtube-dl -f best 视频链接

3.下载视频中的音频

    youtube-dl -x 视频链接

#### 缓存视频合并 (Android)
首先在 B 站客户端缓存你想下载的视频 
打开应用，选择你想下载的视频 
点击保存即可 
![缓存视频合并](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Screenshot_20200129011044.png)

## 素材制作
### 相关知识收集
#### 歌曲信息
查询了一下这首歌的信息，也是有点意外的。专辑的年龄比我大 
在电台里惑姬也提到，这首歌是翻唱的。于是我也查到了英文原版的一些信息 
中文翻唱版
![好想谈恋爱-专辑封面](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/%E5%A5%BD%E6%83%B3%E8%B0%88%E6%81%8B%E7%88%B1-%E4%B8%93%E8%BE%91%E5%B0%81%E9%9D%A2.jpg)
《Bartender Angel》
歌手：范晓萱
专辑：好想谈恋爱
发行时间：1996.12.1
英文原版
![点击编辑标题](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Life-%E4%B8%93%E8%BE%91%E5%B0%81%E9%9D%A2.jpg)
《Gordon's Gardenparty》
歌手：The Cardigans
专辑：Life
发行时间：1995.3.1
#### 歌词注释
这首歌比较有趣的一个地方在于，提到了很多款酒的名字 
用注释的方式标注出来，可以让有兴趣的观众了解一些相关的小知识 
BARTENDER ANGEL
词：何庆远
曲：Svensson Peter、Persson Nina
颓废 闷 灰暗
我的舞台 Shaking wine

>Wine：Wine 是在 x86、x86-64 容许类 Unix 操作系统在 X Window System 运行 Microsoft Windows 程式的软体。
![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/WINE-logo.png)

>这条注释是私货，因为红酒太过常规。大家都已经有了解，没必要介绍。但是 Wine 这个软件应该是没什么人知道 

后现代浪漫
赶走遗憾
Shaking here
shaking there
火热辣辣 Martini
>Martini：乾马天尼（Dry Martini），是一款琴酒与不甜香艾酒调制的鸡尾酒，以橄榄或扭转柠檬皮做装饰，马丁尼被国际调酒师协会收录为经典鸡尾酒（the Unforgettables） 
配置方法
60 毫升琴酒
10 毫升不甜香艾酒
将材料与冰块放入搅拌杯，以搅拌法混合均匀，滤冰倒入冰镇马丁尼杯，再以扭转柠檬皮或绿橄榄做装饰

Margarita 的神秘

>![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Margarita.jpg)
玛格丽塔（Margarita）是一种用龙舌兰酒配制的鸡尾酒，以龙舌兰酒、柠檬汁和君度橙皮酒等成分兑成的，其杯口上通常粘有一层细盐（这是因为口中有一点盐味时龙舌兰酒的酒味会更好）。在炎热的夏季适合作为餐前酒。
配制方法
35ml 龙舌兰酒，
20ml 君度橙皮酒
15ml Lime 汁，
放入摇酒壶摇匀。
将鸡尾酒杯杯沿用柠檬片蘸湿，
将蘸湿的杯子在细盐面中蘸一下，沾上一层“盐霜”，
把摇好的酒倒入有盐边的杯子。
有时也可加冰块和柠檬皮。

[玛格丽特维基百科页面](https://zh.wikipedia.org/wiki/%E7%8E%9B%E6%A0%BC%E4%B8%BD%E5%A1%94?wprov=sfla1)

怎么 enjoy 最过瘾
bartender angel 告诉你
把苦涩 V.S 甜蜜
渴望 笑 眼神
酒精作怪 Sexy night
背对着伤心
今天不是 Lonely night
Shaking wine
Just for lady Gintonic

>![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Gin%20and%20Tonic%20with%20ingredients.jpg)
琴汤尼（Gin Tonic），是以金酒为基础的调酒里面知名度最高的一种饮品。
配制方法
做法 1：dry gin（干杜松子酒） 45ml +cut lime（酸橙片） 1 个+Tonic Water（汤尼水）适量
做法 2：DRY GIN 和 TONIC WATER，依照酒和 TONIC WATER 一比八（从 1 比 8 到 2 比 5 之间的任何比例都是可以的）的比例的搅拌均匀后，将混合液倒入装满冰块的杯子，扔进一片新鲜的切片柠檬就可以了
做法 3：杯子装入六分满冰块，量琴酒 1 又 1/2 oz 倒入，tonic water 加至八分满。搅拌均匀后放入调酒棒；可将柠檬片轻抹杯口丢入。
[Gin & tonic 维基百科页面](https://en.wikipedia.org/wiki/Gin_and_tonic?wprov=sfla1)

Taquila 让你热情

>![龙舌兰酒](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Tequilas.JPG)
龙舌兰酒（西班牙文：Tequila），是墨西哥产、使用龙舌兰草的心（Piña，在植物学上，指的是这种植物的鳞茎部分）为原料所制造出的含酒精饮品，属蒸馏酒一类。
龙舌兰酒是调酒界最常用到的六大基酒之一（其他五种则是兰姆酒，伏特加，威士忌，白兰地与琴酒），通常在一些口味厚重的调酒里面都可以见到其身影。
[龙舌兰酒维基百科页面](https://zh.wikipedia.org/wiki/%E9%BE%8D%E8%88%8C%E8%98%AD%E9%85%92?wprov=sfla1)

怎么 enjoy 最过瘾
bartender angel angel 告诉你
Bartender give you everything
B52 high 到底

>![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Cocktail%20b52.jpg)
B-52 是鸡尾酒中喝法比较独特的一种，要配上短吸管，餐巾纸和打火机。喝的时候把酒点燃，用吸管一口气喝完，可体验到先冷后热那种冰火两重天的感觉。
B-52 鸡尾酒要依次注入三种酒，先咖啡甜酒，然后甜酒，最后金万利（或黑朗姆酒），在星级酒店和一些专营性的咖啡店较为流行。

Bloody Mary 颠覆你

>![Bloody Mary with cold drink in restaurant](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/Bloody%20Mary%20with%20cold%20drink%20in%20restaurant.jpg)
血玛丽（英语：Bloody Mary），又称迷人血玛莉，是一种可以在上午供应的，酒精含量较低的红色鸡尾酒。基本成分是伏特加、番茄汁和其他各种配料，如辣酱油、塔巴斯科辣椒酱、法式清汤、辣根、芹菜、橄榄、盐、黑胡椒、辣椒、柠檬汁、芹菜盐。因此也被许多人认为是世界上最难喝的鸡尾酒。

怎么 enjoy 最过瘾
bartender angel angel 告诉你
La La La Do Bi Do Bi Do......
### 封面图片处理
#### B 站封面下载
封面制作是必须的 
不管怎么说直接使用截图还是太磕碜了 
组内制作的这个封面是真的很好看 
但是作为组外人员如果直接拿来使用的话，感觉不太好 
还是拿来做一下参考，进行一些修改会好一些 
首先，我们需要将参考的图片下载下来 
复制 AV 号到这个网站
[b 站封面提取_bilibili 封面提取_av 号封面提取](http://www.galmoe.com/)
![](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/Screenshot_20200129154851.png)
点击提取即可

#### GIMP 使用
在 GIMP 中新建一个图片，参考下载好的图片进行绘制 

然后再加上一点点细节，一张封面图就完成了(此处的软件其实换成了krita) 

# 视频制作
## 简单剪辑
### ffmpeg
这里使用到的，依然万能的 ffmpeg 
首先使用 ffplay 播放

| 按钮 | 功能 | 
|:----:|:----:|
|Q，ESC|退出|
|F|全屏|
|P，SPC|暂停|
|w|切换显示模式（视频/音频波形/音频频带）|
|s|步进到下一帧|
|left/right|快退/快进 10 秒|
|down/up|快退/快进 1 分钟|
|page down/page up_跳转到前一章/下一章（如果没有章节，快退/快进 10 分钟）|
|鼠标点击|跳转到鼠标点击的位置（根据鼠标在显示窗口点击的位置计算百分比）|

找到需要剪辑的时间点，使用 ffmpeg 将片段剪辑出来  

    ffmpeg -ss 01:08:43 -to 01:12:00 -accurate_seek -i input.mp4 -codec copy -avoid_negative_ts 1 output.mp4

### Olive
如果不想使用命令行你也可以使用 Olive 来进行剪辑 

将视频导入

在对应的位置将视频剪切

导出

## 字幕制作
### Aegisub
![Aegisub-logo-large](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Aegisub-logo-large.png)
>Aegisub 是一个免费，跨平台且开源的用于创建和修改字幕的工具。您可以使用 Aegisub 轻松地通过音频制作时间轴，并使用多种功能强大的工具，来修改字幕的样式，同时您还可以看到实时的视频预览 

作为字幕制作软件，Aegisub 是非常优秀的。同类软件 Arctime 在便捷性方面会好一些。但是很遗憾的是在我的 Linux 里无法导入视频。只能无奈放弃 

首先我们将字幕的样式进行设置 
为了保证可读性，字体最好选用无衬线字体 
调整一下大小，正文字体完成 

复制一下正文字体，位置修改为左上角。字体大小改小。注释字体完成 

直接复制粘贴导入歌词 
左键设置字幕开始时间，右键设置结束时间 
并且通过Q、W、A、S，快捷键确认位置 

先将所有歌词打完轴，然后复制歌词行，填入注释内容 
将该行字幕样式设置为注释 

设置好注释后，开始K轴 
在音频条下方点开KTV模式 
点击字幕中未自动分开的文字 
调整每个字，使字幕与声音的时间对上 
此时如果播放的话可以看到字的播放其实是没有平滑移动的效果的 
右键，将 \K 改为 \KF 即可 

# 后期压制
## 压制参数
在 B 站的投稿界面可以看到投稿所需的参数 
### 视频码率
![](https://cdn.jsdelivr.net/gh/breathiness/breathiness.github.io/img/Screenshot_20200131105025.png)
## 压制软件
### ffmpeg
使用我们万能的 ffmpeg，可以快速地进行视频压制的操作 
压制 ass 字幕 

    ffmpeg -i input.mp4 -vcodec libx264 -preset medium -crf 23 -vf "ass=input.ass" output.mp4

### HandBrake
如果不想使用命令行，也可以选择 HandBrake 作为压制软件使用 
# 后记
上面提到的各种工具以及使用方法。都是我通过网上的各种免费文章、视频学习得到的 
这是一个获取知识的成本非常低廉的时代，你可以仅仅凭借网络上的知识熟练、甚至精通某些领域。而你所需要的需要付出的仅仅是去学习的兴趣，以及一些时间 
其实星也 seiya 老师的首播里说的其实是非常准确的 
「将兴趣转变为职业，就是要由消费者转变为生产者」 
即使是看 Vtuber 也可以让我们学到很多的知识 
尤其是现在这段时间，大家都出不了门 
刚好有大量的空闲时间来学习 
最好就别把时间给浪费了
