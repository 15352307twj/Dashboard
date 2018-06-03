---
layout: default
title: Software Architecture Document
---

# Owl Design

## 7.4 Software Architecture Document

### 架构问题
- **可恢复性 - 使用过程中服务器中断需要进行恢复**
**因素：**
跳转到某一个页面后服务器中断，无法拉取消息，需要恢复
正在进行购票操作填写信息时服务器中断，需要进行恢复

### 解决方案说明


### 逻辑视图

### 物理视图
![physic_model](/assets/physic_model.png)