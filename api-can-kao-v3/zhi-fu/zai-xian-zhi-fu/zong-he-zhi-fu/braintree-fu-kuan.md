---
description: >-
  使用Braintree来接受PayPal，Venmo，Google Pay和Apple Pay等钱包。
  用Braintree集成时，请同时使用“process”(本文)和“secure-pay”(Yuansfer付款页面)。
---

# Braintree付款

{% api-method method="post" host="https://mapi.yuansfer.com/creditpay" path="/v3/process" %}
{% api-method-summary %}
process
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="paymentMethodNonce" type="string" required=true %}
付款方式的ID。 用于每次单笔付款的单个令牌。
{% endapi-method-parameter %}

{% api-method-parameter name="merchantNo" type="string" required=true %}
商家ID。
{% endapi-method-parameter %}

{% api-method-parameter name="paymentMethod" type="string" required=true %}
标识钱包类型
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID。
{% endapi-method-parameter %}

{% api-method-parameter name="transactionNo" type="string" required=true %}
Yuansfer系统中交易的ID。
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名。
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "result":
    {
        "reference": "a6d19b881699dfea0c8b78e91bc64d42",
        "amount": "22.00",
        "supUserid": "sb-lfgk83666547@business.example.com",
        "transactionNo": "302589410330531000",
        "vendorId": "a902q221",
        "currency": "USD",
        "paymentTime": "2021-01-22T19:23:00Z",
        "status": "success"
    },
    "ret_msg": "success",
    "ret_code": "000100"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### 响应

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| result | object | 结果对象 |
| ret\_msg | string | 响应返回消息。 |
| ret\_code | string | 响应返回码。 了解有关的更多详细信息，请参见[此处](../../../zhu-jie.md#xiang-ying-fan-hui-dai-ma)。 |

#### 结果对象

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| reference | string | 商家系统中交易的发票编号。 |
| amount | number | 交易金额。 |
| supUserid | string | 加密后的钱包用户名或信用卡号。 |
| transactionNo | string | Yuansfer系统中交易的ID。 |
| vendorId | string | 提供者交易ID。 |
| currency | string | 标识货币的三位字符货币代码。 |
| paymentTime | string | 创建交易的日期和时间。 格式：yyyy-MM-dd'T'HH：mm：ss'Z' |
| status | string | 交易状态 |

#### 付款方式

| **钱包** | **数值** |
| :--- | :--- |
| Credit Card | credit\_card |
| PayPal | paypal\_account |
| Venmo | venmo\_account |
| Google Pay | android\_pay\_card |
| Apple Pay | apple\_pay\_card |

{% tabs %}
{% tab title="处理通知请求" %}
```text
{
    "merchantNo": "202333",
    "paymentMethod": "credit_card",
    "paymentMethodNonce": "0cd43d3c-911c-0186-7f2d-7a9b53ced56f",
    "storeNo": "301854",
    "transactionNo": "297553640378707470",
    "verifySign": "893fd2c61aebbfd9b1f4543afb727063"
}
```
{% endtab %}
{% endtabs %}

