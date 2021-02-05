# 支付

{% api-method method="post" host=" https://mapi.yuansfer.com/app-instore/v3" path="/pay" %}
{% api-method-summary %}
pay
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

{% api-method-parameter name="storeAdminNo" type="string" required=false %}
商店管理员ID
{% endapi-method-parameter %}

{% api-method-parameter name="transactionNo" type="string" required=false %}
Yuansfer系统中交易的发票编号。  
 transactionNo或reference是必需的。
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
商家系统中交易的发票编号。   
transactionNo或reference是必需的。
{% endapi-method-parameter %}

{% api-method-parameter name="paymentBarcode" type="string" required=true %}
付款方式。   
来自客户的付款条形码。
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=true %}
付款方式。 可能的值为： **"alipay", "wechat", "unionpay", "paypal", "venmo"**.
{% endapi-method-parameter %}

{% api-method-parameter name="verifySign" type="string" required=true %}
参数签名。
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
        "amount": "13.00",
        "createTime": "2020-10-12 21:38:16",
        "currency": "USD",
        "merchantNo": "200043",
        "originalTransactionNo": null,
        "paymentTime": "2020-10-12 22:38:16",
        "reference": "test20200101206",
        "refundAmount": "0.00",
        "settleCurrency": "USD",
        "storeAdminNo": null,
        "storeNo": "300014",
        "transactionNo": "297553638241892410",
        "transactionStatus": "success",
        "transactionType": "payment",
        "voidAmount": "0.00"
    },
    "ret_code": "000100",
    "ret_msg": "add success"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

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

**响应**

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| result | object | 结果对象 |
| ret\_msg | string | 响应返回消息。 |
| ret\_code | string | 响应返回码。 了解有关的更多详细信息，请参见[此处](../../../zhu-jie.md#xiang-ying-fan-hui-dai-ma)。 |

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
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">createTime</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x521B;&#x5EFA;&#x4EA4;&#x6613;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; yyyy-MM-dd HH&#xFF1A;mm&#xFF1A;ss&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#x201C;
          CNY&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">merchantNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">originalTransactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x539F;&#x59CB;&#x4EA4;&#x6613;&#x7684;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">paymentTime</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x4ED8;&#x6B3E;&#x5904;&#x7406;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; yyyy-MM-dd HH&#xFF1A;mm&#xFF1A;ss&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">refundAmount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x9000;&#x6B3E;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">settleCurrency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x8FD9;&#x662F;&#x5C06;&#x5411;&#x5546;&#x5BB6;&#x4ED8;&#x6B3E;&#x7684;&#x8D27;&#x5E01;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">storeAdminNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5E97;&#x7BA1;&#x7406;&#x5458;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">storeNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5E97;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionStatus</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x72B6;&#x6001;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionType</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x4EA4;&#x6613;&#x7C7B;&#x578B;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;<b>&quot;payment&quot;,&quot;refund&quot;,&quot;void&quot;</b>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">voidAmount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x65E0;&#x6548;&#x6216;&#x53D6;&#x6D88;&#x7684;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
  </tbody>
</table>

{% tabs %}
{% tab title="cURL" %}
```text
curl -XPOST -H "Content-type: application/json" -d '{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "f38965887c5676e2fb19d951251eb613",
    "transactionNo": "297553636764407286",
    "paymentBarcode": "286498530672949108",
    "vendor": "alipay"
}' 'https://mapi.yuansfer.com/app-instore/v3/pay'
```
{% endtab %}

{% tab title="PHP" %}
```php
 <?php
    function transPay()
    {
        $url = 'https://mapi.yuansfer.yunkeguan.com/app-data-search/v2/pay';
        $token = '59600f2a9ad644c6a9570233560cc94e';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'transactionNo' => '297553565108438359',
            'vendor' => 'alipay',
            'amount' => '0.01',
            'paymentBarcode' => '280526696410694666'
        ];
        ksort($params, SORT_STRING);
        $str = '';
        foreach ($params as $k => $v) {
            $str .= $k . '=' . $v . '&';
        }
        $params['verifySign'] = md5($str . md5($token));
        echo 'verifySign:', $params['verifySign'];
        echo "\n";
        $ch = curl_init($url);
        curl_setopt_array($ch, array(
            CURLOPT_RETURNTRANSFER => true,
            CURLOPT_HEADER => false,
            CURLOPT_POST => true,
            CURLOPT_POSTFIELDS => http_build_query($params),
        ));
        $result = curl_exec($ch);
        curl_exec($ch);
        echo $result;
        echo "\n";
        return json_decode($result, true);
    }
    transPay();
?>
```
{% endtab %}

{% tab title="Java" %}
```java
public static void transactionPay(String transactionNo) {
    String url = DOMAIN_URL + TRANSACTION_PAY;
    Map<String, Object> params = new TreeMap<String, Object>();
    params.put("merchantNo", MERCHANT_NO);
    params.put("storeNo", STORE_NO);
    if (StringUtils.isNotEmpty(STORE_ADMIN_NO)) {
        params.put("storeAdminNo", STORE_ADMIN_NO);
    }

    params.put("transactionNo", transactionNo);
    params.put("paymentBarcode", "286754322648217439");
    params.put("vendor", "alipay");
    String verifySign = verifySignHelper.getYuansferVerifySign(params, YUANSFER_TOKEN);
    params.put("verifySign", verifySign);
    String ret = HttpClientUtils.post(url, null, params);
    System.out.println("---transaction pay----");
    System.out.println(ret);
}
```
{% endtab %}

{% tab title="Go" %}
```

```
{% endtab %}
{% endtabs %}

