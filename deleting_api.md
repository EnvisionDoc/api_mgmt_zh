# 删除API

对于不再需要发布在EnOS的API，用户可以选择将其删除。删除API并不会影响该API代理的后台服务。

## 任务描述

本文描述了通过API管理进行删除API的操作。

## 开始前准备

- 拥有一个EnOS账号，并拥有定义API操作需要的相应权限，参考[策略，角色，与权限](/docs/iam/zh_CN/latest/access_policy)。
- 已经完成了[构建API](creating_api)。

## 步骤

1. 选择 **API管理 > 我的API**，点击需要删除的API所在的API组。

2. 在API列表中，首先确保需要删除的API状态为**下线**。

3. 点击**删除API**。

## 结果

API使用者无法继续使用该API调用后台服务。对后台服务无影响。
