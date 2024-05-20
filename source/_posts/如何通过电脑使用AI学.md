title: 【贴心教程】如何通过电脑使用AI学
author: 闰土
tags:
  - 虚拟机
categories:
  - 贴心教程
date: 2022-11-13 17:41:00
---
看挺多人都打不开，写一个吧    
<!-- more-->
### 需求
比较好的电脑（偷懒

### 开始吧

#### 模拟器
首先，我们需要一个**模拟器**。    
你当然可以随便选择模拟器，但是我这里比较推荐的是蓝叠BlueStacks。    
这里是它的中国官网：[蓝叠中国](https://www.bluestacks.cn/)    
进去之后下载安装即可，这里不过多赘述。

安装完蓝叠，请先确认一下这玩意儿可以用。    

{% note warn %}
如果它无法启动，提示了别的还好，提示到“Hyper-V”的字眼你就要考虑换成WSA(Windows Subsystem for Android，Windows安卓子系统)了。    
当然，还没有那么严重，如若如此我会在下面的[判断电脑状况—Hyper-V](#提示有关—Hyper-V)进行详细解说。    
{% endnote %}

#### AI学安装包
链接放在这里了：[https://tbdriver.lanzouv.com/irPAQ0fui8na
密码:epk1](https://tbdriver.lanzouv.com/irPAQ0fui8na)    
跟着蓝叠里的提示走就好。    

### 判断电脑状况—Hyper-V
除非万不得已，否则你可以先不用来到这一步。     
当你来到这一步时，说明你的电脑已经打开Hyper-V了。关掉就行。    
~~哈哈没想到吧~~    
至于怎么关掉，按住Windows键再按住R键打开“运行”，输入```OptionalFeatures```打开“程序与功能”。    
在程序与功能中取消勾选“Hyper-V”即可。    
