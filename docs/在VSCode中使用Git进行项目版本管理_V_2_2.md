# 在 VSCode 中使用 Git 进行项目版本控制

## 一. 版本控制

- 本节的主要目的是为了让读者了解版本控制的一些主要内容，包括版本控制的概念，意义以及常见的版本控制工具。通过本节内容，读者对版本控制将会有初步的了解。

### 1. 什么叫版本控制

- 版本控制是指对软件开发过程中各种程序代码、配置文件及说明文档等文件变更的管理，是软件配置管理的核心思想之一。

### 2. 为什么要进行版本控制

- 在软件开发过程，每天都会产生新的代码，代码合并的过程中可能会出现如下问题：
  - 代码被覆盖或丢失
  - 代码写的不理想希望还原之前的版本
  - 希望知道与之前版本的差别
  - 是谁修改了代码以及为什么修改
  - 发版时希望分成不同的版本(测试版、发行版)  
- 在软件开发的过程中，只需使用版本控制工具，就能解决上述的问题，这就是为什么要进行版本控制的原因。  

### 3. 版本控制的主要功能

- 可以随时回滚到之前的版本
- 协同开发时不会覆盖别人的代码
- 留下修改记录，以便随时查看
- 发版时可以方便的管理不同的版本  

### 4. 常见的版本控制工具

目前常用的版本控制工具主要是 SVN 和 Git :  
(1) SVN

- SVN 是 subversion 的缩写，是一个开放源代码的版本控制系统，通过采用分支管理系统的高效管理，简而言之就是用于多个人共同开发同一个项目，实现共享资源，实现最终集中式的管理。

(2) Git

- Git 是 Linus Trovalds 大神的作品，是一个开放源码的版本控制软件。与 SVN 最大的区别，就是分布式的管理。

(3) 使用选择

- 如果对访问控制、权限分配和代码安全性等要求比较高的，建议使用 SVN。
- 如果是分布式，多人开发，版本迭代比较快的项目，建议使用 Git 。

## 二. 工具介绍和使用

- 本节的主要目的是为了让读者了解在版本控制中常用的两个工具 Git 和 GitHub。通过本节内容，读者将会了解 Git 的基本使用以及了解 GitHub 的作用。

### 1. Git

(1) Git 简介
Git (读音为 /gɪt/ )是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。

(2) Git 安装

