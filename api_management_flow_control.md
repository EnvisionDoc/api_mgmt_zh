# 流量控制

API生产者可以针对API代理层级设置限流措施，按分钟、小时、日、月级别限制调用API次数，此代理下所有API的调用次数总和达到调用上线即被限流，收到HTTP状态码“429 too many requests”。

.. image:: media/api_proxy_new.png
