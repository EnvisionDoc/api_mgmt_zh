# 有关API管理
EnOS API管理(API Management，APIM)将符合EnOS所支持标准的API发布给API消费者。你可以利用API管理配置特定的策略，对API的参数进行控制和处理，包括API设计、测试、管理、发布等全生命周期管理，并管理受托管API的安全、流控、日志、计费、监控和报表等。

API管理解耦了API的生产与消费。后台API的改动不影响前端的应用通过API管理继续访问该API，前端应用不需要修改代码或配置。



## 相关角色
API管理主要服务于以下角色：

- API开发者

  撰写API文档，设计、开发、测试及上线API。

- API消费者

  通常为应用开发者，使用API构建应用程序的企业或个人。


## 主要功能

- [构建API](creating_api)：创建符合OpenAPI 3.0规范的API。

- [部署API](deploying_api)：部署开发的API供组织内部或第三方使用。

- [备份API](exporting_api)：将已构建的API导出，迁移到其他EnOS环境。

- [测试API](testing_api)：在发布API前对其进行测试。

- [监控API](monitoring_api)：查看API被调用的状况。

## 相关服务

与EnOS APIM 相关的EnOS其他服务有：

- 应用注册

  API消费者注册应用获得服务账号所需服务，以用于访问必要API。关于应用注册的详细内容，请见[应用注册](https://www.envisioniot.com/docs/app-development/zh_CN/latest/app_dev_overview.html)

- IAM

  为APIM提供身份管理、认证、授权、审计等服务。关于IAM的详细内容，请见[IAM](https://www.envisioniot.com/docs/iam/zh_CN/latest/iam_overview.html)




