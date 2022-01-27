# **SpringBootStarting**
*take notes while learning*

***

[toc]





## 一、 MarkDown用法

1. “\#”表示标题，可以通过数量表示1-6级标题

2. “\*”表示斜体粗体，分割线

3. “\~~”表示删除，例如：~~删除这里~~

4. < u >标签表示下划线，例如<u>selected text</u>

5. 创建一个脚注[^left foot]

6. 更多功能自行百度

7. "```"表示代码块，例如

   ```java
   //这是一段java代码
   ```

   

[^left foot]: 



## 二、 git用法

### 1.  拉取远程仓库

- 打开目标文件夹，从远程仓库拉取： git clone [ url ]

- 将改动增加到暂存区： git add . ,或者git add [file_name]

- 提交文件： git commit -m "你的评论"

- 改动推送到远程： git push

- 拉取合并最新代码： git pull origin master

### 2. 推送新项目

You can also upload existing files from your computer using the instructions below.

**Git global setup**

```
git config --global user.name "YOURNAME"
git config --global user.email "SAMPLE@SAMPLE.COM"
```

**Create a new repository**

```
git clone git@localhost:liran/test.git
cd test
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```

**Push an existing folder**

```
cd existing_folder
git init
git remote add origin git@localhost:liran/test.git
git add .
git commit -m "Initial commit"
git push -u origin master
```

**Push an existing Git repository**

```
cd existing_repo
git remote rename origin old-origin
git remote add origin git@localhost:liran/test.git
git push -u origin --all
git push -u origin --tags
```

### 3. ssh与多仓库配置

​		通过ssh的方式，可以省去登录环节，提高推送和拉取的效率。如果配置两个仓库，需能够生成两对 私钥/公钥，push 时，可以区分两个账户，推送到相应的仓库。
​	解决方案:
​		生成 私钥/公钥 时，密钥文件命名避免重复；
​		设置不同 Host 对应同一 HostName 但密钥不同；
​		取消 git 全局用户名/邮箱设置，为每个仓库独立设置 用户名/邮箱。

```
ssh-keygen -t rsa -f ~/.ssh/id_rsa_1 -C "yourmail@xxx.com"

ssh-keygen -t rsa -f ~/.ssh/id_rsa_2 -C "yourmail@xxx.com"
```

​		1. 在.ssh文件夹下新建config文件并编辑，令不同的host对应不同的密钥。

```
# github
Host github.com
HostName github.com
user Sample_1
IdentityFile ~/.ssh/id_rsa

# gitlab
Host host@test.com
HostName host@test.com
user Smaple_2
IdentityFile ~/.ssh/id_rsa2
```

  2. 在远程仓库配置SSH

  3. 测试SSH连接

     ```
     ssh -T git@exampleHost.com
     ```

     

  4. 取消全局用户

     ```
     git config --global --unset user.name
     git config --global --unset user.email
     
     #项目目录下重新设置origin（如果需要）
     git remote rm origin
     git remote add origin git@exampleHost.com
     
     git push origin master
     ```

## 三、 GitHub入门

### 1. 查找项目

​	awesome XXX； XXX sample


## 四、 开始面向spring编程

### 1. Hello， Java

```java
public static void main(String[] args) {}
```

### 2. mac配置环境

​	finish.
