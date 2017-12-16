## 准备环节

软件：[Pycharm](http://idea.lanyus.com/)、[Git](https://www.git-scm.com/downloads)

其他：[Github账号](https://github.com/)

## pycharm 配置

进入 pycharm 的 setting 界面，搜索 git ，如图：
![pycharm配置](https://user-gold-cdn.xitu.io/2017/12/16/1605e13a5fd62bf0?w=1281&h=918&f=png&s=39178)

1、GitHub 选项，输入账号密码，点击 test ，会出现成功链接的提示；
>using ssh选项

    a、可不选
    b、推荐选择
    如果选择的话就得在github 上添加 SSH key,具体步骤见参考文章
    
参考文章：[在 github 上添加 SSH key 的步骤](http://hetaoo.iteye.com/blog/2323944)

2、git选项
将git安装路径中的 bin 文件夹下的 git.exe 的路径添加到 Path to Git executable
![git配置](https://user-gold-cdn.xitu.io/2017/12/16/1605e202fdfd7368?w=983&h=125&f=png&s=11716)

## pycharm 中使用 Git

1、将项目路径添加到pycharm中或者新建项目

2、首先 `VSC>import into version control>creat git repository`，生成git仓库
![](https://user-gold-cdn.xitu.io/2017/12/16/1605e2982bc52b80?w=1025&h=360&f=png&s=44146)

3、然后`VSC>import into version control>share project on github`，将项目分享到github中，这里需要密码，密码是创建ssh时设置的

![](https://user-gold-cdn.xitu.io/2017/12/16/1605e2ebe755ab2e?w=447&h=308&f=png&s=12617)
4、现在就可以进行add,commit,push的操作了

    commit快捷键：ctrl+k
    push快捷键：ctrl+shift+k
    
## PS
在pycharm里可以直接通过GUN界面进行操作，但是git常用操作还是要了解一下呀
参考教程：[Git常用操作](https://morvanzhou.github.io/tutorials/others/git/)

`cd`:切换目录，如`cd G://python//demo`

`git config user.name`、`git config user.email`:配置用户信息

`git init`:初始化git环境，即在目录下新建版本管理仓库

`touch 1.py`:命令行模式生成文件

忽略文件方法：

```
touch .gitignore #创建.gitignore
vim .gitignore #通过vim打开

.ignore 配置规则见参考文章

进入vi修改后，要退出的话，先按Esc，然后按shift 和冒号键，然后就可以回到命令行：
：q 在文件未作任何修改的情况下退出。
：q! 强制退出，不保存对文件所作的修改。
：wq 保存对文件所作的修改并退出。
：w 保存文件。
```
参考文章：[.gitignore配置规则](http://blog.csdn.net/yonnangel/article/details/50115059)

`git status -s`: 查看文件状态

`git add 1.py`: 添加文件到modifed/unstage状态

`git commit -m "描述文字"`: 添加文件到stage状态

`git commit -am "描述文字"`: 文件已存在于仓库时可以使用这种方法跳过add

`git log --oneline --graph`: 查看版本记录（oneline 以及 graph方式）

```
#笔者自己总结的，可能有问题

git diff：直接比较的时touch的文件与add后的差别

git diff --cached: 比较的是add后与commit后的差别

git diff HEAD:比较的是touch的文件与commit后的文件
```
`git checkout xxxxxxx`:回到之前的 xxxxx 的版本

`git branch dev`：创建 dev 分支

`git branch`：查看分支

`git checkou dev`：切换到分支

`git checkout -b dev1`：建立并切换到分支 dev1

`git checkout -d dev`:删除 dev 分支