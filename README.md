# Java Lesson

## 2019-12-05

### 公告

1. 想让大家平时练习时就把 git 和 maven 用上，今晚讲一下它们的简单用法
   - 在 github 上创建项目
   - 创建 maven 项目，常见的配置，如何在 pom.xml 加入依赖项目
   - maven 编译
   - git 提交代码到 github 你创建的项目上
2. ：条件、循环、循环嵌套等
3. 使用 LeetCode 上的一些和当前所学内容相关的算法题来作为课堂练习

### git + maven 的安装和使用

- maven 安装
    - 下载 maven 最新版本，https://maven.apache.org/download.cgi
    - 解压下载的安装包（例如：apache-maven-3.6.3-bin.zip）到某个目录
    - windows 环境下将目录 `maven解压目录\bin` 添加到环境变量 Path 上
    - mac 环境，在 `~/.bash_profile` 文件中加入一行，然后执行一下 `source ~/.bash_profile` 使之生效
        ```
        export PATH=/maven解压目录/bin:$PATH
        ```
    - 命令行下执行 `mvn --version`，如果能正确显示版本号，说明安装正确，比如显示内容如下：
        ```
        ➜  java-les mvn --version
        Apache Maven 3.6.1 (d66c9c0b3152b2e69ee9bac180bb8fcc8e6af555; 2019-04-05T03:00:29+08:00)
        Maven home: /Users/sh/bin/mvn
        Java version: 1.8.0_212, vendor: Oracle Corporation, runtime: /Library/Java/JavaVirtualMachines/jdk1.8.0_212.jdk/Contents/Home/jre
        Default locale: zh_CN, platform encoding: UTF-8
        OS name: "mac os x", version: "10.15", arch: "x86_64", family: "mac"
        ```
- 注册 github 账号
- 新建一个项目
    - 登录成功后，点击右上角【+】，在下拉菜单中选择【New repository】
    - 填写项目名（Repository name）和描述（Description）
    - 选择公共库（Public）、不使用 README.md 初始化
    - 点击【Create repository】进行创建
- 将自己项目上传 github
    - 下载 git，https://www.git-scm.com/download/
    - 安装后，进入命令行执行 `git --version`，如果能正常显示版本号说明安装正确，比如显示内容如下：
        ```
        ➜  java-les git --version
        git version 2.21.0
        ```
    - 设置 git 用户名、邮箱
        ```
        git config user.name
        git config user.email
        git config --global user.name "你的名字，显示在git提交历史记录里的名字"
        git config --global user.email "你的邮箱，显示在git提交历史记录里的邮箱"
        ```
    - 将示例空项目，按 maven 项目导入
    - 使用 git 命令初始化仓库，并将第一个版本上传
        ```
        git init
        git add .
        git commit -m "first commit"
        git remote add origin 你创建的github项目地址
        git push -u origin master
        ```
    - 提交成功后，到 github 上刷新，看一下效果
    - 如果使用 http 的 git 地址，如果嫌每次输入用户名密码麻烦的化，使用如果命令可以记住密码
        ```
        git config --global credential.helper store
        ```
    - 修改一下 README.md，然后提交一下
        ```
        git status
        git add .
        git commit -m "本修改说明"
        git push
        ```
        `git add .` 是添加所以的变更，如果单独添加某个文件可以使用 `git add 单个文件路径名称`
    - 到 github 项目页面上刷新一下，看一下效果

### 程序控制执行流程
