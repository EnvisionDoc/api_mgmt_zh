# 安全机制

在API管理中，API开发者可以通过为API代理设置安全选项来安全防护其开发的API。

## 鉴权机制

创建API代理时，API开发者有以下鉴权机制可以在API代理中设定：

- 不需要鉴权： 默认选项，不推荐使用。
- appKey/appSecret鉴权：通过申请调用API的HTTP请求带有的appKey和appSecret来鉴权。

.. image:: media/api_proxy_new.png

