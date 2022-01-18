# GitHub

### **版本**

1.本地版本控制

2.集中版本控制SVN

3.分布式控制GIT【每个人都拥有全部的代码！！安全隐患，但可以离线在本地提交，不会因为服务器损坏或者网络问题，造成不能工作】GIT可以直接看到更新了的代码文件

***



### **Git的配置**

`86134@LAPTOP-T0M66FUN MINGW64 ~/Desktop/gitcode
$ git config --global --list
fatal: unable to read config file 'C:/Users/86134/.gitconfig': No such file or directory`

所有的配置文件，其实都保存在本地！！

查看配置git config -1

查看不同级别的配置文件：git config --system --list

查看当前用户的global配置：git config --global --list

##### Git相关的配置文件：

1） Git\etc\config  :Git安装目录下的gitconfig --system系统级

2） C:\User\Administrator\.gitconfig  只适用于当前登录用户的配置 --global全局,这里可以直接百编辑配置文件，通过命令设置会响应到这里

```
# This is Git's per-user configuration file.
[user]
	name = chenshuting
# Please adapt and uncomment the following lines:
#	name = unknown
#	email = 86134@LAPTOP-T0M66FUN.(none)

```

3）设置用户名和邮箱

当安装Git后首先要做的事是设置你的用户名称和e-mail地址，这是非常重要的，因为每次提交都会使用该信息，他被永远的嵌入到了你的提交中

git config --global user.name "chenshuting" #名称

git config --global user.email 3046488765@qq.com  #邮箱





