# 1. git
## 1.1 git、gitlab、GitHub的简单区别
git 是一种基于命令的版本控制系统，全命令操作，没有可视化界面
gitlab 是一个基于git实现的在线代码仓库软件，提供web可视化管理界面，通常用于企业团队内部协作开发
github 是一个基于git实现的在线代码托管仓库，亦提供可视化管理界面，同时免费账户和提供付费账户，提供开放和私有的仓库，大部分的开源项目都选择github作为代码托管仓库
其中：
* Gitlab和GitHub的区别
**相同点**：二者都是基于web的Git仓库，在很大程度上Gitlab是仿照GitHub来做的；
它们都提供了分享开源项目的平台，为开发团队提供了存储、分享、发布
和合作开发项目的中心化云存储的场所。
**不同点**：GitHub如果要使用私有仓库，是需要付费的。Gitlab可以在上面创建私人的免费仓库。
Gitlab让开发团队对他们的代码仓库拥有更多的控制，相比于GitHub，它有不少的特色：允许免费设置仓库权限;允许用户选择分享一个project的部分代码;允许用户设置project的获取权限，进一步的提升安全性;可以设置获取到团队整体的改进进度;通过innersourceing让不在权限范围内的人访问不到该资源。从代码私有性方面来看有时公司并不希望员工获取到全部的代码，这个时候Gitlab无疑是更好的选择。但是对于开源项目而言，GitHub依然是代码托管的首选。

## 1.2 vscode中使用Github
### 1.2.1 clone时显示无法连接
这时可以通过设置系统代理来解决。具体步骤如下：

打开系统设置，搜索代理设置，并点击编辑按钮。
![[Pasted image 20250320001041.png]]

在代理服务器中，将端口设置为7890（这个端口不会影响正常上网，可以放心设置），然后点击保存。
![[Pasted image 20250320001105.png]]

在终端输入以下命令，设置 Git 使用本地代理：(10809是我自己的v2ray端口)
`git config --global http.proxy http://127.0.0.1:10809`

设置完成后，可以通过以下命令检验是否设置成功：
`git config --global -l`

### 1.2.2 提交时要设置好名称和其他(随便填的)
git config user.name 你的github用户名
git config user.email 邮箱地址

### 1.2.3 提交流程
* 主分支master是稳定版，其分支develop为测试环境，所以自己开发时应该在develop再创建一个分支demo，然后切换到demo分支进行编写
* git add（暂存文件）
* git commit（提交文件）
在vscode中还要在消息模块上写入 feat:update 文件名才能提交成功
* 切换回develop，使用git pull拉取主分支的代码（因为在你开发时可能已经有人提交了代码到主分支上，所以这里要再次同步一下主分支）
*  然后在develop下选择git merge合并代码，其中选择合并的分支为你的demo分支
* 最后如果还有需要的就是git push到github网站上了

我的git仓库地址
https://github.com/chenaaa1/note.git