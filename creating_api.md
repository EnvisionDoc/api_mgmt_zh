# 构建API

为了将自己的API发布在EnOS上，以供授权的使用者调用，用户需要首先在API管理中定义自己的API。

## 任务描述

本文介绍了如何在API管理中创建API。

## 开始前准备

- 拥有一个EnOS账号，并拥有定义API操作需要的相应权限，参考[策略，角色，与权限](/docs/iam/zh_CN/latest/access_policy)。


## 步骤

### 新建API组 <createapigroup>

1. 选择 **API管理 > 我的API**。

2. 点击**新建API组**，填入以下字段：
   
   - 分组名称：支持英文大小写、数字、连字符(-)，不超过32个字符；
   - 分组路径
   - 分组描述：不超过140个字符

3. 点击**保存**，完成API组的创建。



### API基本信息 <basicinfo>

1. 点击已创建的API组，在**基本信息**页，点击**添加API**。
   
2. 在API基本信息页，填入下列字段后点击**下一步**：
   - API名称
   - API类型
      - 私有：平台内部使用接口，如开发测试用API
      - 二方：平台内部接口需对外提供服务，如EnOS API
      - 三方：领域内部接口或外部接口，如天气服务API
   - 验证方式
   - API描述


### API后端服务 <backend>

配置API后端服务，以EnOS API中[Get Device](/docs/api/zh_CN/latest/connect/get_device.html)的API挂载为例，按照API文档配置参数。

.. image:: media/api_backend.png

1. 在**API后端服务**页配置以下信息：
   
   - 后端服务地址：即实际提供该API服务的HTTP地址及端口号。

   - HTTP Method：目前EnOS支持GET、POST、PUT、DELETE。

   - 后端请求路径：提供该API服务的资源所在路径。

   - 入参请求模式：API网关对入参的处理模式，支持**透传**和**映射**。

      - 映射：API网关在接收到API请求时，通过映射关系将请求转换成后端需要的格式。
      - 透传：API网关在接收到API请求后，不对请求进行处理，直接转发到后端服务。
   
   - 后端超时时间：指API请求到达API网关后，API网关调用API后端服务的响应时间，即由API网关请求后端服务开始直至API网关收到后端返回结果的时长。单位为毫秒。如果响应时间超过该值，API网关会放弃请求后端服务，并给用户返回相应的错误信息。
   
   - 后端参数：即调用后端服务所需要的参数。以[Get Device](/docs/api/zh_CN/dev/connect/get_device.html)为例，包含`orgId`和`assetId`。
      - 参数名
      - 参数位置：参数在请求中的位置，可选Head、Query和Path。
      - 数据类型：字段的类型，支持String、Int、Long、Float、Double、Boolean、Binary、Date、DateTime、Password。
      - 是否必选
      - 默认值
      - 描述
   
   - 常量参数：对API使用者不可见，但是API网关会在中转请求时，将这些参数加入到请求中的指定位置，再传递至后端服务，实现后端的业务需求。
      - 参数名
      - 参数位置：常量参数在请求中的位置，支持Head和Query
      - Mapping
      - 默认值
      - 描述


2. 完成后点击**下一步**。

### API请求 <request>

配置请求API。根据API版本迭代的命名标准，对当前API的进行版本管控。如果在**API后端服务**中选择的**入参请求模式**是**透传**，那么在API请求中**请求路径**与后端请求路径保持一致。

1. 在API请求页，填写下列字段：

   - API版本：用以标识API的不同版本，同一个API的不同版本可以挂载在同一个API组下面。 

   - 请求路径：API使用者为调用该API所使用的路径。如在**API后端服务**中选择的入参请求模式为**映射**，则请求路径可以根据需要由API开发者进行设定；如果入参请求模式为**透传**，请求路径与后端请求路径保持一致。

   - API参数定义：当**入参请求模式**为**映射**时，需要设定API请求的参数定义。API参数定义包含下列字段：
      - 参数名：展示给API使用者的参数名称
      - 后端参数名：参数所映射的后端参数
      - 参数位置：参数在请求中的位置
      - 后端参数位置：对应的后端参数在API网关转发来的请求中的位置
      - 数据类型：字段的类型
      - 后端数据类型：对应的后端数据类型
      - 是否必填
      - 默认值
      - 描述

   上述字段中，**参数名**、**是否必选**、**默认值**、**描述**由用户自己设定，其他字段会自动匹配**API后端服务**页上后端参数的响应字段。

2. 完成后点击**下一步**。


### 返回结果 <response>

1. 在返回结果页，写入返回结果，根据EnOS API文档，填入返回示例结果信息、定义响应参数和错误代码。
   - Content Type

   - 成功结果示例

   - 失败结果示例：可选字段。

   - 错误码定义

2. 完成后点击**下一步**。


### 插件配置 <plugin>

APIM为每一个API都提供功能丰富的插件服务。点击**添加插件**下的“+”添加插件。目前可供使用的插件服务有流量控制、黑白名单以及MOCK测试。

1. 在插件配置页，用户可以为将要发布在EnOS的API增加额外配置，当前EnOS支持下列功能：
   - 流量控制
      - 频率限制
      - 请求大小限制
   - IP限制
   - Mock测试

2. 点击**完成**。

## 结果

在API组详情页，可以看到创建成功的API，当前该API的状态为**下线**，是否公开为**私有**。

## 后续操作

[部署API](deploying_api)