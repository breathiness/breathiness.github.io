
![524c56c35b5356205fa51c1c5c005052](https://user-images.githubusercontent.com/11361630/131866961-5228f62b-bec4-481c-abc6-e0d7155900a8.jpg)

## 前言
当 Windows 系统用户想要体验一下 Linux 系统，或者只需要使用 Linux 系统下的某几个应用时你会如何选择？  
是使用双系统？虚拟机？还是使用服务器？  
这几种方法显然都有一些不方便的地方。  
双系统可以带来完整的 Linux 体验，但是安装有些复杂，且切换系统需要重启电脑。比较麻烦。  

![a104e425ac027ec5292ce25aa4d12e91](https://user-images.githubusercontent.com/11361630/131867122-d34e1b61-7a19-46bd-9c3d-95837fbf7f6c.jpg)  

虚拟机同样能有完整的 Linux 体验，切换系统也比较方便。安装虽然比双系统简单，但是也同样需要比较多的步骤。  

服务器虽然使用方便快捷，用法多样。但是仅支持纯命令行，并且要钱。  

![69286ca999d67bde3e1148b1320e9f73](https://user-images.githubusercontent.com/11361630/131870023-8e4a412b-bb23-4345-a266-30c38b213971.png)

这些上手 Linux 的初期投入容易让人萌生退意。  
而 Windows10 系统自带的 WSL。就是非常方便的体验 Linux 系统的方法。基本可以做到开箱即用。  
只需要在功能页面打开 WSL，然后在商店下载需要的发行版即可。  
如果不使用商店也可以直接下载安装包。  

<https://docs.microsoft.com/zh-cn/windows/wsl/install-manual#downloading-distros>

![f5491367e8228b76b7d2af14e966ac7f](https://user-images.githubusercontent.com/11361630/131870106-f3804f94-6481-489a-8d13-51a2fe44e182.png)

但是我这里并不打算使用这种方式安装。这里主要有两个问题。  
1. 官方商店里的 Linux 发行版数量不多。而且缺少了我常用的 ArchLinux  
2. 在国内的网络情况，微软的下载速度很微妙。  

为了解决这些问题，我使用的方案是使用 Windows Terminal+ArchWSL  

## 安装

### ArchWSL 安装

![10a8fb29432dcf2e66da580c70789770](https://user-images.githubusercontent.com/11361630/131870192-d0d71367-0483-43b2-8022-fc13bb6ec2d4.png)

安装(with zip package)  
进入 ArchWSL GitHub 页面，进入发布页面。  

Releases · yuk7/ArchWSL · GitHub  
<https://github.com/yuk7/ArchWSL/releases>

选择下载压缩包。  
![8747a627bbf2a966d0c9df6e6cb203bc](https://user-images.githubusercontent.com/11361630/131870273-20d411bd-ae34-4e5b-91e3-1a054546ee68.png)

然后解压，打开 arch.exe 即可安装完成。  

![f6dd1a0b5ae83be5e8e150bc026c2d87](https://user-images.githubusercontent.com/11361630/131870322-e94e8a1a-4a18-4195-b03f-66521edc4ada.jpg)

安装完成后的配置我在后续应该会再出个教程。  

### Windows Terminal 安装

![e6d8df14189f531d5a785cd73fa53743](https://user-images.githubusercontent.com/11361630/131870408-48b91d5f-0278-4001-8a70-26dbfc2f362b.png)

如果你只需要体验 Linux 系统。安装好 ArchWSL 就足够了。但是，我想要让使用过程更加舒服一些。所以我选择的是微软官方开源的终端模拟器。  

在 GitHub 发布页面下载，双击打开即可安装。  

<https://github.com/microsoft/terminal/releases>
![3a937c30bfa3fd36ae45c9148597cd1d](https://user-images.githubusercontent.com/11361630/131870474-65c5201a-c0f2-4aee-89da-717b703b55a1.png)

打开后可以在上方选择到 ArchWSL，就能进入 Arch 系统了。  
更加详细的介绍可以查看少数派的这篇文章。  

新生代 Windows 终端：Windows Terminal 的全面自定义  
<https://sspai.com/post/59380>

在配置过程中，我与文章里不同的地方在于我没有使用 quicker 右键菜单我是直接修改的注册表。  

## ArchWSL 常见问题
### 移动位置后打开会出现闪退现象

虽然看起来 ArchWSL 是绿色软件，但实际上如果你移动 ArchWSL 的路径后是无法继续使用的。  
解决方法(机翻):  
通常，您不能移动已安装的文件夹，因为WSL实例使用注册表项。  
请卸载并重新安装。  
1.运行wslconfig / u Arch命令来卸载实例。  
2.删除rootfs和temp文件夹。  
3.重新安装。  

或操纵注册表项以更改路径。(HKCU\Software\Microsoft\Windows\CurrentVersion\Lxss{LxUID})  

![43c167d6ad9f0965fafa2984a0708cb8](https://user-images.githubusercontent.com/11361630/131870688-1d73ad0a-c1ba-4c89-8c69-7329aa4446c2.png)

### pacman 无法安装软件

要安装软件之前还需要运行以下命令，进行初始化 keyring  

sudo pacman-key --init  
sudo pacman-key --populate  