# API管理工作原理

API代理解耦了面向应用的API及后台的API服务。当API生产者更换了后台的API服务，仍然可以通过配置API代理，让API消费者继续续访问后台服务。API生产者还可以配置策略于前置流中，对API消费者的API请求和相应中的参数进行控制。

.. image:: media/api_management_workflow.png

在前述流程中，API管理流程有以下步骤：
1. API消费者向API代理发起调用请求；
2. API代理根据API请求参数将其导入相应的API流中；
3. 在API流中，API请求经过前置流根据API策略进行处理，发送给后台API服务；
4. 后台API服务根据处理后的API请求返回响应参数；
5. 响应参数经过API代理按照策略处理后，返回API消费者端。