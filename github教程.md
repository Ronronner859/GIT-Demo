## git教程

### 打开本地的文件夹  这里通过vscode打开

### 打开之后里面放入你想放入的文件或者自己手动创建文件

### 新建终端：通过命令端来操作git

- vscode命令端跟Linux基本类型
- 支持linux的基本命令操作

### 步骤1-基本提交

#### 查看git版本信息

```c
git version
```

#### 配置个人账户和个人邮箱 （提交时可以显示是那个用户提交的）

```
git config --global user.name "cy"
git config --global user.email "2863519726@qq.com"
```

####  初始化

```
git init
```

初始化的作用是记录你文件的版本信息和日志

#### 添加

```
pass1:针对单个文件
git add 某个文件名
pass2:针对多个文件
git add .
```

添加后只是暂存文件，但是不会保存提交记录

#### 查看状态

（也就是你文件添加后状态–此时它会显示绿色）

```
git status
```

#### 提交

```
简化版版操作用-m会跳过vim编辑器
//git commit -m “提交说明”
git commit -m "first commit"
```

commit后会保存提交记录

#### 查看提交记录

```
git log
```

可以显示你的提交文件的日志信息

### 步骤2-修改回退

**步骤1操作完成后，就会记录你的第一次提交记录了**

#### 修改

将文件进行修改后，文件的颜色由绿色变成橙色

绿色：表示新增的文件

橙色：表示修改过的文件

然后再执行：

```
git add .
git commit -m "second"
```

然后进行第二次提交

#### 回退版本

>// 以下是日志信息 
>
>PS D:\Otherfile\test> git log
>commit 49076d4e8516d07b83aed080bf869d13d739ac3c (HEAD -> master)
>Author: cy <2863519726@qq.com>
>Date:   Fri Nov 11 17:40:51 2022 +0800
>
>    second
>
>commit 6dedd4c4e43741173f1ed35eec99f516b44f2377
>Author: cy <2863519726@qq.com>
>Date:   Fri Nov 11 17:31:51 2022 +0800
>
>    first

复制commit后面的命令然后执行

```
git reset --hard 6dedd4c4e43741173f1ed35eec99f516b44f2377
```

然后就可以回退到之前的版本

### 步骤3-版本切换

**通过创建分支-切换不同的版本**

#### 创建分支

2.0

```
git branch 2.0 //git branch 分支名
```

3.0

```
git branch 3.0 //git branch 分支名
```

#### 切换分支

```
git checkout 2.0
```

```
git checkout 3.0
```

```
git checkout master
```

#### 合并分支

可以在不同的分支上或者主流上继续写code

然后通过merge合并分支

```
git merge 2.0
```

```
git merge 3.0
```

**分支主要用于团队协作**

开发互不影响又能同时操作
