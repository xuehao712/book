# 取消

{% api-method method="post" host="https://mapi.yuansfer.com/app-data-search/v3" path="/cancel" %}
{% api-method-summary %}
cancel
{% endapi-method-summary %}

{% api-method-description %}
该API取消交易付款。   
**注意**：   
如果**支付**API的支付结果失败，则Yuansfer系统将取消交易。   
如果**支付**API的支付结果成功，则Yuansfer系统将退还交易金额。
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

{% api-method-parameter name="transactionNo" type="string" required=false %}
商家系统中交易的发票编号。  
 transactionNo或reference是必需的。
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
商家系统中交易的发票编号。   
transactionNo或reference是必需的。
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
        "amount": 0.01,
        "currency": "USD",
        "reference": "test20200101307",
        "status": "closed",
        "transactionNo": "297553638302751118"
    },
    "ret_msg": "cancel success ",
    "ret_code": "000100"
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
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D; &#x201C;
          CNY&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x9000;&#x6B3E;&#x72B6;&#x6001;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x57FA;&#x4E8E;Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x9000;&#x6B3E;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
  </tbody>
</table>

{% tabs %}
{% tab title="cURL" %}
```text
curl -XPOST -H "Content-type: application/json" -d '{
	"merchantNo": "200043",
	"storeNo": "300014",
	"verifySign": "dd81f7781603bec48ae2c6a9ac758bf2",
	"transactionNo": "297553638301777927",
}' 'https://mapi.yuansfer.com/app-data-search/v3/cancel'
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
    function transCancel()
    {
        $url = 'https://mapi.yuansfer.yunkeguan.com/app-data-search/v2/cancel';
        $token = '59600f2a9ad644c6a9570233560cc94e';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'transactionNo' => '297553565108438359'
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
    transCancel();
?>
```
{% endtab %}

{% tab title="Java" %}
```java
public static void transactionCancel(String transactionNo) {
    String url = DOMAIN_URL + TRANSACTION_CANCEL;
    Map<String, Object> params = new TreeMap<String, Object>();
    params.put("merchantNo", MERCHANT_NO);
    params.put("storeNo", STORE_NO);
    if (StringUtils.isNotEmpty(STORE_ADMIN_NO)) {
        params.put("storeAdminNo", STORE_ADMIN_NO);
    }

    params.put("transactionNo", transactionNo);
    String verifySign = verifySignHelper.getYuansferVerifySign(params, YUANSFER_TOKEN);
    params.put("verifySign", verifySign);
    String ret = HttpClientUtils.post(url, null, params);
    System.out.println("---transaction reverse----");
    System.out.println(ret);
}
```
{% endtab %}

{% tab title="Go" %}
```

```
{% endtab %}
{% endtabs %}