- [下载 git](https://git-scm.com/download/win) , 打开即可自动下载
![git downloading](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_downloading.png)
- 如果没有特殊要求，一路点击 next 即可  
![git setup](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_setup.png)
- [Git 安装选项说明](https://blog.csdn.net/crazy_cw/article/details/81629946)
  
(3) Git 三种状态
Git 有三种状态，你的文件可能处于其中之一：已提交（ committed ）、已修改（ modified ）和已暂存（ staged ）。 已提交表示数据已经安全的保存在本地数据库中。 已修改表示修改了文件，但还没保存到数据库中。 已暂存表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。
![工作目录、暂存区域以及 Git 仓库](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_three_status.png)

- Git 仓库目录是 Git 用来保存项目的元数据和对象数据库的地方。 这是 Git 中最重要的部分，从其它计算机克隆仓库时，拷贝的就是这里的数据。  
- 工作目录是对项目的某个版本独立提取出来的内容。 这些从 Git 仓库的压缩数据库中提取出来的文件，放在磁盘上供你使用或修改。  
- 暂存区域是一个文件，保存了下次将提交的文件列表信息，一般在 Git 仓库目录中。 有时候也被称作“索引”，不过一般说法还是叫暂存区域.  
  
(4) Git 常见命令

- git init
用 git init 在目录中创建新的 Git 仓库。 你可以在任何时候、任何目录中这么做，完全是本地化的。  
在目录中执行 git init，就可以创建一个 Git 仓库了。比如我们创建 example 项目：
  - 新建文件夹:example
  - 在文件夹 example 下打开 Git Bash ，输入 git init
  ![git init](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_init.png)你可以看到在你的项目中生成了 .git 这个子目录。 这就是你的 Git 仓库了，所有有关你的此项目的快照数据都存放在这里。  

- git add
git add 命令可将该文件添加到暂存区域，如我们在 example 项目里面添加 README.txt 文件。此时，该文件只是存储在工作目录。我们需要用 git add README.txt 命令，将文件添加到 Git 暂存区域。
![git add](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_add.png) 新项目中，添加所有文件很普遍，我们可以使用 git add . 命令来添加当前项目的所有文件。

- git status  
git status 命令用于查看项目的当前状态。  
该命令的时候加了 -s 参数，以获得简短的结果输出

- git commit
使用 git add 命令将想要快照的内容写入暂存区域， 而执行 git commit 将暂存区域的内容添加到 Git 仓库中。  
接下来，我们使用 git commit 命令将暂存区域的内容添加到 Git 仓库中。  
![git commit](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_commit.png)
使用 -m 选项以在命令行中提供提交注释。  
如果你觉得 git add 提交缓存的流程太过繁琐，Git 也允许你用 -a 选项跳过这一步。  
此时我修改了项目中的两个文件，使用 git commit -am 命令  
![git commit -a](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_commit_am.png) 
从图中可以看出，git commit -am 命令等于 git add . 命令加上 git commit -m 命令。

### 2. GitHub

(1) GitHub 简介
GitHub是一个面向开源及私有软件项目的托管平台，因为只支持 Git 作为唯一的版本库格式进行托管，故名 GitHub 。

(2) GitHub 作用
GitHub可以托管各种 Git 库，并提供一个 web 界面。

## 三. 计算器项目范例

- 本节将以计算器项目为范例（此计算器项目目前只是一个简单的软件项目，暂未加入版本控制功能，暂未存储到 GitHub 仓库），讲解 VSCode，Git，GitHub 联合使用前的一些准备以及从零演示如何将此项目加入版本控制功能和存储到远程 GitHub 仓库。本节主要分两部分进行讲解：

  1. VSCode，Git，GitHub 联合使用前的准备工作
  2. 将项目加入版本控制功能和存储到远程 GitHub 仓库的基本步骤

### 1. 必要准备

在演示之前，我们需要做一些准备工作，不然无法将 VSCode，GItHub 和 Git 联合使用。这些准备工作，只需进行一次即可，以后进行项目版本控制无需再做。

准备工作主要有 3 部分：

  1. Git 初始化配置
  2. 添加 SSH Keys
  3. 在 VSCode 中使用 Git工具配置

(1) Git 初始化配置
在 Git Bash 命令行中输入：

```python
git config --global user.name "Your Name"
git config --global user.email "email@example.com
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。  

(2) 添加 SSH Keys
SSH Keys 能让你方便的登录到 SSH 服务器，而无需输入密码。

1). 打开 Git Bash
2). 在 Git Bash 中输入 ssh-keygen -t rsa -C "your email address"，按三次回车，会生成一个 id_rsa.pub文件（生成位置请看 Git Bash 的输出信息），里面记录着 SSH 秘钥。  
3). 用记事本打开 id_rsa.pub 文件，复制里面信息。
4). 进入网址 <https://github.com/settings/ssh/new>（先要登录网站），然后填写信息。其中Title随便输入内容，Key 为我们刚才复制的内容
![git5](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/add_ssh_keys.png)
5). 信息填写完成之后点击 Add SSH key。

(3) 在 VSCode 中使用 Git工具配置
1). 打开 VSCode ，点击 File，再点击 Preferences ，最后点击 Settings
![vscode git setup1](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_vscode_setup.png)
2). 在搜索框输入：terminal.integrated.shell.windows ，输入完成之后，点击 Edit in settings.json ，进入 settings json 页面  
![vscode git setup2](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_vscode_setup2.png)  
3). settings json添加配置
添加内容为：

```python
  "terminal.integrated.shell.windows": "D:\\Git\\bin\\bash.exe",  
  "git.path":"D:\\Git\\bin\\git.exe"
```

注意后面的文件路径，要根据自己电脑上的路径来填写
![vscode git setup3](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_vscode_setup3.png)

4). 添加完成之后，按 Ctrl + S 保存 settings json，再重启 VSCode 就可以在 VSCode 使用 Git 工具。
![vscode git setup4](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_vscode_setup4.png)

- 到此准备工作全部做完，下一步就是对计算器项目进行演示。

### 2. 范例演示

- 此次演示是为了让读者了解如何在项目中使用 Git 工具加入版本控制功能以及如何将本地项目存储到 GitHub 仓库。
- 此次演示分 4 个步骤进行：
  1. 在 GitHub 上建立 calculator 仓库
  2. 将 GitHub 上的 calculator 仓库的内容克隆到本地
  3. 将计算器项目里的内容添加到 Git 仓库
  4. 将 Git 仓库的内容推送到 GitHub 的 calculator 仓库

(1) 第一步，在 GitHub 上建立 calculator 仓库

- 在 GitHub 上登录你的账号，进入 Your repositories 界面，点击 New ，进入创建 GitHub 仓库界面
![GitHub Create Repository1](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/create_github_repository.png)
- 填写相应信息，然后点击 Create repository，就可以创建一个 GitHub 仓库
![GitHub Create Repository2](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/create_github_repository2.png)
- 此时的 GitHub 仓库只有几个初始化的文件，需要我们将计算器项目的文件推送到 GitHub 仓库里

(2) 第二步，将 GitHub 上的 calculator 仓库的内容克隆到本地

- GitHub 上的 calculator 仓库创建完成之后，打开 VSCode，按下 Shift + Ctrl + p , 进入命令搜索框，在里面输入 Git Clone ，然后点击 Git Clone 命令，再输入 calculator 仓库的 url 地址。
![Git clone url](https://github.com/WanglinLi595/Save_Markdown_Picture/blob/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/git_clone_url.png?raw=true)
- 按下换行键，会弹出一个窗口，这是用来选择 GitHub 仓库克隆到本地的路径。选择好之后，点击 Select Repository Location 就可以将 calculator 仓库的内容克隆到本地。

(3) 第三步，将计算器项目里的内容添加到 Git 仓库

- calculator 仓库克隆到本地后，会在你选定的路径生成一个文件夹。文件夹的名字为你 GitHub 仓库的名字。我们 GitHub 上的仓库名为 calculator，那么克隆下来的文件夹名也为 calculator 。
![calculator](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E4%BD%BF%E7%94%A8VSCode%2BGitHub%E8%BF%9B%E8%A1%8C%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/github_name.png)
- 然后将计算器项目里面的内容复制到 calculator 文件夹里面。用 VSCode 打开 calculator 文件夹。
![modify](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/vscode_open_calculator.png)
从图中可以看到，VSCode 已经识别到了我们修改的文件
- 点击 Source Control，再点击 "√" (这个相当于 git commit -am 命令），它会将所有修改的文件添加到 Git 仓库。
![vscode add commit](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/vscode_git_commit.png)
- 点击 "√" 之后会出现一个警告消息框，点击 Yes 即可。之后又会出现一个消息填写框，在里面输入修改信息即可。这样就将计算器项目里的内容添加到 Git 仓库了。
- 此时该项目就能进行版本控制了

(4) 第四步，将 Git 仓库的内容推送到 GitHub 的 calculator 仓库

- 将修改文件添加到 Git 仓库后，只需在 VSCode Git 工具栏点击 push，就可以将 Git 仓库里面的内容推送到 GitHub 的 calculator 仓库了。
![push](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/vscode_git_push.png)
![repository](https://raw.githubusercontent.com/WanglinLi595/Save_Markdown_Picture/master/%E5%9C%A8%20VSCode%20%E4%B8%AD%E4%BD%BF%E7%94%A8%20Git%20%E8%BF%9B%E8%A1%8C%E9%A1%B9%E7%9B%AE%E7%89%88%E6%9C%AC%E6%8E%A7%E5%88%B6/pic/vscode_git_repository.png)  
可以看到，此时本地计算器项目文件夹里的文件已经存储到了 GitHub 上的 calculator 仓库。
- 经过这四个步骤，计算器项目就可以使用 Git 进行版本控制，而且计算器项目也存储在 GitHub 仓库了。
- 这里只演示了在 VSCode 上使用 Git 进行版本控制的基本步骤。如果想了解 Git 进行版本控制的更多功能，如：版本回退，分支管理，团队协作等，请查看下面的推荐教程。

## 四. 更多教程推荐

**(1) [Git 官网](https://git-scm.com/book/zh/v2)**  
**(2) [Git 教程 | 菜鸟教程](https://www.runoob.com/git/git-tutorial.html)**  
**(3) [Git教程 - 廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/896043488029600)**
