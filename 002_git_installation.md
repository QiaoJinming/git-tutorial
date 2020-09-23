### git 安装与配置文件

---

> 成文时间：2020-09-14
>
> 参考地址：[GIT--fast-version-contro](https://git-scm.com/book/zh/v2)
>
> 阅读软件：Typora(Catfish主题)
>
> 联系作者：qiao_jinming@foxmail.com
>
> 文章作者：乔金明

---



##### 1. 如何使用git

- 使用git通常有多种方式，例如命令行模式，GUI（图形用户界面）模式，推荐使用命令行模式
  - 只有命令行模式才能够使用全部git命令
  - GUI为使用方便通常会封装一系列命令，但是遇到问题时发现解决问题很困难，反之命令行模式则很难出现这种问题
  - GUI形式各异，迁移后需要熟悉新的操作，但是命令行操作则可以避免这种情况，有GUI就一定可以使用命令行，会用命令行即可使用GUI，反之不然
- 不同系统下的一些终端
  - unix：基于unix的系统，诸如MacOS，Ubuntu，Centos，都可以使用本身的终端Terminal
  - win：Windows系列系统可以使用自带的cmd，powerShell等，推荐使用第三方开源终端工具cmder



##### 2. git安装

- Linux and Unix，如果需要权限增加相应的权限命令即可，以下仅以常用的系统作为举例，实际安装中请以需要安装git版本与当前系统版本进行选择，[git在不同Linux系统的安装命令](https://git-scm.com/download/linux)

  ```shell
  Debian/Ubuntu
  # apt-get install git
  
  Fedora
  # yum install git (up to Fedora 21)
  # dnf install git (Fedora 22 and later)
  ```

- MacOS，Mac系统可以以以下三种方式进行安装，[git在MacOS系统的安装命令](https://git-scm.com/download/mac)

  - homebrew方式：homebrew是mac下的包管理器，相当于ubuntu下的apt，如果已经具有了brew环境，可以直接通过命令行brew install git进行安装
  - 二进制方式：下载二进制安装包，与其他dmg软件安装相同方式进行git安装
  - 图像化方式：直接进行git图像桌面的安装，下载安装包并安装即可，[地址](https://desktop.github.com/)
  - 其他方式：例如通过Xcode进行安装，通过编译源码进行安装，这些方式使用较少，全部介绍意义不大，有兴趣可以独立了解

- Windows，win系统可以以下两种方式安装，[git在Win系统的安装方式](https://git-scm.com/download/win)

  - 二进制方式：直接下载安装方式链接中的安装包安装即可
  - 图像化方式：直接进行git桌面安装，下载安装即可，[地址](https://desktop.github.com/)

- 源码安装，源代码安装可以得到最新的版本，因而会有部分人觉得更加实用，但实际上二进制方式虽然稍落后于最新版本，但本身的差异并不明显，而且源码安装相较而言更加麻烦，不仅需要进行必要依赖搭建而且需要编译安装，更容易出现问题，所以这里不再介绍各种系统下的git源码安装方式



##### 3. git配置文件位置与查看

- git可以修改配置文件来进行相关参数的修改，同时git也提供了一组命令来进行配置文件的修改

- 配置文件路径

  - linux中常见位置
    1. 系统级配置文件，即为所有用户的配置，位于/etc/gitconfig下
    2. 用户级配置文件，即为当前用户的配置，位于~/.gitconfig或者~/.config/git/config下
    3. 项目级配置文件，即为当前项目的配置，位于项目根目录中的.git/config下
  - Windows中常见位置
    1. 用户目录中，位于C:\Users\\$USER\\.gitconfig下
    2. 安装目录中，位于安装目录的/etc/gitconfig下
  - 配置文件的作用顺序，距离项目越近，优先级越高，例如项目级配置优先级大于用户级配置，因为配置文件所配置的范围越大，其粒度也就越粗，就越像通用配置文件，通用文件当然没有独立配置文件的优先级高

- 可以通过以下命令查看所有的配置以及它们所在的文件

  ```shell
  $ git config --list --show-origin
  ```


