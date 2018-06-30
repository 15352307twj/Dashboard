---
layout: default
title: Usecase design
---
# Owl Design

## 7.5 Usecase design

#### 用例简介

该用例为购票订餐：
用户购票需要：
选择电影 -> 选择电影院 -> 选择场次 -> 选择座位 -> 选择订餐商(可选) -> 选择食物(可选) -> 支付

使用BCE模式画出的顺序图如下：
![Screen Shot 2018-06-30 at 12.39.52 PM](/assets/Screen%20Shot%202018-06-30%20at%2012.39.52%20PM.png)

类图如下：
![Screen Shot 2018-06-30 at 1.57.37 PM](/assets/Screen%20Shot%202018-06-30%20at%201.57.37%20PM.png)

#### 用例简介

本用例包含一个用户最基本的一次使用过程，包括：

1. Log in
2. Search movie
3. Make reservation
4. Make payment

流程图按照BCE模型画出，其中由于领域对象或数据实体太多，我统一使用Entities代表实体对象。在这里Entities是代表一类实体，而不是单一的某种实体。 

类图按照我们项目实际组成的类，以及它们之间的关系画成。 

顺序图

![](https://github.com/Owl-Movies-Ticket-System/Dashboard/blob/gh-pages/assets/lf_shunxutu.png?raw=true)

类图

![](https://github.com/Owl-Movies-Ticket-System/Dashboard/blob/gh-pages/assets/lf_leitu.png?raw=true)

#### 用例简介

本用例包含一个用户选择影院，在该影院中选择电影，订座，支付的过程：

1.	Log in
2.	Choose Theater
3.	Choose Movie
4.	Make Reservation
5.	Make Payment

顺序图，使用BCE模式画出的顺序图如下：
![](https://github.com/Owl-Movies-Ticket-System/Dashboard/blob/gh-pages/assets/7.5UseCase.png?raw=true)

类图与上相同

![](https://github.com/Owl-Movies-Ticket-System/Dashboard/blob/gh-pages/assets/lf_leitu.png?raw=true)

