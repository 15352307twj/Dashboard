---
layout: default
title: Software Architecture Document
---

# Owl Design

## 7.4 Software Architecture Document

### 架构问题
- 可靠性——用户重复提交订单的问题

### 解决方案说明
- 解决方案概要：使用一个实时生成的token判断用户是否重复提交。
- 因素：防止用户重复提交订单。
- 解决方案：在前端部分为提交的订单生成一个token储存在会话中，提交订单时检测token是否已经存在，若存在则判断为重复提交订单。token会有一个时间戳，超过特定时间（如1分钟）就会被会话丢弃。
- 动机：很显然，如果用户重复提交订单会出现逻辑错误（如座位号冲突等）。

### 逻辑视图
![logic_view](/assets/logic_view.png)

### 物理视图
![physic_model](/assets/physic_model.png)