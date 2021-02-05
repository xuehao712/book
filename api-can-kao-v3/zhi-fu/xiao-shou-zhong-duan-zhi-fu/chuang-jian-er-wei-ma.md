---
description: create-trans-qrcode
---

# 创建二维码

此API用于商户展示二维码的用例。 要了解更多信息，请参阅[指南](../../../zhi-nan/xiao-shou-zhong-duan/chuang-jian-er-wei-ma.md)。

{% api-method method="post" host="https://mapi.yuansfer.com/app-instore/v3" path="/create-trans-qrcode" %}
{% api-method-summary %}
create-trans-qrcode
{% endapi-method-summary %}

{% api-method-description %}
该API创建交易并获取二维码，供客户扫描以在交易二维码付款流程中进行付款。 客户使用钱包应用程序扫描此二维码以结帐。
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

{% api-method-parameter name="amount" type="string" required=true %}
交易金额。
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
标识货币的三位字符货币代码。  
可能的值为：“ USD”
{% endapi-method-parameter %}

{% api-method-parameter name="settleCurrency" type="string" required=true %}
结算货币\(用于除USD之外的所有货币\)。
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=true %}
付款方式。   
可能的值为：“ alipay”，“ wechatpay”。  
\(尚不支持“ unionpay”\)
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=true %}
商家系统中交易的发票编号。
{% endapi-method-parameter %}

{% api-method-parameter name="ipnUrl" type="string" required=false %}
即时付款通知处理程序URL。 IPN URL必须是安全的。
{% endapi-method-parameter %}

{% api-method-parameter name="needQrcode" type="string" required=false %}
可能的值为：true或false。 默认值是true。   
如果此参数为true，则Yuansfer系统将创建二维码图像。 如果此参数为false，则Yuansfer系统将不会创建二维码图像。
{% endapi-method-parameter %}

{% api-method-parameter name="timeout" type="integer" required=false %}
超时\(以分钟为单位\)。   
默认值为120。
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
        "reference": "test2020102023",
        "amount": "0.11",
        "deepLink": "https://qr.alipay.com/bax05773sia4dshxhw7100f3",
        "transactionNo": "297553638914321581",
        "settleCurrency": "USD",
        "currency": "USD",
        "timeout": "120",
        "qrcodeUrl": "https://mobilecodec.alipaydev.com/show.htm?code=bax05773sia4dshxhw7100f3&picSize=M"
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
| ret\_code | string | 响应返回码。 了解有关的更多详细信息，请参见[此处](../../zhu-jie.md#xiang-ying-fan-hui-dai-ma)。 |

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
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;<b>(</b>&#x7F8E;&#x5143;)&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">deepLink</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x6DF1;&#x5C42;&#x94FE;&#x63A5;URL&#x3002; (&#x975E;&#x9996;&#x9875;&#x7F51;&#x5740;)</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">settleCurrency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x7ED3;&#x7B97;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x7ED3;&#x7B97;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#x201C;
          CNY&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">timeout</td>
      <td style="text-align:left">integer</td>
      <td style="text-align:left">
        <p>&#x8D85;&#x65F6;(&#x4EE5;&#x5206;&#x949F;&#x4E3A;&#x5355;&#x4F4D;)&#x3002;</p>
        <p>&#x9ED8;&#x8BA4;&#x503C;&#x4E3A;120&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">qrcodeUrl</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x4E8C;&#x7EF4;&#x7801;&#x7684;&#x7F51;&#x5740;&#x3002;</td>
    </tr>
  </tbody>
</table>

{% tabs %}
{% tab title="cURL" %}
```text
curl -XPOST -H "Content-type: application/json" -d '{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "45bfac0286debaf0c316c011d6842d2c",
    "amount": "0.11",
    "currency": "USD",
    "settleCurrency": "USD",
    "reference": "test2020102023",
    "ipnUrl": "http://zk-tys.yunkeguan.com/login/test",
    "needQrcode": "true",
    "vendor": "alipay",
    "timeout": "120"
}' 'https://mapi.yuansfer.com/app-instore/v3/create-trans-qrcode'
```
{% endtab %}

{% tab title="PHP" %}
```php
 <?php
    function transQrcode()
    {
        $url = 'https://mapi.yuansfer.yunkeguan.com/app-data-search/v2/create-trans-qrcode';
        $token = '59600f2a9ad644c6a9570233560cc94e';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'vendor' => 'alipay',
            'amount' => '0.01',
            'ipnUrl' => 'https://nengjtian.s1.natapp.cc/login/test',
            'reference' => 'test2018061901',
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
    transQrcode();
?>
```
{% endtab %}

{% tab title="Java" %}
```java
public static void transQrcode() {
    String url = DOMAIN_URL + TRANS_QRCODE;
    Map<String, Object> params = new TreeMap<String, Object>();
    params.put("merchantNo", MERCHANT_NO);
    params.put("storeNo", STORE_NO);
    if (StringUtils.isNotEmpty(STORE_ADMIN_NO)) {
        params.put("storeAdminNo", STORE_ADMIN_NO);
    }

    params.put("vendor", "alipay");
    params.put("amount", "0.01");
    params.put("ipnUrl", "https://nengjtian.s1.natapp.cc/login/test");
    params.put("reference", "testabc100");
    String verifySign = verifySignHelper.getYuansferVerifySign(params, YUANSFER_TOKEN);
    params.put("verifySign", verifySign);
    String ret = HttpClientUtils.post(url, null, params);
    System.out.println("---trans-qrcode-create ----");
    System.out.println(ret);
}
```
{% endtab %}

{% tab title="Go" %}
```

```
{% endtab %}
{% endtabs %}



