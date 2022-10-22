---
description: 本页说明了选手可以获取的特殊类型的数据
---

# 基础类声明

### class player 玩家

#### 成员变量

`float x`  玩家的位置的x值

`float y` 玩家的位置的y值

`int hp`  玩家的血量

`int type` 玩家的兵种类型

`int coins` 玩家的金币数

### class rate 速度

#### 成员变量

`float x` x轴的速度分量

`float y` y轴的速度分量

### class bullet 子弹

#### 成员变量

`float x` 子弹的x坐标

`float y` 子弹的y坐标

`rate rates` 子弹的速度

### class enemy 敌人

#### 成员变量

`string name` 敌人的名字,eg:"Player3"

`float x`  敌人的位置的x值

`float y` 敌人的位置的y值

`int hp`  敌人的血量

`int type` 敌人的兵种类型

`int coins` 敌人的金币数

`rate rates` 敌人的速度

### class coin 金币

#### 成员变量

`float x`  金币的位置的x值

`float y` 金币的位置的y值

### class wall 障碍物

成员变量

`float x` 障碍物中心点的x坐标

`float y` 障碍物中心点的y坐标

`float xlength` 障碍物x方向上的长度

`float ylength` 障碍物y方向上的长度