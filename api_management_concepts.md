# 术语
本文介绍API管理涉及的术语。



<!--## API文档

  符合[OpenAPI 3.0](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.0.md)规范的交互式文档。是位于后端的HTTP服务及操作，不会直接提供给API消费者。-->

<!--## API代理

  包含一个或多个API及其调用策略及配额，通过公开API被消费者调用。-->

<!--## API流

  定义了控制API及其所带信息的处理流程。通常一个代理中的一个API代表一条流。-->

<!--## 前置流

  API请求通过API代理时的必然会经过的API流，前置流会根据API生产者配置的策略对API请求进行预处理。-->

## API组

一个API组包含一个或多个API以及使用配额和策略。可通过EnOS控制台提供给开发人员使用。

## API后端服务

实现API的HTTP服务及其操作。

## API类型

EnOS将API分为以下几种类型：
- 私有：不向第三方公开，仅供本OU在EnOS上使用的API。
- 三方：所有EnOS上的其他OU都可以看到并使用该API。

<!--## API策略

  用于控制API流中API及其所带参数行为的策略。通过配置API策略，可以改变API请求参数的行为。

  典型的API策略包括安全策略、流控策略、参数转换、缓存策略等。
  
## API模型

  API 请求为非Form表单Body传参时，定义的传参模型，通常为JSON对象。

## 应用
  消费API的基本单元，由 _API消费者_ 在[应用注册](https://www.envisioniot.com/docs/app-development/zh_CN/latest/app_dev_overview.html)中进行申请和管理。

## 应用密钥
  应用的身份，与应用为一一对应关系。-->



  


