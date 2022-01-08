---
title: Sanguosha CLI
summary: Written in Java, 10000+ lines
tags:
- Personal
date: "2020-07-02T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: preview
  focal_point: Smart

url_code: "https://github.com/wzk1015/sanguosha"
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

# 文字版三国杀

## 功能介绍

本软件基于Java实现了文字版三国杀，其中包括了66个武将，41种手牌及若干其他功能类，共计147个类和接口，采用高度面向对象的设计方法实现，总行数达到**10000行**以上。同时，使用了swing开发了GUI作为游戏界面。代码经过仔细整理和重构，使用checkstyle检查，符合google的代码设计规范。

<img src="https://raw.githubusercontent.com/wzk1015/sanguosha/master/README.assets/image-20211117215440021.png" alt="image-20211117215440021" style="zoom: 67%;" />

主要实现了三国杀对战的功能，涵盖了上百种不同技能，可以进行单机多人对战、玩家挑战AI等，支持自定义游戏人数、身份配置、武将扩展包等功能。玩家通过键盘输入命令与程序交互，在屏幕上以文字形式展示游戏进行流程、全局每名玩家的状态、当前回合玩家的状态等信息。游戏中每名玩家依次执行自己的回合，打出卡牌或使用技能触发一系列复杂的判定过程，并实时判定游戏结束条件，在触发游戏结束条件时结束程序，输出获胜者。





## 使用说明

### 前提条件

系统内安装jdk（版本1.8以上）

### GUI运行

使用命令行（windows下可按下win+R输入cmd，mac下打开终端）进入目录，运行`java -jar sgsgui.jar`即可

<img src="https://raw.githubusercontent.com/wzk1015/sanguosha/master/README.assets/image-20200702143730552.png" alt="image-20200702143730552" style="zoom: 25%;" />

<img src="https://raw.githubusercontent.com/wzk1015/sanguosha/master/README.assets/image-20200702143815869.png" alt="image-20200702143815869" style="zoom: 25%;" />

### 命令行运行

运行`java -jar sanguosha.jar`，即可命令行运行

<img src="https://raw.githubusercontent.com/wzk1015/sanguosha/master/README.assets/image-20200702143543760.png" alt="image-20200702143543760" style="zoom: 25%;" />

### 自定义

默认配置下使用全套卡牌+武将标准包，身份根据人数预先设定。在初始化时选择`customize`，即可自定义扩展包、身份分配、每个玩家可选的武将数量。



## 整体架构

整体架构上，由GraphicLauncher调用GraphicRunner类的run方法启动游戏。该方法初始化游戏界面和ActionListener，随后初始化游戏内核GameLauncher，并通过JTextField组件的输入内容与游戏核心进行交互。

游戏内核GameLauncher调用游戏管理核心GameManager，完成初始化牌堆、分配身份、选择武将等步骤，并循环执行每个玩家的回合，直到触发游戏终止条件时，输出获胜者。

每名玩家的回合在其武将类Person的run方法中执行，依次进行回合开始阶段、判定阶段、摸牌阶段、出牌阶段、弃牌阶段、回合结束阶段。在此过程中会有多个触发技能的时机，此时会进入到武将子类的技能方法中（重写父类方法）执行。使用手牌（基本牌、锦囊牌、判定牌）时，会进入到该牌的判定过程中，将使用者与该牌的对象进行交互。



## 设计实现

### 管理类

#### GameManager

* 负责游戏宏观运行（每名玩家依次出牌、判定胜负条件、角色死亡等）
* 提供涉及到多个玩家的调用接口
  * 铁索连环伤害
  * 拼点
  * 查询玩家之间的距离

如果将整个游戏理解为操作系统，那么GameManager相当于内核，提供系统调用帮助卡牌和武将完成功能。

#### IO

* 封装系统IO接口，例如输出卡牌信息、获得输入内容


#### Utils

* 提供常用工具包，例如断言、深拷贝、随机整数等



### 牌堆类

#### CardsHeap

* 游戏开始时初始化牌堆，分配手牌
* 负责牌堆和弃牌的管理，提供摸牌、弃牌与判定接口
* 牌堆为空时自动洗牌
* 为诸葛亮、神吕蒙等提供查看牌堆与操控牌堆的接口

#### PeoplePool

* 游戏开始时初始化武将牌，分配武将
* 游戏开始时为玩家分配身份
* 为左慈提供分配化身接口



### 人员类

#### SkillLauncher

接口，设定了一些技能发动时机的方法，默认均为空函数体，Person类实现该接口。若武将需要设置技能，可重写方法。

#### PlayerIO

接口，提供用户选择玩家（由GameManager代为完成）、选择选项、选择卡牌的接口（通过Person类实现`PlayerIO`接口实现）。

#### Attributes

抽象类，设置了翻面、铁索连环、喝酒、死亡、性别、卡牌、装备牌、判定牌等相关属性，以及属性相关的操作，如摸牌弃牌、增减体力等，并内置了所有防具的处理逻辑。

#### Person

抽象类，所有武将的公共父类，武将行为的核心，属性全部封装在Attributes类中，并通过PlayerIO实现了IO接口，主要功能为回合内的完整流程，包括回合开始、判定、摸牌、出牌、弃牌、结束阶段等，核心逻辑为出阶段解析命令并使用卡牌、技能。



### 其余重要类

#### Sha

杀卡牌，继承自BasicCard，包含了杀伤害的属性（火、雷、普通）。调用大多数武器的功能（除诸葛连弩和丈八蛇矛在Person类中），并调用了各个杀相关的技能发动时机方法。

#### Card

抽象类，所有卡牌的公共父类，包括花色、点数、所有者、使用者、目标、[目标二]、是否已被取走（用于决定是否进入弃牌堆）等属性。核心行为是选择卡牌目标。
