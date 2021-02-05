---
description: 如果要进行付款，请将POST请求发送到付款端点，并在请求正文中以JSON格式包含付款详细信息。 然后，将金额发送给收款人以完成付款。
---

# 发送金额

{% api-method method="post" host="https://mapi.yuansfer.com" path="/v3/payouts/pay" %}
{% api-method-summary %}
pay
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="invoiceId" type="string" required=true %}
商家系统中交易的发票编号。
{% endapi-method-parameter %}

{% api-method-parameter name="subject" type="string" required=true %}
付款完成后发送的电子邮件的主题行。
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
标识货币的三位字符货币代码。   
可能的值为：**"USD", "CNY", "PHP", "IDR", "KRW", "HKD"**.
{% endapi-method-parameter %}

{% api-method-parameter name="merchantNo" type="string" required=true %}
商户ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="string" required=true %}
交易金额。
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=true %}
付款渠道。   
可能的值为：**"alipay", "wechatpay", "paypal", "venmo", "unionpay", "creditcard", "truemoney", "alipay\_hk", "tng", "alipay\_cn", "kakaopay", "bkash", "easypaisa**".
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名。
{% endapi-method-parameter %}

{% api-method-parameter name="ipnUrl" type="string" required=false %}
异步回调地址。 IPN网址必须是安全的。
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
在发票上显示的交易说明。
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
发件人指定的付款记录。
{% endapi-method-parameter %}

{% api-method-parameter name="language" type="string" required=false %}
标识正在使用的人类语言。
{% endapi-method-parameter %}

{% api-method-parameter name="customerNo" type="string" required=false %}
Yuansfer系统中的接收方ID
{% endapi-method-parameter %}

{% api-method-parameter name="receiver" type="string" required=true %}
收款方。
{% endapi-method-parameter %}

{% api-method-parameter name="receiverType" type="string" required=true %}
使用receiver时需要。 可能的值为： **"EMAIL", "PHONE", "PAYPAL\_ID"**.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
     "result": {
          "amount": "10.00",
          "receiver": "sb-lfgk83666547@business.example.com",
          "transactionNo": "303768502875460668",
          "createdTime": "2021-01-18T02:19:00Z",
          "invoiceId": "20210118101801",
          "currency": "USD",
          "status": "pending"
    },
    "ret_msg": "payout created",
    "ret_code": "000100"
        
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
| ret\_code | string | 响应返回码。 了解有关的更多详细信息，请参见[此处](../zhu-jie.md#xiang-ying-fan-hui-dai-ma)。 |

#### 结果对象

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#x53C2;&#x6570;</b>
      </th>
      <th style="text-align:left"><b>&#x7C7B;&#x578B;</b>
      </th>
      <th style="text-align:left"><b>&#x8BF4;&#x660E;</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;(&#x7F8E;&#x5143;)&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">receiver</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x6536;&#x6B3E;&#x65B9;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">createdTime</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x521B;&#x5EFA;&#x4EA4;&#x6613;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; yyyy-MM-dd HH&#xFF1A;mm&#xFF1A;ss&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">invoiceId</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A; <b>&quot;USD&quot;, &quot;CNY&quot;, &quot;PHP&quot;, &quot;IDR&quot;, &quot;KRW&quot;, &quot;HKD&quot;</b>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x72B6;&#x6001;</td>
    </tr>
  </tbody>
</table>

#### 支出项目状态

| **状态** | **说明** |
| :--- | :--- |
| success | 资金已计入收款方的帐户 |
| pending | 您的付款要求已收到，将被处理 |
| failed | 此付款请求失败，因此未从发送者的帐户中扣除资金 |
| returned | 收款人尚未领取此款项，因此资金已退还到您的帐户中 |
| refunded | 此付款请求已退还 |
| reversed | 此付款请求已撤消 |
| unclaimed | 此付款的接收者没有PayPal帐户。 注册PayPal帐户的链接已发送给收件人 |
| onhold | 此付款请求正在审核中，已暂停 |
| blocked | 此付款请求已被阻止 |

{% tabs %}
{% tab title="支出通知请求" %}
```text
{
    "amount": "10.00",
    "currency": "USD",
    "invoiceId": "20210118101801",
    "paymentTime": "2021-01-18T02:19:05Z",
    "receiver": "sb-lfgk83666547@business.example.com",
    "status": "success",
    "transactionNo": "303768502875460668",
    "vendor": "PAYPAL",
    "verifySign": "b091c63b56948c2066d4410e71a25d99"
}
```
{% endtab %}
{% endtabs %}

