# 预付

{% api-method method="post" host="https://mapi.yuansfer.com/micropay/v3" path="/prepay" %}
{% api-method-summary %}
prepay
{% endapi-method-summary %}

{% api-method-description %}
 该API为In-APP和/或WeChat Mini程序解决方案提供移动支付。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="merchantNo" type="string" required=true %}
商户编号
{% endapi-method-parameter %}

{% api-method-parameter name="storeNo" type="string" required=true %}
店铺编号
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
价格金额。
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="number" required=true %}
价格货币，可能的值：USD，CNY
{% endapi-method-parameter %}

{% api-method-parameter name="settleCurrency" type="string" required=true %}
结算货币\(用于除USD之外的所有货币\)。
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=true %}
可能的值为：“ alipay”，“wechatpay”，“ paypal”，“ venmo”，“creditcard”，“ googlepay”，“ applepay”。 注意：当vendor为“alipay“时，“ terminal”参数必须为APP。
{% endapi-method-parameter %}

{% api-method-parameter name="ipnUrl" type="string" required=true %}
即时付款通知处理程序URL。 IPN URL必须是安全的。
{% endapi-method-parameter %}

{% api-method-parameter name="openid" type="string" required=false %}
来自微信的openid，只有微信小程序才需要。
{% endapi-method-parameter %}

{% api-method-parameter name="reference" type="string" required=true %}
商家系统中交易的发票编号。
{% endapi-method-parameter %}

{% api-method-parameter name="terminal" type="string" required=true %}
可能的值为：“ MINIPROGRAM”，“ APP”。
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
显示在发票上面的交易说明。
{% endapi-method-parameter %}

{% api-method-parameter name="note" type="string" required=false %}
交易注释。
{% endapi-method-parameter %}

{% api-method-parameter name="timeout" type="integer" required=false %}
超时（以分钟为单位）。   
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
        "nonceStr": "QyGptpsnpbydUzdVvkJy5fysWHYO48uF",
        "package": "prepay_id=wx131236528509476a97469b574a5ea30000",
        "paySign": "F2BB1584CB384DC008C665BD19FBB736BF24F1727CEB01159F9BEFA1162A61B7",
        "signType": "HMAC-SHA256",
        "timeStamp": "1602563859"
    },
    "ret_msg": " prepay success",
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
      <td style="text-align:left">result</td>
      <td style="text-align:left">object</td>
      <td style="text-align:left">
        <p>&#x5FAE;&#x4FE1;&#x5C0F;&#x7A0B;&#x5E8F;&#x7ED3;&#x679C;&#x5BF9;&#x8C61;&#x3002;</p>
        <p>&#x5FAE;&#x4FE1;&#x5E94;&#x7528;&#x7ED3;&#x679C;&#x5BF9;&#x8C61;&#x3002;</p>
        <p>&#x652F;&#x4ED8;&#x5B9D;&#x5E94;&#x7528;&#x7ED3;&#x679C;&#x5BF9;&#x8C61;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">ret_msg</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x54CD;&#x5E94;&#x8FD4;&#x56DE;&#x6D88;&#x606F;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">ret_code</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x54CD;&#x5E94;&#x8FD4;&#x56DE;&#x7801;&#x3002; &#x6709;&#x5173;&#x66F4;&#x591A;&#x8BE6;&#x7EC6;&#x4FE1;&#x606F;&#xFF0C;&#x8BF7;&#x53C2;&#x89C1;
        <a
        href="../../../zhu-jie.md#xiang-ying-fan-hui-dai-ma">&#x6B64;&#x5904;</a>&#x3002;</td>
    </tr>
  </tbody>
</table>

#### 微信小程序结果对象

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| timeStamp | string | 时间戳。 |
| nonceStr | string | 随机字符串。 |
| package | string | prepay\_id的信息。 |
| signType | string | 签名类型。 |
| paySign | string | 签名。 |

#### 微信应用结果对象

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| appid | string | 应用ID。 |
| noncestr | string | 随机字符串。 |
| package | string | 数值为'Sign=WXPay'. |
| partnerid | string | 合作伙伴的信息。 |
| prepayid | string | prepay\_id的信息。 |
| sign | string | 签名。 |
| timestamp | string | 时间戳。 |

#### 支付宝应用结果对象

| **参数** | **类型** | **说明** |
| :--- | :--- | :--- |
| payInfo | string | 付款信息。 |

{% tabs %}
{% tab title="cURL" %}
```text
curl -XPOST -H "Content-type: application/json" -d '{
    "merchantNo": "200043",
    "storeNo": "300014",
    "verifySign": "09f722178f6cf2e71c9dfdd664e8663b",
    "amount": "10",
    "currency": "CNY",
    "settleCurrency": "USD",
    "ipnUrl": "http://zk-tys.yunkeguan.com/login/test",
    "reference": "test2020101302",
    "description": "司机支付会员费用",
    "vendor": "wechatpay",
    "terminal": "MINIPROGRAM",
    "openid": "ocBgh5fnabrf-pxPgCWXlq2mOvG8"
}' 'https://mapi.yuansfer.com/micropay/v3/prepay'
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
    function microprepay()
    {
        $url = 'https://mapi.yuansfer.com/micropay/v2/prepay';
        $token = '5cbfb079f15b150122261c8537086d77a';
        $params = [
            'merchantNo' => '200043',
            'storeNo' => '300014',
            'amount' => '0.01',
            'currency' => 'USD',
            'vendor' => 'wechatpay',
            'ipnUrl' => 'https://nengjtian.s1.natapp.cc/login/test',
            'reference' => 'test2018070101',
            'description' => 'test_description',
            'note' => 'test_note',
            'openid' => '***'
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
    microprepay();
?>
```
{% endtab %}

{% tab title="Java" %}
```java
public class MicropayTest {

    public static final String TEST_URL = "https://mapi.yuansfer.yunkeguan.com";            //testing domain
    public static final String PROD_URL = "https://mapi.yuansfer.com";                      //production domain
    public static final String YUANSFER_TOKEN = "5c5fe30183be69fceff8174358d4b8ae";


    public static void main(String[] args) {
        YuansferVerifySignHelper helper = new YuansferVerifySignHelper();

        AppMircopayDto dto = paramSetting();
        Map<String, Object> params = ReflectionUtils.convertBean2MapIgnoreNullVal(dto, new String[]{"serialVersionUID"});
        String verifySign = helper.getYuansferVerifySign(params, YUANSFER_TOKEN);
        params.put("verifySign", verifySign);

        String url = TEST_URL + "/micropay/v2/prepay";
        String ret = HttpClientUtils.post(url, null, params);
        System.out.println(ret);
    }

    public static AppMircopayDto paramSetting() {
        AppMircopayDto dto = new AppMircopayDto();
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
        dto.setReference("9091023122");                                             //order NO. of client's system
        dto.setOpenid("***");                                                       //wechat openid
        dto.setVendor("wechatpay");                                                 //"wechatpay"

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
```go
func mciropay(t *table) {
    req := yuan.Securepay{
        MerchantNo:  "200043", //customer The merchant NO.
        StoreNo:     "300014",
        Currency:    "USD",
        Amount:      "0.01",
        Vendor:      "wechatpay",
        Reference:   fmt.Sprintf("demo_%d", time.Now().Unix()), //sequence number of customer system
        IpnUrl:      "https://customer-ipn",        //internet accessible
        Description: "description",
        Note:        "note",
        Openid:      "***",
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

