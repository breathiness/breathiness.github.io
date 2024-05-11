- 2018-06-28 酷安文章存档

此系列文章在我的专栏「Linux 从入门到日常使用」更新，欢迎订阅 https://www.coolapk.com/dyh/1552 

# 前言

虽然我原本打算从桌面环境讲起，但是现在我的电脑不在身边。目前能用的只有手机还有树莓派。没办法完成截图和演示操作。

所以我会先介绍一下如何美化命令行。

这次作为演示使用的是 https://www.coolapk.com/apk/com.termux 

> Termux 是一个 Android 下一个高级的终端模拟器, 开源且不需要 root, 支持 apt 管理软件包，十分方便安装软件包, 完美支持 Python,PHP,Ruby,Go,Nodejs,MySQL 等。随着智能设备的普及和性能的不断提升，如今的手机、平板等的硬件标准已达到了初级桌面计算机的硬件标准, 用心去打造完全可以把手机变成一个强大的工具.

还有更多关于 termux 的详细介绍，推荐观看 @国光 写的这篇文章 http://www.sqlsec.com/2018/05/termux.html#more 

基本上关于 termux 的各种方面都有进行介绍，非常不错。

# 基础篇

## 0.简介

我们平时使用的系统里，默认的命令行界面可能是这样的。  
跟网络上一些截图相比似乎并不酷炫。一些视频里的命令行操作自己好像没办法实现。比如说 Tab 键补全时可以显示待补全的选项。  
这一点如果是 Archlinux 用户应该会有明显的体验。在 chroot 后命令行前的提示符会由彩色变成黑白。  
这是因为 Archlinux 的 live 系统中使用的是 zsh，而 Archlinux 的基本系统中却没有安装 zsh，而是更古老的 bash。  
那么这篇文章介绍的就是这款基础但是功能强劲的 shell 软件。

## 1.安装

zsh 在大多数发行版上都可以直接通过包管理器进行安装。  
apt install zsh #在 termux 中不需要 root 权限即可安装，如果是在电脑上会需要 sudo 命令或者切换到 root 用户。  
这时候就能输入 `zsh` 开始使用了。不过目前还不着急，我们可以一次性将所有的美化要用到的工具都全部安装好再切换 shell。

首先是 oh-my-zsh http://ohmyz.sh/ 

> oh-my-zsh 是一个著名的，社区驱动的框架，它拥有很多有用的函数，helpers，插件，主题，可以用来简化复杂的 Zsh 配置。

可以使用`wget`安装

sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

也可以使用`curl`安装

sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" 

如果你使用的是 https://www.coolapk.com/apk/io.neoterm 安装过程会简化一些。

只需要在「软件包」里搜索 zsh 就能快速找到 zsh 和 oh-my-zsh 并安装。  
安装完成后就可以实现很多功能并且能方便地美化了。  
这里再安装一个美化主题和两个插件，作为如何为 zsh 增加更多功能的演示。  
首先是一款非常漂亮，而且有着相当强大的自定义功能的 zsh 主题——Powerlevel9k http://dwz.cn/86HppE 

git clone http://dwz.cn/86Hpq5 ~/.oh-my-zsh/custom/themes/powerlevel9k

然后要安装的是一个提供了类似 Fish 的操作。让我们可以补全之前使用过的命令的插件——zsh-autosuggestions http://dwz.cn/86HpGg 

当然，用文字可能不太好理解，官方有一段演示大家可以看看。 https://asciinema.org/a/37390 

因为我们已经安装了 oh-my-zsh，所以并不使用演示中的安装方法。

git clone http://dwz.cn/86HpGg ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

然后是一款仿 Fish 的语法高亮插件——zsh-syntax-highlighting http://dwz.cn/86HpWh 

能更方便地看出当前输入的命令有没有错误。

git clone http://dwz.cn/86HpWh .git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

然后还可以再安装一个加强自动补全功能的插件——zsh-completions http://dwz.cn/86Hpre 

git clone http://dwz.cn/86Hpre ~/.oh-my-zsh/custom/plugins/zsh-completions

在安装完上面的几个插件后，你会发现命令行好像完全没有变化。  
这是因为我们仅仅是将插件下载安装，但是并没有在设置中开启。接下来就来介绍一下如何进行配置的修改。

## 2.配置

