![Gmeek-image](https://cdn.sa.net/2024/05/20/wIOLKsEqAClXYt6.png)  

## 0 杂谈

个人博客（Weblog 或 blog）是一种在网络上发布的个人日记或出版物，用以分享个人的想法、经验、知识、评论等。它是一个平台，让个人能够在网上表达自己，记录生活点滴，或是就特定主题提供深入分析和见解。个人博客相当相比起其他社交工具，没有推送，也没有内容的限制，是个更加强调其私人属性的内容分享方式。  
传统的个人博客搭建需要有服务器、要买域名。在过去的门槛是比较高的。GitHub 后来推出了个非常好用的功能，是 GitHub pages。可以说是搭建个人博客最方便的方式之一了。域名和服务器都能直接白嫖。并且有很多成熟的项目可以直接调用，我之前搭建的个人博客就是使用的 mirror 博客框架。  
![Mirror-GitHub 主页](https://cdn.sa.net/2024/05/20/i9F8Ho5xreyEnag.png)  
mirror 相比起传统的方式接触代码和命令行的数量大大减少了。安装和后续维护简单，可以只在手机上用 termux 就能完成布置。后面就能通过在该仓库提交 issues 的方式来新建文章。  
这个工具搭建好的博客我是使用了很长时间的。在当时这个工具很好地解决了有无的问题。让我快速的开始了在博客上分享的过程。  
但是 mirror 在功能上其实是有缺失的。比如说缺少了切换夜间模式的功能。以及大部分个人博客都有的 RSS 功能。并且因为我搭建博客的时间比较早，GitHub 的 token 还是用的旧版本的。GitHub 有段时间会经常发邮件提醒我更新 token。这使得我一直很想替换掉 mirror，但一直以来却苦于没有什么好的替代品。直到这篇文章的主角登场。  

## 1 功能介绍

最近，一个叫 Gmeek 的博客框架吸引了我的注意。新建文章的方式依然是提交 issue，支持标签、支持评论、支持夜间模式、支持 RSS、支持使用个人域名、可自动更新版本。得益于 Github Actions 的存在，配置方式比起 mirror 还要更加简单。据官网的说法是：  

>一个博客框架，超轻量级个人博客模板。完全基于`Github Pages` 、 `Github Issues` 和 `Github Actions`。不需要本地部署，从搭建到写作，只需要 18 秒，2 步搭建好博客，第 3 步就是写作。

- [Demo 页面](http://meekdai.github.io/)
- [Gmeek 更新日志](https://meekdai.github.io/post/Gmeek-geng-xin-ri-zhi.html)
- [Gmeek 快速上手](https://blog.meekdai.com/post/Gmeek-kuai-su-shang-shou.html)

![Gmeek-官网图-light](https://cdn.sa.net/2024/05/20/etOc7VBribKkxgH.jpg)

看到如此符合我需求的工具，我果断就用起来了。实际体验下来，搭建和使用都是符合预期的方便。

## 2 安装方式

如果你是之前没有在 GitHub 建过个人博客的新人的话，那新建一个 Gmeek 博客的流程就相当简单了。跟官网的介绍说法一样，只要你有 GitHub 账号，就可以在两步后直接开始写作。甚至速通玩家来还能再压一下时间。具体流程就和官网介绍的一样。

### 2.1 从模板创建仓库

在登录了 GitHub 账号的情况下，点击 [通过模板创建仓库](https://github.com/new?template_name=Gmeek-template&template_owner=Meekdai)  
> [!NOTE]
>建议仓库名称为`XXX.github.io`，其中`XXX`为你的 github 用户名。
>

![Gmeek-template-New](https://cdn.sa.net/2024/05/20/fKVFx4tOSyMQkae.png)  

### 2.2 仓库设置调整

在仓库的`Settings`中`Pages->Build and deployment->Source`下面选择`Github Actions`。  

![GitHub Pages-config](https://cdn.sa.net/2024/05/20/OzhFHKlAJmfkxT6.png)  

这一步做完就算是部署完成了。下面按照正常流程开始写作即可。

### 2.3 开始写作

在 issue 页面点击绿色新建按钮即可开始写作。

![Create-issue-1](https://cdn.sa.net/2024/05/20/289r51gM6Gebj7q.png)  

> [!TIP]
> issue 使用的是 markdown 语法，推荐查看 GitHub 官方的教程：[基本撰写和格式语法](https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

issue 编辑相比起其他编辑器，有个很方便的功能。在 MarkDown 文件里如果想添加图片，通常来说需要在图床上先上传。之后再将对应的图片链接粘贴进来。但是在 issue 里可以直接拖入图片。编辑器会自动上传然后生成链接。相当方便。

![New-issue 增加标签](https://cdn.sa.net/2024/05/20/vsI1Po8j6mfAGXg.png)  

在编辑完成后有个非常重要的点。一定要记得**必须**添加一个`标签 Label`（至少添加一个）。

### 2.4 设置修改（非必须）

这样配置完成后网站名称和简介都是默认的。虽然不影响使用，但最好还是修改一下，可以体现这是谁的博客、主要内容是什么。
如果你是 GitHub 高手，使用 git 拉到本地来进行修改那当然不错。但如果你是新人，推荐直接在网页上编辑文件。点击配置文件→点击编辑按钮就能修改配置了。

![Gmeek-config-edit-1](https://cdn.sa.net/2024/05/20/XJALOzvQ6ZlVoCG.png)  

默认生成的文件只有 4 条必须有的设置，其他的设置可以根据 [官方教程](https://blog.meekdai.com/post/Gmeek-kuai-su-shang-shou.html) 配置文件段的说明添加。

![Gmeek-config.json-edit](https://cdn.sa.net/2024/05/20/WqL5UGo63pQPCEF.png)  

我增加的配置一个是网站的开始日期。配置后在底部可以看到此网站运行了多少天。
还有在文章底部增加了版权说明：我的文章内容都是用的 CC0，没有任何限制。如果你有其他需求协议需求，也可以看看共享协议官网的介绍 [About CC Licenses](https://creativecommons.org/share-your-work/cclicenses/)。

### 2.5 手动全局生成（非必须）

这个步骤就像是重启按钮。平时不使用也没什么问题。如果遇到什么不对劲的就可以重启一下。

通过 Actions->build Gmeek->Run workflow 按钮全局重新生成

![Run-Github Actions](https://cdn.sa.net/2024/05/20/t4UCaD32XsMJbHV.png)  

## 3 现有仓库升级（非正常流程）

如果你不是萌新。在之前已经有对应的仓库了要怎么办？是只能删除掉仓库重新从模板新建吗？这对我这种已经在 issue 里写了好几篇文章的人来说有点太麻烦了。而且我这个仓库还关系着我的北极徽章，那就更不想丢掉了。

![GitHub-Arctic Code Vault Contributor](https://cdn.sa.net/2024/05/20/i6qaR2kjpYbdOVP.png)  

而作者其实也提供了两种解决方案。首先是新仓库方案。如果你新建一个其他名称的仓库，其实也是可以使用 GitHub Pages 功能的。配置好后只需要在链接后增加新仓库的名称即可。

![Gmeek-Github-issue-1](https://cdn.sa.net/2024/05/20/xEJ3vud5nU1kaGB.png)  

这个方案的好处是可以不影响原本个人博客的功能。但坏处是链接变的长了一些。对我来说还有一个问题，我原本的 issue 又需要一篇篇搬过去。太过麻烦。  
第二种方式就更符合我的实际需求。直接在原本仓库进行升级。  

![Gmeek-Github-issue-2](https://cdn.sa.net/2024/05/20/eP9WYsFhqCOb4vx.png)  

- 从模板仓库复制配置文件
打开模板仓库，下载仓库的压缩包。

![Gmeek-template-zip](https://cdn.sa.net/2024/05/20/s15L9jlrvfKFHNU.png)  

本地解压后将这两个文件直接复制到我的仓库文件夹内。

![Gmeek-template-main-file](https://cdn.sa.net/2024/05/20/3rLxSaRYDTqOEzZ.png)  

这里面 img 文件夹放的是我文章使用的图片。虽然 issue 里可以直接上传图片。但我还是更喜欢在外部放图片。这样更方便后续对图片内容进行编辑。这些文件留着并不会对 Gmeek 的部署有影响。

- 上传 GitHub
在 VScode 内填写修改的信息。然后推送到 GitHub 即可。

![git-commit](https://cdn.sa.net/2024/05/20/kcLXgJnrjy9Wp2s.png)  

- 修改仓库设置以及运行 Github Actions
在仓库页面将设置改成 Github Actions，然后重新运行一遍后，打开网址就能看到我之前的文章全都正常显示了。

![breathiness.github.io](https://cdn.sa.net/2024/05/20/1OZzXPogWVYH3yw.png)  

这就出现了一个很有意思的现象：Gmeek 这个项目诞生于 2023 年 7 月 28 日，但使用了这个框架的博客文章却是在 2021 年写的。

## 4 其他功能

### 4.1 RSS

RSS 是我非常喜欢的一个功能。我基本上每天都会看通过 RSS 订阅的文章。Gmeek 是默认带有 RSS 功能的。在主页右上方复制 RSS 链接。在 RSS 阅读器内添加订阅即可。

![Inoreader-breathiness-RSS](https://cdn.sa.net/2024/05/20/KRZcdJHmv7if2g1.png)  

### 4.2 黑暗模式

黑暗模式也是我很喜欢的功能，Gmeek 上点击切换按钮就能修改了。

![Gmeek-dark-mode](https://cdn.sa.net/2024/05/20/lDtnGUcRe7B2u4E.png)  

### 4.3 评论

最下方可以为当前文章添加评论。评论账号使用 Github 账号登陆。

![breathiness-blog-commet](https://cdn.sa.net/2024/05/20/Md8u9nFJe2a1hNH.png)  

## 5 总结

其他的博客框架可能有着更高的颜值、更好的自定义、更丰富的功能。但我依然推荐大部分人使用 Gmeek。作为断断续续写了几篇文章的人，就我自己的体验来说，一个足够简单的发布方式是可以切实提高写作欲望的。众所周知，博客的写作其实并没有一个强制性。这种情况下，任何写作路上的小小障碍都有可能让人简单的放弃。比如只有手机端的酷安、不支持 markdown 的 B 站文章、编辑器莫名其妙 BUG 的少数派……一旦遇到了问题其实很容易出现半途而废的情况。  
我笔记软件里的各种半成品长文估计也有十几篇了。最近长文接近年更的原因也是如此。很多时候一些原本打算写篇长文的话题，到最后总是变成一个动态简单分享一下就完了。而 Gmeek 很好的解决了这个问题。只要你的当前设备能连接到 GitHub，文章的编辑和上传就没有什么障碍。可以说是个能避免因为网站原因，而放弃发布文章的好博客框架。