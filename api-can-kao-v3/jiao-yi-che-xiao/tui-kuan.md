# 退款

{% api-method method="post" host=" https://mapi.yuansfer.com/app-data-search/v3" path="/refund" %}
{% api-method-summary %}
refund
{% endapi-method-summary %}

{% api-method-description %}
该API退还交易付款。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="merchantNo" type="string" required=true %}
商户ID
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo	" type="string" required=true %}
商店ID
{% endapi-method-parameter %}

{% api-method-parameter name="refundAmount" type="string" required=true %}
退款金额\(以价格货币来计算\)。
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="number" required=true %}
标识货币的三位字符货币代码。   
可能的值为：“ USD”
{% endapi-method-parameter %}

{% api-method-parameter name="settleCurrency" type="number" required=true %}
结算货币\(用于除USD之外的所有货币\)。
{% endapi-method-parameter %}

{% api-method-parameter name="transactionNo" type="string" required=false %}
Yuansfer系统中交易的发票编号。  
transactionNo或reference是必需的。
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
商家系统中交易的发票编号。   
transactionNo或reference是必需的。
{% endapi-method-parameter %}

{% api-method-parameter name="refundReference" type="string" required=false %}
商家系统中退款交易的ID。
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
        "amount": "0.01",
        "currency": "USD",
        "reference": "test20200101306",
        "refundAmount": "0.01",
        "refundReference": "refund2020101305",
        "refundTransactionNo": "297553638302358781",
        "settleCurrency": "USD",
        "status": "success",
        "transactionNo": "297553638301777927"
    },
    "ret_msg": "refund success ",
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

**结果对象**

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
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;</td>
    </tr>
    <tr>
      <td style="text-align:left">refundAmount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x9000;&#x6B3E;&#x91D1;&#x989D;&#x3002; &#x4EC5;&#x5F53;&#x4ED8;&#x6B3E;&#x8BA2;&#x5355;&#x5305;&#x542B;&#x201C;Amount&#x201D;&#x65F6;&#x624D;&#x8FD4;&#x56DE;&#x6B64;&#x53C2;&#x6570;&#x3002;</td>
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
      <td style="text-align:left">settleCurrency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x7ED3;&#x7B97;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x9000;&#x6B3E;&#x72B6;&#x6001;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">refundReference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x9000;&#x6B3E;&#x4EA4;&#x6613;&#x7684;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">refundTransactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x9000;&#x6B3E;&#x4EA4;&#x6613;&#x7684;ID&#x3002;</td>
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
    "refundAmount": "0.01",
    "currency": "USD",
    "settleCurrency": "USD",
    "transactionNo": "297553638301777927",
    "refundReference": "refund2020101305"
}' 'https://mapi.yuansfer.com/app-data-search/v3/refund'
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
    function securepayRefund()
    {
        $url = 'https://mapi.yuansfer.com/app-data-search/v2/refund';
        $token = '5cbfb079f15b150122261c8537086d77a';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'amount' => '0.01',
            'reference' => 'test2018070101'];
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
    securepayRefund();
?>
```
{% endtab %}

{% tab title="Java" %}
```java
public class SecurepayRefundTest {
    public static final String TEST_URL = "https://mapi.yuansfer.yunkeguan.com";            //Testing domain
    public static final String PROD_URL = "https://mapi.yuansfer.com";                      //Production domain
    public static final String YUANSFER_TOKEN = "5c5fe30183be69fceff8174358d4b8ae";

    public static void main(String[] args) {
        YuansferSecurepayRefundDto refundDto = new YuansferSecurepayRefundDto();
        YuansferVerifySignHelper verifyHelper = new YuansferVerifySignHelper();
        refundDto.setAmount("0.01");
        refundDto.setCurrency("USD");
        refundDto.setMerchantNo("200043");
        refundDto.setStoreNo("300014");
        refundDto.setReference("9091023122");


        Map<String, Object> params = ReflectionUtils.convertBean2MapIgnoreNullVal(refundDto, new String[]{"serialVersionUID"});
        String verifySign = verifyHelper.getYuansferVerifySign(params, YUANSFER_TOKEN);
        refundDto.setVerifySign(verifySign);
        params.put("verifySign", verifySign);

        String url = TEST_URL + "/app-data-search/v2/refund";
        String ret = HttpClientUtils.post(url, null, params);
        JSON json = JSON.parseObject(ret);
        System.out.println(json);
    }
}
```
{% endtab %}

{% tab title="Go" %}
```go
func refund(t *table) {
    req := yuan.Refund{
        MerchantNo:       "200043", //customer The merchant NO.
        StoreNo:          "300014",
        Currency:         "USD",
        Reference:        "original sequence No.", //sequence number of customer system
        Amount:           "0.01",
    }

    resp, err := req.PostToYuansfer(yuansferToken)
    if err != nil {
        fmt.Println(err)
        return
    }
    fmt.Println(resp)
}
```
{% endtab %}
{% endtabs %}

