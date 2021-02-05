# Yuansfer付款

{% api-method method="post" host="https://mapi.yuansfer.com/online/v3" path="/secure-pay" %}
{% api-method-summary %}
secure-pay
{% endapi-method-summary %}

{% api-method-description %}
 这将用来支付订单。
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

{% api-method-parameter name="amount" type="string" required=true %}
交易金额
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=true %}
交易货币; USD, CNY, PHP, IDR, KRW, HKD
{% endapi-method-parameter %}

{% api-method-parameter name="settleCurrency" type="string" required=false %}
结算货币\(用于除USD以外的所有货币\)。
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=true %}
支付渠道。  
可能的数值: **"alipay", "wechatpay", "paypal",  "venmo", "unionpay", "creditcard" "truemoney", "alipay\_hk", "tng", "gcash", "dana", "kakaopay", "bkash", "easypaisa"**.
{% endapi-method-parameter %}

{% api-method-parameter name="ipnUrl" type="string" required=true %}
异步回调地址， IPN网址必须是安全可靠的。
{% endapi-method-parameter %}

{% api-method-parameter name="callbackUrl" type="string" required=true %}
同步回调HTTP地址，用于接收事件的通知消息。 回调网址需遵循宏替换规则，例如 `xxxcallback_url?trans_no={amount}&amount={amount}`，然后Yuansfer将自动替换有关参数列表{}里的值。
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=false %}
商家系统中交易的发票编号。
{% endapi-method-parameter %}

{% api-method-parameter name="terminal" type="string" required=true %}
可能的数值: **"ONLINE"**, **"WAP", "YIP"**.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
显示在发票上面的交易说明。
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
付款注释。
{% endapi-method-parameter %}

{% api-method-parameter name="osType" type="string" required=false %}
当终端为WAP或APP时，我们需要此参数，可能的值为“ IOS”，“ ANDROID”。
{% endapi-method-parameter %}

{% api-method-parameter name="timeout" type="integer" required=false %}
超时\(以分钟为单位\)。   
默认值为120。
{% endapi-method-parameter %}

{% api-method-parameter name="goodsInfo" type="string" required=true %}
客户从商家购买的商品数组的JSON编码字符串。   
不支持特殊字符。  
例如: \[{"goods\_name":"name1", "quantity":"quantity1"}, {"goods\_name":"name2", "quantity":"quantity2"}\]
{% endapi-method-parameter %}

{% api-method-parameter name="creditType" type="string" required=false %}
付款类型。 仅在vendor为“creditcard”时才需要。 可能的数值为“normal”或“recurring”。 默认值为“normal”。
{% endapi-method-parameter %}

{% api-method-parameter name="paymentCount" type="integer" required=false %}
自动扣除的数量。 仅当vendor为“creditcard”且credittype为“recurring”时才需要查询。   
新的paymentCount值必须大于当前设置，如果无限制的话，设置为0。
{% endapi-method-parameter %}

{% api-method-parameter name="frequency" type="integer" required=false %}
自动扣除的频率。 仅当vendor为“creditcard”，credittype为“recurring”且unit为“Day”时才需要
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
        "cashierUrl": "http://zk-tys.yunkeguan.com/appTransaction/yuansfer-redirect-record/297553638298245023",
        "currency": "PHP",
        "reference": "test202001011303",
        "settleCurrency": "USD",
        "transactionNo": "297553638298245023"
    },
    "ret_code": "000100",
    "ret_msg": "prepay success "
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

\*\*\*\*

