# 发布API

API测试通过之后，就可以通过API代理发布给API消费者使用。

## 任务描述

本文介绍了通过API代理，将API发布给API消费者以供调用的步骤。

## 开始前准备

- 拥有一个EnOS账号，并拥有发布API操作需要的相应权限，参考[访问控制](api_management_access_control)。
- 了解API管理相关[概念](api_management_concepts)。
- 已经部署了一个API并测试通过。

## 步骤
1. 选择 **API管理 > API代理**；
2. 将需要发布的API代理的 **部署** 修改为 **在线**，API代理即被发布到生产环境；
3. 将需要发布的API代理的 **可见性** 修改为 **公共**，API代理即可被API消费者发现并申请使用。

## 结果

API被公开发布，API消费者可以发现并申请使用该API。

## 后续任务

[删除API](deleting_api)