# 撤销

{% api-method method="post" host="https://mapi.yuansfer.com" path="/auto-debit/v3/revoke" %}
{% api-method-summary %}
revoke
{% endapi-method-summary %}

{% api-method-description %}
撤销接口将用于撤销授权请求。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="merchantNo" type="string" required=true %}
商家ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="autoDebitNo" type="string" required=true %}
自动付款记录ID
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
正确返回数值
{% endapi-method-response-example-description %}

```
{
    "result": {
        "autoDebitNo": "298222562856331071",
        "autoReference": "testAuth2021010801",
        "vendor": "GCASH"
    },
    "ret_code": "000100",
    "ret_msg": "revoke success"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
错误返回数值
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
| autoDebitNo | string | Yuansfer系统中自动付款的唯一ID。 |
| autoReference | string | 商户系统中自动付款的唯一ID。 |
| vendor | string | 付款渠道，可能的值为： **"gcash", "kakaopay", "alipay", "alipay\_hk", "dana", "truemoney", "tng", "easypaisa", "bkash"**. |

{% tabs %}
{% tab title="参数格式" %}
```text
{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "acb359804dd3805da41cbccf23af3a0a",
    "autoDebitNo": "298217806906830305"
}
```
{% endtab %}

{% tab title="正确返回数值" %}
```
{
    "result": {
        "autoDebitNo": "298222562856331071",
        "autoReference": "testAuth2021010801",
        "customerBelongsTo": "GCASH"
    },
    "ret_code": "000100",
    "ret_msg": "revoke success"
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

