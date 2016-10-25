# Github的简单常用命令

***

###目录
> [**第一章：Git环境设置**](#setting)
>
> [**第二章：Git创建SSH**](#create_SSH)
> 
> [**第三章：Git拉取文件**](#create)
> 
> [**第四章：Git尝试修改**](#change)
> 
> [**第五章：Git分支操作**](#branch)
> 
> [**第六章：Git远程提交**](#push)
> 
> [**第七章：Pro Git**](#pro)
> 
> [Thanks](#thanks)


***

## <a name="setting"></a>第一章：Git环境设置

####Linux

```
$sudo apt-get install git-core
```

####Mac


* 使用Terminal，需要下载[Git](http://jaist.dl.sourceforge.net/project/git-osx-installer/git-2.10.1-intel-universal-mavericks.dmg)包.

* 使用[Github Desktop](https://mac-installer.github.com/mac/GitHub%20Desktop%20222.zip).


####Window

* 使用[git bush](https://github.com/git-for-windows/git/releases/download/v2.10.1.windows.1/Git-2.10.1-32-bit.exe)

***

## <a name="create_SSH"></a>第二章：Git创建操作

###Step 1:初始化信息

```
$git config --global user.name "your_name"
$git config --global user.email "your_address@mail.com"

```

###Step 2:生成密钥

```
$ssh-keygen -t rsa -C "your_address@mail.com"
```

###Step 3:复制密钥

####Linux

```
$sudo apt-get install xclip
$xclip -sel clip < ~/.ssh/id_rsa.pub
```

####Mac

```
$pbcopy < ~/.ssh/id_rsa.pub
```

####Windows

```
$clip < ~/.ssh/id_rsa.pub
```

* 如果以上方法不好用的话，情尝试以下方法,直接复制密钥

```
$vi < ~/.ssh/id_rsa.pub
```

###Step 4:关联Terminal与GitHub
***

1. 登录自己的GitHub账号进入Settings

![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/97F7FC2A-AABC-4C1B-8C09-7809A1A4C89C.png?raw=true)

2. 找到“SSH和GPG keys”并且点击“New SSH key”
![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/00366E52-8319-4A6D-A80A-21A1182636E7.png?raw=true)


3. 成功创建SSH
![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/D91F5876-6D8B-400A-A736-FCF5E02CB7E7.png?raw=true)

###Step 5:在Terminal登录SSH

```
$ssh -T git@github.com
```

> 出现以下情景就成功登录SSH
> 
> ![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/8ED2DE1E-8E25-45E6-BFF5-BD1B0324F405.png?raw=true)
> 
>
***

## <a name="push"></a>第三章：Git拉取文件

###从远程拉取 UIT-Training/211-213-215

![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/FFD005F6-41A1-4ACA-8E41-196F9E029876.png?raw=true)

> 以HTTPS拉取UIT-Training/211-213-215文件
```
$git clone https://github.com/UIT-Training/211-213-215.git
```

***

## <a name="change"></a>第四章：Git尝试修改

###打开拉取的文件(以211-213-215为例)

```
$cd 211-213-215/
```

###修改文件内容（为自己建立一个.md文件）

vim下载地址：
> [Linux](http://www.vim.org/git.php)
> [Mac](https://github.com/macvim-dev/macvim/releases/download/snapshot-113/MacVim.dmg)
> [Windows](ftp://ftp.vim.org/pub/vim/pc/gvim80.exe)
> 
```
$vim shenxiaojian.md 
```

1. 点击 --> i

2. 当输入结束之后 --> Esc

3. 输入 --> :wq

###查看文件状态

```
$git status
```
![Show](https://github.com/Mr-Jason-Sam/UIT_Resource/blob/master/C0C742FE-2A1A-4279-BC77-6B5131F8B541.png?raw=true)
结果，文件未标记，需要进行git add 操作

***

## <a name="branch"></a>第五章：Git分支操作

###新建分支

```
$git branch shenxiaojian
```

###查看分支

> 查看本地分支
> 
>```
>$git branch
>```

> 查看所有分支
> 
>```
>$git branch -a
>```

###切换分支

```
$git checkout shenxiaojian
```
 成功切换到自己的分支

***

## <a name="push"></a>第六章：Git远程提交

###Step 1:文件标记

```
$git add shenxiaojian.md
```

###Step 2:提交文件

```
$git commit -m 'shenxiaojian'
```

###Step 3:远程连接

```
$git remote add shenxiaojian https://github.com/UIT-Training/211-213-215.git
```

###Step 4:远程推进

```
$git push -u origin shenxiaojian
```

***

## <a name="pro"></a>第七章：Pro Git

###本周末可以学习[Pro Git](http://git.oschina.net/progit/)的基本用法～

> 重要的知识点都在**前5章**,其他知识点可以选看，最好动手实践，而不是复制粘贴


## <a name="thanks"></a>Thanks

 **有需要改正的可以指出**