软件的下载：下载慢的话，可以找淘宝镜像:[git-for-windows Mirror (taobao.org)](http://npm.taobao.org/mirrors/git-for-windows/)

启动git

安装成功后在开始菜单中会有git选项，菜单下有3个程序：任意文件夹下右键也可以看到对应的程序

gitbash:unix跟Linux的风格的命令行，使用最多，推荐最多

gitcmd:windows风格的命令行

git gui：图形界面的git，不建议初学者使用，尽量先熟悉常用的命令行

***



### **#基本的Linux命令**

平时一定要多使用这些基础的命令

```
cd 改变目录

cd.. 回退到上一个目录，直接cd进入默认目录

pwd 显示当前所在的目录路径

ls(ll) 都是列出当前目录下的文件，只不过(ll)列出的内容更为详细

touch 新建一个文件 ，如touch.index.js就会在当前目录下新建一个index.js文件

rm 删除一个文件，rm index.js就会在当前目录下新建一个index.js文件

mkdir 新建一个目录，就是新建一个文件夹  例如：mkdir test,新建一个test文件夹

rm -r 删除一个文件夹，rm -r src删除目录

mv 移动文件，mv index.html 是我们要移动的文件，src是目标文件夹，例如：mv index.html test     【将index.html移到test文件夹】 

reset重新初始化终端\清屏

clear清屏

history查看命令历史

help帮助

exit退出

#表示注释
git pull  拉取代码
git checkout branch_name  切换分支
git status    查看工作区状态
git log   查看过往的提交记录
git add  提交到暂存区
git commit -m "这里是提交注释"
git push    提交到远程仓库
```

rm -rf /     危险危险危险！！！！删除电脑中的全部文件！！！

****

#### Git的基本理论（核心）

工作区域：工作目录（working directory）,暂存区（stage/index），资源库（repository/Git Directory）。还有一个远程的仓库（working directory）

<img src="C:\Users\86134\Desktop\heima\git.png" alt="git"  />

```
working directory：平时存放代码的地方

stage/index：暂存区，用于临时存放你的改动，事实上他只是一个 文件，保存即将提交到文件列表信息

repository/Git Directory:本地仓库，安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本

Remote：托管代码的服务器，项目组中的一台电脑用于远程数据交换本地的三个区域，确切的说应该是git仓库中的HEAD指向的版本

HEAD：ref: refs/head/master  #主分支


```

***



### 工作流程：

1.在工作目录中添加、修改文件；       

```
UserMapper.xml
```

2.将需要进行版本管理的文件放入暂存区

```
git add.
```

3.将暂存区的文件提交到git仓库

```
git commit
```

git管理的文件有三种状态：已修改（modified），已暂存（staged），已提交（committed）

***



### Git项目搭建

1.创建工作目录与常用指令

2.本地仓库的方法有两种：一是创建全新的仓库，二是克隆远程仓库

1）创建全新的仓库，需要用Git管理的先您过目的根目录执行，执行后可以看到多出了一个.git目录，关于版本的所有信息都在这个目录里面

```
#在当前目录新建一个Git代码库
$ git init
```

2）克隆远程目录，由于是远程服务器上的仓库完全镜像一份至本地

可以取gitee或者GitHub上克隆一个测试！

```
#克隆一个项目和他的整个代码历史（版本信息）
$ git clone https://gitee.com/kuangstudy/openclass.git  #后面为克隆项目/代码的网址
```

***



### Git文件操作

```
文件的四种状态
```

```
untracked
unmodify
modified
staged

```

```
查看文件状态
```

```
#查看指定文件状态
git status [filename]

#查看所有文件状态
git add .       #添加所有的文件到暂存区
git commit -m "消息内容"   #提交暂存区中的内容到本地仓库， -m提交信息
```





```
忽略文件
```

在主目录下建立”.gitignore"文件，此文件有如下规则：

1）忽略文件的空行/井号（#）开始的行将会被忽略

2）可以使用Linxu通配符，如：星号（*）代表任意多个字符

？代表一个字符

[]代表可选字符范围              {string1，string2，...}代表可选的字符串

3）若名称最前面有一个感叹号（！），表示例外规则，将不被忽略

4）若名称最前面有一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录的文件不忽略

5）若名称最后面有一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件/目录都被忽略）

```
#  注释
*.txt  #忽略所有.txt结尾的文件，这样的话上传就不会被选中
！lib.txt     #但lib.txt文件除外
/temp         #仅忽略项目根目录下的TODO文件不包括其他目录temp
build/        #忽略build/目录的所有文件
doc/*.txt     #会忽略doc/notes.txt，但不包括doc/server/arch.txt
```

***



### 使用码云

这个其实可以作为未来找工作的一个重要信息！

```
GitHub是有墙的，比较慢，在国内的话，我们一般使用gitee，公司有时候会搭建自己的gitlab服务器
```

1）注册登录码云，完善个人信息

2）设置本机绑定SSH公钥，实现免密码登录！（这一步很重要，免密码登录）

```
#进入 C:\Users\Adminstrator\ssh
#生成公钥
ssh-keygen
```

> 86134@LAPTOP-T0M66FUN MINGW64 ~/.ssh
> $ ssh-keygen -t rsa
> Generating public/private rsa key pair.
> Enter file in which to save the key (/c/Users/86134/.ssh/id_rsa):
> Enter passphrase (empty for no passphrase):
> Enter same passphrase again:
> Your identification has been saved in /c/Users/86134/.ssh/id_rsa
> Your public key has been saved in /c/Users/86134/.ssh/id_rsa.pub
> The key fingerprint is:
> SHA256:NMI0emjh4yU76FbviSH7kAbdB5DyFX9v9zkzqalnap0 86134@LAPTOP-T0M66FUN
> The key's randomart image is:
> +---[RSA 3072]----+
> |  ..o.o          |
> |. .o.B .         |
> | o .O * +        |
> | ..= B + o       |
> |. o * . S o .    |
> | o o +   . . . o |
> |  B . .    . .B  |
> | o + + .  . Eo + |
> |  ..o o  .o=o    |
> +----[SHA256]-----+

3)将公钥信息public key添加到码云账户中即可

4）使用码云创建一个自己的仓库

许可证：开源是否可以随意转载，开源但是不能商业使用，不能转载，..限制

克隆到本地！

***



### IDEA中集成Git**<u>【未，先跳过】</u>**

(idea中缺一些东西)

1）新建项目，绑定git

将我们远程的git文件目录拷贝到项目中即可！

注意观察idea中的变化

2）修改文件，使用IDEA操作git

3）提交测试

***



### Git的分支

master 主分支

dev    开发用

v4.0

v3.0    不同版本的分支

