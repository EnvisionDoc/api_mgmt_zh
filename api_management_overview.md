# 有关API管理
EnOS API管理(API Management，APIM)将符合EnOS所支持标准的API通过代理，发布给API消费者。你可以利用API管理配置特定的策略，对API的参数进行控制和处理。包括API设计、测试、管理、发布等全生命周期管理，并管理受托管API的安全、流控、日志、计费、监控和报表等。

API管理通过代理，解耦了API的生产与消费。后台API的改动不影响前端的app通过代理继续访问该API,前端app不需要修改代码或配置。



## 相关角色
API管理主要服务于以下角色：

- API 开发者

  撰写API文档，设计、开发、测试及上线API。

- API 消费者

  通常为App开发者，使用API构建应用程序的企业或个人。


## 主要功能
- 定义API

  _API开发者_ 可以创建或导入符合OpenAPI 3.0规范的API、测试API。

- 部署API

  _API开发者_ 可以创建或导入API代理、测试代理、创建代理策略，通过API代理部署自己开发的API。

- API文档查询

  _API消费者_ 可以查询、选择并申请使用已发布的公共API。

## 相关服务

与EnOS APIM 相关的EnOS其他服务有：

- 应用注册

  API消费者注册应用获得服务账号所需服务，以用于访问必要API。关于应用注册的详细内容，请见[应用注册](https://www.envisioniot.com/docs/app-development/zh_CN/latest/app_dev_overview.html)

- IAM

  为APIM提供身份管理、认证、授权、审计等服务。关于IAM的详细内容，请见[IAM](https://www.envisioniot.com/docs/iam/zh_CN/latest/iam_overview.html)




