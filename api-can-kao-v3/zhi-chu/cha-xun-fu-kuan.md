# 查询付款

{% api-method method="post" host="https://mapi.yuansfer.com" path="/v3/payouts/inquiry" %}
{% api-method-summary %}
inquiry
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="merchantNo" type="string" required=true %}
商户ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名。
{% endapi-method-parameter %}

{% api-method-parameter name="invoiceId" type="string" required=true %}
商家系统中交易的发票编号。
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
    "ret_msg": "query success",
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
      <td style="text-align:left">string</td>
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
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;ID&#x3002;</td>
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
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#xFF0C;&#x201C;
          CNY&#x201D;&#xFF0C;&#x201C; PHP&#x201D;&#xFF0C;&#x201C; IDR&#x201D;&#xFF0C;&#x201C;
          KRW&#x201D;&#xFF0C;&#x201C; HKD&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x72B6;&#x6001;&#x3002;</td>
    </tr>
  </tbody>
</table>

