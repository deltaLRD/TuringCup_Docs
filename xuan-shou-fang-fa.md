---
description: 本页介绍了选手可以操控player所进行的攻击
---

# 选手方法

### 信息获取

#### 函数名

`player getMyself()`

#### 具体说明：

返回一个player，存储玩家自身的相关数据

#### 函数名

`List<enemy> getEnemy()`

#### 具体说明：

返回一个enemy列表，存储周围十米范围内敌方的相关数据

#### 函数名

`List<wall> getWalls()`

#### 具体说明

返回一个wall列表，存储场上所有障碍物的信息

#### 函数名

`List<coin> getCoin()`

#### 具体说明：

返回一个coin列表，存储场上所有金币的信息

#### 函数名

`List<buff> getBuff()`

#### 具体说明

返回一个buff列表，存储场上所有的buff信息

#### 函数名

`List<bullet> getBullet()`

#### 具体说明

返回一个bullet列表，存储场上所有子弹的信息

### 玩家操作

#### 函数名

`void moveTo(float x, float y)`

#### 参数：

`float x` 目标点的x值

`float y` 目标点的y值

#### 具体说明：

让玩家向目标点移动

#### 函数名

`void CloseAttack(float x, float y)`

#### 参数：

`float x` 所要攻击的方向的x值

`float y` 所要攻击的方向的y值

#### 具体说明

近距离攻击会通过判断附近一定范围是否有敌人，敌人是否在攻击方向的一定范围内从而攻击

不同兵种有不同的 `攻击范围 攻击距离 攻击力`

只有当敌人与选手控制的`player`的距离 `<=` 攻击距离

同时攻击方向和敌人的位置的夹角 `<=` 攻击范围

攻击才生效

<figure><img src=".gitbook/assets/test.png" alt=""><figcaption></figcaption></figure>

#### 函数名

`void RemoteAttack(float x, float y)`

#### 参数：

`float x` 所要攻击的方向的x值

`float y` 所要攻击的方向的y值

#### 具体说明：

向目标点发射弓箭，初始默认使用箭袋1，两个箭袋都清空时调用此方法为近战攻击

#### 函数名

`void reload()`

#### 具体说明：

切换箭袋，从箭袋1切换到箭袋2，或者从箭袋2切换到箭袋1，有1秒的换弹时间

#### 函数名

`int ChangeType(int type)`

#### 参数：

`int type` 想要变化的兵种

> `type == 0` 是普通士兵 消耗0分
>
> `type == 1` 是弓箭手 消耗10分
>
> `type == 2` 是骑兵 消耗5分
>
> `type == 3` 是枪兵 消耗5分

#### 具体说明：

无论从什么兵种变化到什么兵种都会消耗对应的分数

> 从弓兵变到枪兵也会消耗5点分数
>
> 再从枪兵变化到弓兵会再消耗10点分数

变化成功会返回 `1`

变化失败会返回`0`

攻击力就是敌人扣的血量

所有兵种攻击速度都是0.5s一次

普通士兵

<pre data-line-numbers><code><strong>攻击范围: float CloseAttackRange = 60 (°)
</strong><strong>攻击距离: float CloseAttackLength = 1 
</strong>攻击力: float Power = 5 
移动速度: float speed = 2</code></pre>

弓兵

{% code overflow="wrap" lineNumbers="true" %}
```
攻击范围: float CloseAttackRange = 50 (°)
攻击距离: float CloseAttackLength = 0.9 
攻击力: float Power = 8 
移动速度: float speed = 2
弓兵有两个箭袋，每个箭袋10只箭，第一个箭袋弓箭速度30m/s，第二个箭袋弓箭速度20m/s，切换箭袋的时间为1s，两个箭袋都用完后变为近战
```
{% endcode %}

枪兵

{% code overflow="wrap" lineNumbers="true" %}
```
攻击范围: float CloseAttackRange = 30 (°)
攻击距离: float CloseAttackLength = 2.5
攻击力: float Power = 10
移动速度: float speed = 2
```
{% endcode %}

骑兵

{% code overflow="wrap" lineNumbers="true" %}
```
攻击范围: float CloseAttackRange = 60 (°)
攻击距离: float CloseAttackLength = 1 
攻击力: float Power = 5 
移动速度: float speed = 5
```
{% endcode %}
