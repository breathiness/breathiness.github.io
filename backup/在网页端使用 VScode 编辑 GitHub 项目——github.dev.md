![github.dev-题图](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/github.dev-%E9%A2%98%E5%9B%BE.png)

[TOC]

## 简介

通常我在网页端查看代码时，会用到 [github1s](https://github.com/conwnet/github1s) 这个项目。  
这个项目可以通过在项目 URL 的 `GitHub` 后面 +1s 来快速打开在线版的 VScode .

![VS Code - GitHub1s](https://raw.githubusercontent.com/conwnet/github1s/master/resources/images/vs-code-github1s.png)

但是这种方式打开的 VScode 只能用于阅读源码。并且不能添加扩展。  
那么有没有一种方式可以直接编辑代码、支持添加扩展呢？  

答案是有的，而且这还是 GitHub 官方推出的功能。  
那就是 GitHub.dev 项目。  

- <https://github.com/github/dev>

>在任何存储库或拉取请求上按 `.` 键，或者将 URL 中的 `.com` 替换为 `.dev`，以直接进入浏览器中的 VS Code 环境。  
>
>这是一种编辑和导航代码的快捷方式。 如果您想一次编辑多个文件或在进行快速更改时利用 Visual Studio Code 的所有强大的代码编辑功能，它尤其有用。 有关更多信息，请参阅我们的 [文档](https://docs.github.com/en/codespaces/developing-in-codespaces/web-based-editor) 。  
![github.dev-简易使用](https://user-images.githubusercontent.com/856858/130119109-4769f2d7-9027-4bc4-a38c-10f297499e8f.gif)

在  `github/dev` 这个项目的第一次提交时间是 2021年8月20日 但是似乎并没有什么文章介绍。  

![GitHub.dev-上线时间](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E4%B8%8A%E7%BA%BF%E6%97%B6%E9%97%B4.png)

我找到这个功能还是在 codespaces 的介绍页面下方看到的一句话介绍。这个功能藏得还挺深的。  

![codespace-github.dev 介绍](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/codespace-github.dev%20%E4%BB%8B%E7%BB%8D.png)

### 快速打开

使用方式前面也已经提到了，直接在对应项目页面按 `.` 键即可。  
但是我在浏览器上是习惯使用 Surfingkeys 扩展（为浏览器添加 VIM 快捷键）。`.` 键已经被分配给了“重复最近一次操作”功能。  

虽然也可以直接在地址栏修改 `.com` 替换为 `.dev` 来进入。但是我还是选择了另外一种方式。  
使用油猴脚本增加按钮。  

[显示 Github.dev 按钮](https://greasyfork.org/zh-CN/scripts/431463-%E6%98%BE%E7%A4%BA-github-dev-%E6%8C%89%E9%92%AE)
>在 Github 网站顶部显示 Github.dev 按钮，Github.dev 是一个利用 VsCode Online 浏览代码的项目

![显示 Github.dev 按钮](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E6%B2%B9%E7%8C%B4%E8%84%9A%E6%9C%AC.png)

安装完成，刷新页面后即可在项目上方看到 Github.dev 按钮。

## 使用体验

进入网页版 VScode 后，操作方式与桌面版并无太大差别。你可以使用习惯的方式进行文件的编辑。  
但是网页版还是会有一些差距的。下面简单介绍一下差异的地方。  

### 设置同步

不知道是不是 BUG 虽然点击下面的同步选项可以弹出设置，但其实并不能同步桌面版的设置。  

![GitHub.dev-设置同步](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E8%AE%BE%E7%BD%AE%E5%90%8C%E6%AD%A5.png)

网页版是另外保存的一套设置。其他设备进入之后会自动同步。  

### 自动保存

相比起桌面版 VScode，网页版可能是考虑到网络问题，在文件修改之后会立刻进行自动保存。不会出现代表 `未保存` 的小白点。  

![github.dev-桌面版保存](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/github.dev-%E6%A1%8C%E9%9D%A2%E7%89%88%E4%BF%9D%E5%AD%98.png)

### 无需 pull

提交 `commit` 之后无需 `push` 操作类似于编辑本地仓库。

![GitHub.dev-修改内容后自动保存](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E4%BF%AE%E6%94%B9%E5%86%85%E5%AE%B9%E5%90%8E%E8%87%AA%E5%8A%A8%E4%BF%9D%E5%AD%98.png)

### 新增 issues

可以直接在 VScode 内新建 issues。  
最上方一行是 issues 的标题；  
第二行是受让人；  
第三行是标签；  

后面的就是正文部分了；  

![GitHub.dev-添加 issues](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E6%B7%BB%E5%8A%A0%20issue.png)

填写完成后点击右上角的 `√` 即可完成创建。  

不过只能进行新建操作。并不能进行现有 issues 的编辑。确实非常可惜。  

### 多平台支持

用网页版可以带来的优势就是可以在任何有现代浏览器的设备上使用。  
当然，在手机设备上的屏幕限制如果不使用桌面模式，基本是无法正常使用的。  

![github.dev-手机使用](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/github.dev-%E6%89%8B%E6%9C%BA%E4%BD%BF%E7%94%A8.png)

### 支持部分扩展

网页版 VScode 也可以添加扩展，并且也可以同步。  
但是并不是所有扩展都可以安装  

在扩展页面，暗色的扩展都是不支持安装的。而且在支持的那些扩展中也有一些带有感叹号的，这些在功能上会有部分限制。  
比如说 markdownlint 这个扩展就限制无法修改配置文件。  

![GitHub.dev-不支持部分扩展](https://raw.githubusercontent.com/breathiness/breathiness.github.io/master/img/GitHub.dev-%E4%B8%8D%E6%94%AF%E6%8C%81%E9%83%A8%E5%88%86%E6%8F%92%E4%BB%B6.png)

而最离谱的是连语言包扩展都不支持。只能用英文版。

## 总结

虽然 github.dev 目前还有各种各样的问题。依然比不上桌面端 VScode 的强大功能，但是总体来说还是非常好用的。  
使用方便、无需部署、无需付费、支持编辑文件、支持部分扩展……  
已经有非常充足的理由让人去使用了。  