在有图形界面的系统中要修改配置是非常方便的。通常我们在软件中可以找到「设置」或者「首选项」的按钮。点开后就能修改各种设置了。那么在命令行这种完全找不到按钮的情况下，我们应该如何修改设置呢？  
在 Linux 系统中很多软件安装后会自动创建一个配置文件，我们只需要修改文件里的内容即可达到修改设置的效果。  
在安装好 oh-my-zsh 后，用文本编辑器打开`.zshrc`文件后就能看到很多的默认配置以及示例。  
我们如何让主题和插件生效呢？首先我们找到文件里的`ZSH_THEME="robbyrussell"`将引号里的内容修改为你想切换的主题名字。比如说 oh-my-zsh 自带的主题里我非常喜欢「gentoo」和「agnoster」

![adc3edaa91b3cc95c00befa3899ca36a](https://user-images.githubusercontent.com/11361630/134189528-6b6121b2-a7ad-4ae2-9d89-d42d43e411fc.jpg)

不过在这里我们需要的是换上我们之前安装的主题。

ZSH_THEME="powerlevel9k/powerlevel9k"

然后保存退出。当再次进入 zsh 时就能看到美化过后的样子。

![f7707a90473d9bfefd85fdcd15ea1dd3](https://user-images.githubusercontent.com/11361630/134189615-2a75b661-dc1c-4bf6-903a-0c9cc8a31d95.jpg)

然后是插件的启用方法。同样是打开`.zshrc`，找到

plugins=(
git
)

在括号内添加你需要使用的插件。比如说在 oh-my-zsh 自带的插件中我非常喜欢的 sudo 插件。双击`Esc 键`即可在当前命令的最前面添加`sudo`.关于更多的 oh-my-zsh 自带插件大家可以在 oh-my-zsh wiki 的 Plugins 页面 https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins 找到。

将之前下载的三个名字也写到括号内，然后在配置文件的随便一个地方增加一行。

autoload -U compinit && compinit

![74c6c1e276300dc9abf7b70ef9596bde](https://user-images.githubusercontent.com/11361630/134189769-fc4e2ddf-8d46-475b-b98f-e17732e87efd.jpg)

接下来再重启一下终端或者你可以执行命令 `source ~/.zshrc` 来生效修改的配置，而不需要重新登录。  
然后基础篇到此结束。

#进阶篇

只要看完基础篇就能开始正常的使用了。而进阶篇是给打算深入了解应用的读者观看。稍微介绍一些更深入的配置方法，或者进阶可以阅读的资料。

## 0.命令行快捷键

快捷键对日常使用来说非常重要，对于完全使用文字进行控制的命令行来说就更是如此。记住几个快捷键就能让命令的编辑过程变得顺滑很多

### 终端相关操作

0. `Ctrl` + `C`

看到这个快捷键大家的第一反应可能是复制。但是在命令行中代表的却是终止当前命令。比如说常用的`ping`指令，就需要用`Ctrl`+`C`来停止。

1. `Tab`

补全，包括命令、路径等各种东西。在默认的bash里补全是需要在已经没有其他补全选项时才能进行补全。而在zsh中按tab后会列出能补全的选项。然后就可以在各选项中选择自己需要的命令。

2. `Ctrl` + `D`

退出当前终端，同样你也可以输入exit。当然，如果你当前还有命令没有执行就不行。这个快捷键会变成文字编辑中的删除光标所在位置的文字。

3. `Ctrl` + `Z`

暂停当前进程，比如你正运行一个命令，突然觉得有点问题想暂停一下，就可以使用这个快捷键。暂停后，可以使用fg 恢复它。

5. `Ctrl` + `L`

清屏，相当于`clear`命令的效果。

### 文字编辑快捷键

大家可以去看看我之前也推荐过的视频教程。「Live Coding」第八期 把命令行玩「飞」起来 - by 柴锋 http://www.bilibili.com/video/av4337389 

这里就不做过多介绍了。

## 1.Zsh 配置

Zsh 的配置文件 `.zshrc` 其实还有很多有趣的玩法。

首先最常用的功能应该就是别名了。alias（别名）在 shell 中是非常常用的，它主要用于给命令起别名，简化输入。

比如说我就习惯将 ls 替换为 colorls。Color LS http://dwz.cn/86HpUK 会在后续的文章中介绍。

alias ls='colorls'

alias 的效果相当于直接将字符串替换过来，比较好理解。

关于别名还有一个比较有趣的用法。比如说我下面的这个例子，为`alias`加上`-s`后，当遇到后缀名为`.gz`的文件，就会自动将文件用 tar 解压。

alias -s gz='tar -xzvf'

还有就是在`.zshrc`里直接添加命令，会在每次打开时执行。

fortune-zh

这样每次打开都会输出一句名言，这就非常浪漫了。

然后我在电脑上使用时有时会在一些别的路径打开命令行，这时候不需要再输出名言。

[[ -e ./.zshrc ]] && fortune-zh

在这样设置之后在每次打开时会先判断当前目录有没有`.zshrc`文件，如果有就运行`fortune-zh`命令。

当然，`.zshrc`文件可以玩的东西还有好多。详细介绍推荐观看这篇《Zsh 开发指南》 https://github.com/goreliu/zshguide/blob/master/00_Zsh-%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97%EF%BC%88%E7%9B%AE%E5%BD%95%EF%BC%89.md 

## 2.Powerlevel9k 配置

Powerlevel9k 虽然表面上仅仅是个主题，但是实际上Powerlevel9k还是一个非常好用的主题编辑器。可以通过修改`.zshrc`文件来方便地修改主题样式。自定义出属于自己的主题。可以说是相当强大了。

不过我还是挺喜欢原来的主题的，所以我自己的自定义项却比较少，只有四条。

POWERLEVEL9K_CONTEXT_TEMPLATE="breathiness" 
POWERLEVEL9K_COMMAND_EXECUTION_TIME_THRESHOLD="0"
POWERLEVEL9K_RIGHT_PROMPT_ELEMENT=(time)

![f0e109dd5ed85163bea7f2ca4cf4ae0a](https://user-images.githubusercontent.com/11361630/134190003-bbb7d80f-063a-4429-a829-b4ea25c636b6.jpg)

可以在 Show Off Your Config https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config 页面中看到用户们自定义的各种各样的样式。

比如说下面展示的几种是我在 Show Off Your Config 页面中随便找的我比较喜欢的几种。

![4283bae3aa74a7ea295050be4adbaad1](https://user-images.githubusercontent.com/11361630/134190248-a9604085-15fc-4727-acb8-8a485b7284a4.jpg)

![13ff7bbf0c750c634d21e3f46aa952f1](https://user-images.githubusercontent.com/11361630/134190336-9d5e2245-61bc-4bbe-b3fa-193345d2f629.jpg)

![e79195221feda8462c2b53f9a1407472](https://user-images.githubusercontent.com/11361630/134190371-86b12e0a-8c6f-4fa3-b888-61f8c8e516ce.jpg)

可以参考一下或者直接拿来用。

设置教程可以参考一下Wiki上的介绍。Stylizing Your Prompt http://dwz.cn/86Hpsm 

我记得之前有个博客写过一个非常详细的教程，但是我忘记保存了……现在再去搜也找不到。希望有知道的酷友可以发一下地址。(或者自己写一篇)

# 广告时间

当然在 Termux 中使用Linux系统与真正的Linux系统还是有一些微妙的区别的。

如果想在手机上也能有更加纯正的Linux命令行体验也可以尝试购买一个服务器。

拥有一个服务器其实是一件非常方便的事情。在之后更新的教程中我也会介绍一些在服务器上非常简单就能部署的服务以及一些有趣的小玩意。敬请期待

还记得我在之前的文章 https://www.coolapk.com/feed/5742706 中介绍的腾讯云活动吗？现在又有新的活动了，上次没上车的酷友可以了解一下。

https://cloud.tencent.com/act/campus/group/detail?fromSource=gwzcw.1075736.1075736.1075736&group=32446 

# 抱怨时间

这次文章的更新也是跳票了好久，真的非常抱歉。这次的原因除了习惯性地把文章写的有点「大」。更加主要的原因还是出来工作加班……原先是说新人前几个星期是不需要加班。但是苹果那边需要一大堆的数据。然后搞得新人也要加班到很晚，每天基本都要凌晨才能睡觉。真的是没时间写文章。(讨厌苹果的理由+1)

现在都是抽午休还有搭班车的时间来写东西……希望这个项目忙完之后可以更加规律的更新吧。

最后还是惯例要抱怨一下酷安糟糕的编辑体验，不支持 markdown 这种老生常谈的话题就不吐槽了。将文章加图片简直是让我想摔手机……

参考资料：
Zsh - ArchWiki http://dwz.cn/86HpGP 
「Live Coding」第八期 把命令行玩「飞」起来 - by 柴锋 http://www.bilibili.com/video/av4337389 
Termux 高级终端安装使用配置教程 | 国光
http://www.sqlsec.com/2018/05/termux.html#more 
Zsh 开发指南 https://github.com/goreliu/zshguide/blob/master/00_Zsh-%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97%EF%BC%88%E7%9B%AE%E5%BD%95%EF%BC%89.md 
oh-my-zsh Wiki http://dwz.cn/86HpX3 
powerlevel9k Wiki http://dwz.cn/86HpXb