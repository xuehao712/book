# 支付

{% api-method method="post" host="https://mapi.yuansfer.com" path="/auto-debit/v3/pay" %}
{% api-method-summary %}
pay
{% endapi-method-summary %}

{% api-method-description %}
使用此界面可以根据Yuansfer返回的状态和操作指令来发起付款并处理付款结果。 进行扣除时将使用AccessToken。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="vendor" type="string" required=true %}
支付渠道，可能的数值为： **"alipay", "truemoney", "alipay\_hk", "tng", "alipay\_cn", "gcash", "dana", "kakaopay", "bkash", "easypaisa"**
{% endapi-method-parameter %}

{% api-method-parameter name="merchantNo" type="string" required=true %}
 商家ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="autoDebitNo" type="string" required=true %}
自动付款记录ID
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="string" required=true %}
价格金额
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
标识货币的三位字符货币代码。 可能的值为： **"USD", "CNY", "PHP", "IDR", "KRW", "HKD"**.
{% endapi-method-parameter %}

{% api-method-parameter name="settleCurrency" type="string" required=true %}
结算货币
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=true %}
商家系统中交易的发票编号
{% endapi-method-parameter %}

{% api-method-parameter name="ipnUrl" type="string" required=true %}
异步回调地址
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
正确返回值 
{% endapi-method-response-example-description %}

```
{
    "result": {
        "amount": 100,
        "autoDebitNo": "298222562856331071",
        "currency": "PHP",
        "reference": "test2021010801",
        "transactionNo": "297553645779430418"
    },
    "ret_code": "000100",
    "ret_msg": "pay success"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
 错误返回值
{% endapi-method-response-example-description %}

```
{
   "ret_code": "000000",
   "retMsg": "data error : verifySign",
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
| amount | string | 价格金额 |
| autoDebitNo | string | Yuansfer系统中自动付款记录的唯一ID。 |
| currency | string | 标识货币的三字符货币代码。 可能的值为：**"USD", "CNY", "PHP", "IDR", "KRW", "HKD"**. |
| settleCurrency | string | 用于结算的货币。 |
| reference | string | 商家系统中交易的发票编号。 |
| transactionNo | string | 交易的唯一ID。 |

{% tabs %}
{% tab title="参数格式 " %}
```text
{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "cec6cc1dc16c399f68b66d74f8e363f5",
    "autoDebitNo": "298222562856331071",
    "amount": "100",
    "currency": "PHP",
    "settleCurrency": "USD",
    "reference": "test2021010801",
    "ipnUrl": "http://zk-tys.yunkeguan.com/ttest/test"
}
```
{% endtab %}

{% tab title="正确返回数值" %}
```
{
    "result": {
        "amount": 100,
        "autoDebitNo": "298222562856331071",
        "currency": "PHP",
        "settleCurrency": "USD",
        "reference": "test2021010801",
        "transactionNo": "297553645779430418"
    },
    "ret_code": "000100",
    "ret_msg": "pay success"
}
```
{% endtab %}

{% tab title="错误返回数值" %}
```
{
   "ret_code": "000000",
   "ret_msg": "data error : verifySign",
}
```
{% endtab %}
{% endtabs %}

