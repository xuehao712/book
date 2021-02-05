# 销售终端

### 总览

Yuansfer POS合作伙伴可以让他们的商家接受PayPal，Venmo，AliPay和其他Yuansfer支持的钱包。以上几种钱包可用于实体店的POS的支付方式。

为了实现店内付款，合作伙伴将与Yuansfer API集成。 这些API公开了RESTful的端点，将允许合作伙伴在其POS上执行付款，取消和退款等操作。

{% hint "info" %}
如果想要成为POS合作伙伴，请联系 [Yuansfer客服团队](https://www.yuansfer.com/contact)。
{% endhint %}

**Yuansfer的店内二维码付款有两种可实现的用例：**

1. 扫描二维码，其中钱包应用程序显示要由POS机扫描二维码。
2. 创建二维码，其中POS显示要由电子钱包应用程序扫描二维码。

### 含义

| **术语** | **含义** |
| :--- | :--- |
| QR Code | 二维码，代表钱包交易标识符的二维条形码。 |
| Onboarding | 为新的合作伙伴和位置创建帐户，配置文件和凭据的过程。 |
| Wallet App | 钱包应用程序是用户进行店内付款的便捷解决方案，可以在与移动钱包服务提供商一起列出的商家店里使用。 |
| POS | 销售终端机用于在实体店进行购买与消费产品然后付款。 |
| Reversal | 交易出现错误或对请求的响应不足后，撤消付款交易的过程。 |

### POS实践

1. POS应该提供二维码扫描选项，以便当客户想要使用电子钱包应用付款时。 POS扫描二维码并自动识别钱包类型。扫描二维码后，POS机便会显示钱包类型并将扫描的二维码发送到Yuansfer系统。
2. POS应该能够向收银员清楚地显示交易状态。例如。 “正在处理”，“已批准”，“已拒绝”（由提供商），“等待客户确认”，“已取消客户”等。POS应显示“正在处理”，直到收到响应为止，此时状态为“由API响应确定。 
3. 收银员应有一种取消交易的方法，以便在客户的电话出现问题且交易无法完成的情况下，防止POS卡在检查状态。 
4. 所有交易应在合理的时限内完成，并在由于任何意外原因而无法完成交易时显示警告消息。

您可以使用[添加](../../api-can-kao-v3/zhi-fu/xiao-shou-zhong-duan-zhi-fu/sao-miao-er-wei-ma/tian-jia.md)，[支付](../../api-can-kao-v3/zhi-fu/xiao-shou-zhong-duan-zhi-fu/sao-miao-er-wei-ma/zhi-fu.md)，[创建二维码](../../api-can-kao-v3/zhi-fu/xiao-shou-zhong-duan-zhi-fu/chuang-jian-er-wei-ma.md) API进行POS\(店内\)集成。

