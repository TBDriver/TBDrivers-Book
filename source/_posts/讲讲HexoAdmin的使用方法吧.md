title: 讲讲Hexo Admin的使用方法吧~
author: 闰土
tags:
  - Hexo Admin
categories:
  - 教程
banner_img: 'https://s1.ax1x.com/2022/11/06/xXzxP0.png'
date: 2022-08-22 13:16:00
---
今天来写个Hexo Admin的食用方法！    
这个Post就是用Hexo Admin写的~    
<!-- more -->   
## 为什么选择Hexo Admin？
懒。（    
看了下，目前的Hexo编辑器并不是很多，貌似只有Hexo Admin还算凑合，讲究的可以试试自己开发。但是回头看：只要咱好好配置，Hexo Admin的功能还是很齐全的嘛~    
但是在线写文章的编辑器已经有人在开发啦，点击[传送门](https://www.bilibili.com/video/BV1f3411C7dy/)带你看看新的大佬开发的编辑器 **Hexon** ！
先来看看效果：     
![写稿子的主页~](https://s1.ax1x.com/2022/11/06/xXzj5q.png)   
分析下特点：
* 优点
  1. 文章书写
      - 支持实时渲染MarkDown文档。
      - 支持增加标签和分类。
      - 自动增加时间，无需撰写复杂且sb的 `Front-Matter`。
      - 支持书写一些其他的东西，比如 ` About.md`。
  2. 网站
     - 支持在线部署
     - 支持设置密码
     - 支持一些其他设置
* 缺点
  - 无法在线书写，需要 `hexo server` 后在 `localhost:4000/admin` 中使用

那么，咱来看看怎么使用吧！
## **如何使用Hexo Admin？**
必应一搜全都有，但是我还是做了个总结。   

### **安装**
---
如果你已经安装好了Hexo Admin，    
可以点击右上方的目录跳转到“使用”，    
或者直接[戳我](#使用)跳转到“使用”   

#### **安装配置**
---
需求如下：    
npm    
Hexo   ---> 3.7及以上    
↓需要：    
所需要的版本的 Node.js & Ruby  

#### **安装和打开方式**
---
打开命令行，定位至hexo根目录下，输入如下指令：    
`npm install --save hexo-admin`    
通过执行 `hexo server` 启动Hexo后，    
进入 `localhost:4000/admin`     
便可进入Hexo Admin的主界面。    
{% note info %}
_**没用的小知识增加啦！**_    
在通过命令行使用Hexo失败，比如提示“这啥玩意儿啊没见过啊”的时候，    
可以在hexo前面加上 `npx` 来间接使用。    
For 1 zample:    
运行 `npx hexo server` 来启动Hexo。    
{% endnote%}

### **使用**
---
如果你按照上述的操作运行完成并且没什么错误的话，你可以通过进入`localhost:4000/admin/`来进入主界面。    

Hexo Admin的主界面很简单。分为五栏：    
- [Posts(发帖)](#Posts-发帖)
- [Pages(页面)](#Pages-页面)
- [About(关于)](#About-关于)
- [Deploy(部署)](#Deploy-部署)
- [Settings(设置)](#Settiings-设置)
点击便可进入对应的栏目。  

#### Posts|发帖
---
写一个博客的步骤如下：    
1. [新建页面](#新建页面)
2. [编辑内容、标签与分类](#编辑内容、标签与分类)
3. [发布](#发布)

##### 新建页面
---
在 Posts 界面点击“+ New Post”就可以新建一个页面。    
把鼠标悬停在新建的页面栏目上，就会在栏目的右上角显示一个链接图标和一支笔。点击链接便可以进入这篇文章的网页版，点击那支笔便可以进入这篇文章的编辑界面。

##### 编辑内容、标签与分类
---
~~不会有人不会写MarkDown吧~~不会写Markdown？没关系！我这里准备了一系列[教程](https://tbdriver.github.io/2022/MarkDown撰写指东南西北/)给你~    
点击右上角的设置图标就可以对文章进行设置。
Hexo Admin提供了以下设置项：
- 发布时间
- 作者
- 标签
- 分类

##### 发布
---
按下右上角的“Publish”就可以发布啦~

#### Pages|页面
---
其实功能和Posts差不多，只是可以对博客内部的md文件进行编辑。但是也还是很方便的啦~    

#### About|关于
---
就是Hexo Admin的简介。  

#### Deploy|部署
---

{% note warning %}
你需要安装Git来实现这里的全部功能。
{% endnote %}

是不是很棒？Hexo Admin内嵌了部署的功能！但是它本身是不能部署的。为了让Deploy能用且更加方便，我们来对它进行一下改造。    
首先，在Hexo根目录下的`_config.yml`的任意处增加如下代码：    
```yaml
# Config Hexo Admin
admin: 
   deployCommand: HexoDeploy.bat
# Config deployer
deploy:
  type: 'git'
  repo: 你的仓库地址
  branch: 要上传的分支
  message: 信息，随便填啦~
```
然后再在Hexo根目录下新建一个名为`HexoDeploy.bat`，在里面写下如下代码：    
```
clean && hexo deploy
```
最后，在Hexo根目录下执行：    
```
npm install hexo-deployer-git
```
一切就都准备好啦！以后你就只需要在Deploy栏目中按下“Deploy”按钮就行了。   
部署完成后，部署界面大概会变成这样：    
![部署后](https://s1.ax1x.com/2022/11/06/xjSgzT.png)    
只要看见“Std Error”一栏没有东西就成功啦~    
当然，有东西的话就说明博客或者文章的某个位置出了点问题，这个就费心大家去修下BUG辣~    

#### Settings|设置
---
其实设置里也没什么东西，好奇的可以开下翻译看看功能。    
但是还是有一个功能吸引了我的注意，那就是后台登陆功能。
![它大概长这样](https://s1.ax1x.com/2022/11/06/xjSwLQ.png)
如果你和我是一样的版本，那它大概长这样。    
如果你需要后台功能的话~~都只能在本地运行了也太没安全感了吧~~，就可以点击“Setup authentification here”，对账号和密码进行配置。    
配置好了呢，就回到`_config.yml`中的admin加上如下代码：    
```yaml
  username: 你的用户名
  secret: 你的密码
  password_hash: 配置好会给你一串Hash，复制过来就可以了
```
一切配置好之后，你的admin大概长这样：    
```yaml
admin:
  username: 你的用户名
  secret: 你的密码
  password_hash: 配置好会给你一串Hash，复制过来就可以了
  deployCommand: hexo_pubish.bat
```
试试看吧~