#### 响应

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| result | object | 结果对象。 |
| ret\_msg | string | 响应返回消息。 |
| ret\_code | string | 响应返回码。 想了解有关的更多详细信息，请参见[此处](../../zhu-jie.md#xiang-ying-fan-hui-dai-ma)。 |

**结果对象**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;&#x3002; &#x5F53;&#x60A8;&#x4F7F;&#x7528;USD&#x4F5C;&#x4E3A;&#x4ED8;&#x6B3E;&#x8D27;&#x5E01;&#x65F6;&#xFF0C;&#x5B83;&#x5C06;&#x8FD4;&#x56DE;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x8D27;&#x5E01;&#xFF1A; USD, CNY, PHP, IDR, KRW, HKD</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">cashierUrl</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x6536;&#x94F6;&#x5458;&#x9875;&#x9762;&#x7684;URL&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">settleCurrency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x7ED3;&#x7B97;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4F4D;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>

{% tabs %}
{% tab title="cURL" %}
```text
curl -XPOST -H "Content-type: application/json" -d '{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "72a2c6ce8497adc8a03a78135618e666",
    "amount": "13",
    "currency": "PHP",
    "settleCurrency": "USD",
    "vendor": "alipay",
    "terminal": "ONLINE",
    "timeout": "30",
    "reference": "test202001011303",
    "ipnUrl": "http://zk-tys.yunkeguan.com/ttest/test",
    "callbackUrl": "http://zk-tys.yunkeguan.com/ttest/test2?status={status}",
    "description": "test+description",
    "note": "test note",
    "osType": "IOS",
    "goodsInfo": [
        {
            "goods_name": "name1",
            "quantity": "quantity1"
        }
    ]
}' 'https://mapi.yuansfer.com/online/v3/secure-pay'
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
    function securepay()
    {
        $url = 'https://mapi.yuansfer.com/online/v3/secure-pay';
        $token = '5cbfb079f15b150122261c8537086d77a';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'amount' => '0.01',
            'currency' => 'USD',
            'vendor' => 'alipay',
            'ipnUrl' => 'https://nengjtian.s1.natapp.cc/login/test',
            'callbackUrl' => 'https://nengjtian.s1.natapp.cc/login/test2?transactionNo={transactionNo}&status={status}&amount={amount}&time={time}&reference={reference}&note={note}',
            'terminal' => 'ONLINE',
            'reference' => 'test2018070101',
            'description' => 'test_description',
            'note' => 'test_note',
            'timeout' => '120'
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
    securepay();
?>
```
{% endtab %}

{% tab title="JAVA" %}
```java
public class SecurepayTest {
    public static final String TEST_URL = "https://mapi.yuansfer.yunkeguan.com";            //Testing domain
    public static final String PROD_URL = "https://mapi.yuansfer.com";                      //Production domain
    public static final String YUANSFER_TOKEN = "5c5fe30183be69fceff8174358d4b8ae";

    public static void main(String[] args) {
        YuansferVerifySignHelper helper = new YuansferVerifySignHelper();

        YuansferSecurepayDto dto = paramSetting();
        Map<String, Object> params = ReflectionUtils.convertBean2MapIgnoreNullVal(dto, new String[]{"serialVersionUID"});
        String verifySign = helper.getYuansferVerifySign(params, YUANSFER_TOKEN);
        params.put("verifySign", verifySign);

        String url = TEST_URL + "/online/v3/secure-pay";
        String ret = HttpClientUtils.post(url, null, params);
        System.out.println(ret);
    }

    public static YuansferSecurepayDto paramSetting() {
        YuansferSecurepayDto dto = new YuansferSecurepayDto();
        /**
         * merchantNo,storeNo is necessory, and they are provided by Yuansfer
         */
        dto.setMerchantNo("200043");                                                //The Merchant NO.
        dto.setStoreNo("300014");                                                   //The Store NO.

        /**
         * transaction infomation is necessory
         */
        dto.setAmount("0.01");                                                      //The amount, unit "division"
        dto.setCurrency("USD");                                                     //currency, "USD"
        dto.setIpnUrl("https://nengjtian.s1.natapp.cc/login/test");                 //Asynchronous callback address
        dto.setCallbackUrl("https://nengjtian.s1.natapp.cc/login/test2");           //Synchronous callback address
        dto.setReference("9091023122");                                             //order NO. of client's system
        dto.setTerminal("ONLINE");                                                  //"ONLINE" or "WAP"
        dto.setTimeout("120");                                                      //unit "minute"
        dto.setVendor("alipay");                                                    //“alipay","wechatpay" or "unionpay"

        /**
         * note，desription are optional
         */
        dto.setDescription("test-description");                                     //description
        dto.setNote("test-note");                                                   //note

        return dto;
    }
}
```
{% endtab %}

{% tab title="Go" %}
```
import (
        "fmt"
        "time"
        yuan "github.com/yuansfer/golang_sdk"
)

func securepay() {
    req := &yuan.Securepay{
        MerchantNo:  "200043", //customer The merchant NO.
        StoreNo:     "300014",
        Currency:    "USD",
        Amount:      "0.01",
        Vendor:      "wechatpay",
        Reference:   fmt.Sprintf("demo_%d", time.Now().Unix()), //sequence number of customer system
        IpnUrl:      "https://customer-ipn",        //internet accessible
        CallbackUrl: "https://customer-callback",   //internet accessible
        Description: "description",
        Note:        "note",
        Terminal:    "ONLINE",
        Timeout:     "120",
    }

    goods := "Yuansfer"
    quantity := "1"
    if quantity != "" && goods != "" {
        goodsInfos := []yuan.GoodsInfomation{
            yuan.GoodsInfomation{
                GoodsName: goods,
                Quantity:  quantity,
            },
        }
        _ = req.Format(goodsInfos)
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