```
#查看文件中有的主分支跟分支
$ git branch

#新建一个分支,但还停留在当前的分支
$ git branch [branch-name]

#
$ git branch -r

#
$ git branch dev

#合并指定分支到当前的分支
$ git merge [branch-name]

#删除分支
$ git branch -d [branch-name]

#删除远程分支
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]
```

多个分支如果并行执行，就会导致我们代码不冲突，也就是同时存在多个版本！

web-api    -A

web-admin    -B会调用A（修改了A的代码）

web-app     -C会调用B和A 的代码

如果冲突了就需要协商即可！

如果同一个文件在合并分支时都被修改了会引起冲突，解决的办法是我们可以修改冲突文件后重新提交！选择要保留它的代码还我自己的代码！

master主分支应该非常稳定，用来发布新版本，一般不允许在上面工作，工作一般情况下在新建的dev分支上工作，工作完后，比如要发布，或者说dev分支代码稳定后可以合并到主分支master上来

***



***



## 创建流程

设置用户名和邮箱

```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

初始化仓库

```
git init
```

将文件添加到暂存区

```
git add hello.txt
#如果是多个文件存放到暂存区的话，执行
git add .
```

提交

```
git commit -m 'First commit'   #First commit为当前commit的信息，用于简单描述提交的内容
```

查看提交记录

```
git log                        #查看提交记录
git log --graph                #以 ASCII 图形显示提交记录
git log --graph --oneline    #以 ASCII 图形显示提交记录，并且每条记录一行显示
```

回滚

```
git reset --hard a7e0219    #a7e0219为commit的ID，--hard表示回滚的模式
```



### 分支管理【创建分支、合并分支、变基分支、优选】

查看当前的分支

```
git branch
```

#### 创建分支

```
git branch test        #创建名为test的分支
git branch -d test    #删除名为test的分支
```

切换分支【checkout】

```
git checkout test   #test为分支名称
```

添加文件并提交

```
git add BranchTest.txt
git commit -m 'commited by test'
```

查看当前的记录

```
git log --all --graph --oneline

```

#### 合并分支

回到master分支

```
git checkout master
```

合并分支

```
git merge test
```



#### 变基分支



```
 #test分支的开始位置在99e8b90，此时需要master分支中的bbb.txt，但不想合并，就可以用变基分支进行操作：
 git rebase master 
```



#### 优选

即cherrypick，可以单独合并某一次提交。master文件中有了两个文件，我只需要其中的一个，且不想进行分支合并，也不想分支变基，所以就可以选择优选。

```
git cherry-pick 6fb1632   #6fb1632是优选的commitID，
```

### 远程仓库

#### 创建远程仓库

在github中的new repository选项，填写仓库地址和名称，设置共有/私有，点击创建即可

#### 添加远程仓库并推送

复制仓库地址

回到我的仓库，添加仓库地址

```
git remote add origin git@github.com:kakkk/test.git
#其中，origin为远程仓库名称， git@github.com:kakkk/test.git为远程仓库的地址
```

添加身份验证【使用ssh，也可以使用token，这里使用ssh】

先在本地生成一个rsa公钥

```
ssh-keygen -t rsa
```

用记事本/编辑器打开i公钥，即id-rsa.pub

打开GitHub，点击头像，setting

选择ssh和gpg keys,点击new ssh key

将刚刚得到的公钥复制到里面，添加即可

完成后，使用一下命令测试：

```
ssh -T git@github.com
```

#### 推送

推送远程仓库

```
git push origin master 
```

### 克隆项目

```
git clone 远程仓库地址
```

### 抓取/拉取项目

- 抓取（fetch）：只获取远程仓库分支，不进行自动合并，需要手动合并才能提交

- 拉去（pull）：获取并自动合并远程分支

  ```
  git fetch origin
  git pull origin
  ```

  

### 文件的修改上传

```
1）先抓取文件
git fetch origin（地址）
2）修改
3）上传
git checkout master/其他分支
git add 文件
git commit -m 'updating(说明内容)'
git push -u origin（仓库地址，要改成例如：git@github.com:CST-Fighting/deepcode-assignments.git） master/其他分支
```

