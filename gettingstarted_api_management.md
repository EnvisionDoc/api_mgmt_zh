# API管理快速入门

你可以使用EnOS API管理 (APIM) 将 API 发布给API消费者，以充分发挥其数据和服务的潜力。API的消费者可以通过后台API生成API代理访问后台API的服务。

本快速入门介绍如何创建、部署API，将API发布为公共API，以及如何使用已发布的公共API。

## 开始前准备
- 了解API管理相关[术语](api_management_concepts)；


## 生产API任务描述

API的生产流程如下图所示：

.. image:: media/api_management_production.png

基于该流程图，本示例有以下任务：

  1. 新建或导入API定义；
  2. 通过创建API代理以部署API，配置基本信息及策略；
  3. 测试API；
  4. 公开发布API；



## 步骤1：定义API
为新建API文档，你需要：
1. 登录EnOS控制台，选择 **API管理 > API文档**。

2. 点击 **新建**，根据情况选择 **创建文档** 或 **导入文档**，本文以创建文档为例，选择 **创建文档**。

3. 填写 **名称** 为“SwaggerPetStore”和 **描述** 为“A sample API”。
    .. image:: media/api_spec_create.png

4. 在API文档编辑器中复制[editor.swagger.io](https://editor.swagger.io/)中的代码，点击 **保存**。


## 步骤2：部署API
通过上一步骤，你新建了一个名称为“SwaggerPetStore”的API。本步骤将通过新建的API，快速生成API代理。
1. 选择 **API管理 > API文档**。
2. 在刚创建的SwaggerPetStore一栏，点击 **生成代理** 按钮。
3. 在新API代理详情页，在 **后台服务器URL** 一栏填入“http://petstore.swagger.io”， **超时** 一栏中填入10。

    .. image:: media/api_proxy_new_petstore.png

4. 点击 **保存**，保存生成的API代理，此时API已经部署到了EnOS。


## 步骤3：测试API代理
1. 部署好API后，选择 **API管理 > API代理** ，查看新建的SwaggerPetStore，在详情页复制**URL**中的URL地址；
    .. image:: media/api_proxy_overview.png
2. 选择**API文档**,查看SwaggerPetStore的详情页，在编辑器中将刚才复制的URL粘贴并替换掉原来的服务器URL；
    .. image:: media/api_spec_swaggerpetstore.png
3. 对已配置的API代理进行测试。在编辑器右侧生成的文档中，点击需要测试的方法，点击 **Try it out** 、按要求输入必要参数后，点击 **execute**进行测试。HTTP返回值为200，说明测试通过。
    .. image:: media/api_spec_swaggerpetstore_editor.png

## 步骤4：将API发布为公共API
选择 **API管理 > API代理**，将SwaggerPetStore的部署状态调整为“在线”，可见性调整为“公开”；


.. image:: media/api_proxy_public.png

发布成功的公共API可在**API管理 > 公共API**处查看。

.. image:: media/public_api_swaggerpetstore.png

## 消费API任务描述

消费API的流程如图所示：

.. image:: media/api_management_consumption.png

基于上述流程，本示例有以下任务：
  1. 在**公开API**中查看被 _API开发者_ 公开的可访问API；
  2. 注册或申请应用账号；
  3. 按需为应用账号申请API的访问权限(可能需要向 _API开发者_ 申请)；
  4. 测试公开API；
  5. 通过HTTP客户端，用申请的应用账号及密钥消费API；

## 步骤1：查看可用的公开API
选择 **API管理 > 公共API**，查看并选择需要消费的API。

.. image:: media/public_api_swaggerpetstore.png


## 步骤2：获取API生产者分发API的访问权限

API消费者需要将应用注册在EnOS的某个OU内，然后向API生产者申请，让API生产者通过以下方式向API消费者分发访问权限：

- 如果需要授权的应用位于API生产者的OU，API生产者应选择 **应用管理 > 应用注册 > 组织应用**，点击需要授权的应用。在应用详情页面，将accessKey和secretKey提供给API消费者，用于应用接入EnOS调用API。比如名为APP的应用的开发者需要API生产者的授权，API生产者需要将APP的accessKey和secretKey提供给该应用开发者。
    .. image:: media/app_reg_spec.png

- 如果需要授权的应用位于其他OU，API生产者应选择 **应用注册 > 已购买**，点击 **购买应用** ，在购买应用弹窗中输入已注册应用的APP ID，完成对应用的授权。比如名为“新建测试应用”的APP的开发者需要API生产者授权，该APP位于其他OU内，API生产者需要在 **购买应用** 输入该应用的appId。
    .. image:: media/api_reg_purchase_spec.png
    .. image:: media/app_management_purchase_app.png



## 步骤3：测试公开API

选择 **API管理 > 公共API**，点击已获取授权的API，进入API文档页面，点击任一方法，点击 **Try it out**，按要求输入必要参数，点击**Execute**进行测试，如果返回HTTP码200，即为测试成功。

## 步骤4：通过HTTP客户端消费API

API消费者可以手动封装HTTP请求，参见[调用 EnOS REST API](https://www.envisioniot.com/docs/app-development/zh_CN/latest/call_enos_api)。
