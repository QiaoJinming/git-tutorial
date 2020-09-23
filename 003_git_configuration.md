### git配置相关命令

---

> 成文时间：2020-09-15
>
> 参考地址：[GIT--fast-version-contro](https://git-scm.com/book/zh/v2)
>
> 阅读软件：Typora(Catfish主题)
>
> 联系作者：qiao_jinming@foxmail.com
>
> 文章作者：乔金明

---



##### 1. 常用简明配置命令

- 查看当前git版本

  ```shell
  git --version
  ```

- 显示帮助信息命令

  ```shell
  # 显示git的帮助命令，其中--all或者-a为可选项，增加后则打印所有可用的命令，如果加上verbose参数则同时输出介绍，这也是默认输出方式，可以使用no-verbose进行精简命令介绍输出
  git help [--all|-a] [--[no-]verbose]]
  
  # verb表示git下相关的命令，例如config，以下三种方式等价，都是查看相关git命令的帮助文档
  git <verb> --help
git help <verb>
  man git-<verb>
  
  # 如果使用-h参数，可以直接输出简明的帮助文档
  git <verb> -h
  
  # 以下三条命令分别为输出本地html帮助文档，man帮助文档，info帮助文档路径
  git --html-path
  git --man-path
  git --info-path
  
  # 输出所有的可以修改的配置参数，输出的为短命令列表
  git help -c|--config
  
  # 关于帮助信息的相关配置参数
  help.format  # 帮助信息的格式
  help.browser, web.browser, browser.<tool>.path  # 打开帮助信息的浏览器设置
  man.viewer, man.<tool>.path, man.<tool>.cmd  # man查看方式的相关路径与控制等设置
  ```
  
- 配置相关命令，每台计算机只需要配置一次即可对当前系统一直生效，可以在任何时候修改这些配置项

  ```shell
  # 安装完git后，需要进行的初步配置姓名与邮箱地址，否则无法进行提交操作
  git config --global user.name "xxx"
  git config --global user.email "xxx@xxx"
  
  # 选项命令，通过这些命令可以分别对系统、项目、全局等层级的配置文件进行修改
  --global  # 写入全局的项目中的git配置文件中，一次设置全局生效
  --system  # 写入系统中的git配置文件中
  --local   # 写入当前项目的git配置文件
  
  # 设置配置文件路径，而不是使用默认的配置文件
  git config -f|--file <file>
  
  # 获取某个配置参数的值
  git config --get <name>
  
  # 增加一个配置的参数与值的条目，第二条命令指的是覆盖文件中的参数与值的条目
  git config --add <name> <value>
  git -c <name>=<value>
  
  # 删除一个配置的参数与值的条目
  git config --unset <name> [value]
  
  # 配置git的文本编辑器，可以编辑提交时的提交日志记录
  git config --global core.editor <editor>
  
  # 配置帮助命令查看的浏览器相关参数
  git config --global help.format <web>
  git config --global web.browser <browser>
  
  # 输出全部的配置文件参数，第二条命令为输出指定的配置参数
  git config --list
  git config <name>
  ```

- 修改配置文件时，如果没有问题会返回正确码0并退出，否者将返回以下代码

  - 该部分或密钥无效（ret = 1）
  - 没有提供任何部分或名称（ret = 2）
  - 配置文件无效（ret = 3）
  - 配置文件无法写入（ret = 4）
  - 您尝试取消设置一个不存在的选项（ret = 5）
  - 您尝试取消/设置多行匹配的选项（ret = 5）
  - 您尝试使用无效的正则表达式（ret = 6）

 

##### 2. 详细配置帮助命令说明

- 本地命令

  ```shell
  git help git  # git命令的帮助文档
  git help help  # 帮助命令的帮助文档
  git help config  # 配置命令的帮助文档
  git help bugreport  # bug报告命令的帮助文档
  ```

- 在线命令

  - [git命令帮助文档](https://git-scm.com/docs/git)
  - [配置命令帮助文档](https://git-scm.com/docs/git-config)
  - [帮助命令帮助文档](https://git-scm.com/docs/git-help)
  - [bug报告帮助文档](https://git-scm.com/docs/git-bugreport)

