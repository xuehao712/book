# 授权

{% api-method method="post" host="https://mapi.yuansfer.com" path="/auto-debit/v3/consult" %}
{% api-method-summary %}
consult
{% endapi-method-summary %}

{% api-method-description %}
使用此界面可以为在Yuansfer发生的授权启动授权验证URL的授权。 根据请求中的信息授权用户。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="vendor" type="string" required=true %}
付款渠道。 可能的值是：“ alipay”，“ truemoney”，“ alipay\_hk”，“ tng”，“ alipay\_cn”，“ gcash”，“ dana”，“ kakaopay”，“ bkash”，“ easypaisa”
{% endapi-method-parameter %}

{% api-method-parameter name="merchantNo" type="string" required=true %}
商家ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
付款注释
{% endapi-method-parameter %}

{% api-method-parameter name="osType" type="string" required=true %}
当终端是WAP或APP时，我们需要此参数，可能的值为“ IOS”，“ ANDROID”
{% endapi-method-parameter %}

{% api-method-parameter name="osVersion" type="string" required=true %}
当终端是WAP或APP时，我们需要此参数
{% endapi-method-parameter %}

{% api-method-parameter name="autoIpnUrl" type="string" required=false %}
异步回调地址\(注意：如果在完成用户授权后将autoIpnUrl设置为null，则Yuansfer将发送异步回调通知，其中包含诸如autoDebitNo，autoReference，customerBelongsTo，time，note和verifySign之类的参数\)
{% endapi-method-parameter %}

{% api-method-parameter name="autoRedirectUrl" type="string" required=true %}
同步回调地址
{% endapi-method-parameter %}

{% api-method-parameter name="autoReference" type="string" required=true %}
商户系统中自动借记的发票编号
{% endapi-method-parameter %}

{% api-method-parameter name="terminal" type="string" required=true %}
可能的值为：“ ONLINE”，“ WAP”，“ APP”
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
        "authUrl": "https://render.alipay.com/p/c/jzmcoal2/gcash-login?callback=http%3A%2F%2Fzk-tys.yunkeguan.com%2FappIpnCallbackNotify%2Fauto-auth-redirect%2F298222562856331071&authState=298222562856331071&county=US&merchantId=21881101806601J7&merchantName=Yuansfer_Cashier",
        "autoDebitNo": "298222562856331071",
        "autoReference": "testAuth2021010801",
        "vendor": "GCASH"
    },
    "ret_code": "000100",
    "ret_msg": "consult success"
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
| authUrl | string | 用户重定向到该URL以签署合同。 |
| autoDebitNo | string | Yuansfer系统中自动付款的唯一ID。 |
| autoReference | string | 商户系统中自动付款的唯一ID。 |
| vendor | string | 支付渠道，可能的值： **"gcash", "kakaopay", "alipay", "alipay\_hk", "dana", "truemoney", "tng", "easypaisa", "bkash"**. |

{% tabs %}
{% tab title="参数格式" %}
```text
{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "dc6a38102a63a5e3527589679d9ecc9f",
    "vendor": "GCASH",
    "autoIpnUrl": "http://zk-tys.yunkeguan.com/ttest/test",
    "autoRedirectUrl": "http://zk-tys.yunkeguan.com/ttest/test2",
    "autoReference": "testAuth2021010801",
    "terminal": "ONLINE",
    "osType": "IOS",
    "osVersion": "14.0.0.1"
}
```
{% endtab %}

{% tab title="正确返回数值" %}
```
{
    "result": {
        "authUrl": "https://render.alipay.com/p/c/jzmcoal2/gcash-login?callback=http%3A%2F%2Fzk-tys.yunkeguan.com%2FappIpnCallbackNotify%2Fauto-auth-redirect%2F298222562856331071&authState=298222562856331071&county=US&merchantId=21881101806601J7&merchantName=Yuansfer_Cashier",
        "autoDebitNo": "298222562856331071",
        "autoReference": "testAuth2021010801",
        "vendor": "GCASH"
    },
    "ret_code": "000100",
    "ret_msg": "consult success"
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

