# 注解

### 交易对象

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
      <td style="text-align:left">originalTransactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x539F;&#x59CB;&#x4EA4;&#x6613;&#x7684;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">merchantNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">storeNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5E97;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">storeAdminNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5E97;&#x7BA1;&#x7406;&#x5458;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;(&#x7F8E;&#x5143;)&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">refundAmount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x9000;&#x6B3E;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">voidAmount</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x65E0;&#x6548;&#x6216;&#x53D6;&#x6D88;&#x7684;&#x91D1;&#x989D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">transactionType</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x4EA4;&#x6613;&#x7C7B;&#x578B;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C;&#x4ED8;&#x6B3E;&#x201D;&#xFF0C;&#x201C;&#x9000;&#x6B3E;&#x201D;&#xFF0C;&#x201C;&#x65E0;&#x6548;&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">transactionStatus</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x72B6;&#x6001;</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x6807;&#x8BC6;&#x8D27;&#x5E01;&#x7684;&#x4E09;&#x4E2A;&#x5B57;&#x7B26;&#x8D27;&#x5E01;&#x4EE3;&#x7801;&#x3002;
          &#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; USD&#x201D; &#x201C;
          CNY&#x201D; &#x201C; PHP&#x201D;</p>
        <p>&#x201C; IDR&#x201D; &#x201C; KRW&#x201D; &#x201C; HKD&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">createTime</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>The date and time when the authorization was created.</p>
        <p>Format : <b>&quot;yyyy-MM-dd HH:mm:ss&quot;</b>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">paymentTime</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x521B;&#x5EFA;&#x6388;&#x6743;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; yyyy-MM-dd HH&#xFF1A;mm&#xFF1A;ss&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">exchangeRate</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x7F8E;&#x5143;&#x548C;&#x4EBA;&#x6C11;&#x5E01;&#x4E4B;&#x95F4;&#x7684;&#x6C47;&#x7387;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">vendor</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x4ED8;&#x6B3E;&#x65B9;&#x5F0F;&#x3002;</p>
        <p>&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#xFF1A;&#x201C; alipay&#x201D;&#xFF0C;&#x201C;
          wechatpay&#x201D;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>

### 响应返回代码

Yuansfer API在ret\_code参数中返回以下代码：

| **返回代码** | **意义** |
| :--- | :--- |
| 000000 | 系统错误 |
| 000010 | API版本错误 |
| 000020 | 参数为空错误 |
| 000021 | 参数编号无相关信息 |
| 000022 | 参数不匹配 |
| 000023 | 参数值错误 |
| 000030 | 没有权限/访问被拒绝 |
| 000040 | 交易状态错误 |
| 000080 | 供应商系统错误 |
| 000100 | 成功 |

### 交易状态

| **状态** | **意义** |
| :--- | :--- |
| init | 创建了新交易，但未发送到付款渠道。 |
| dealing | 处理付款。 |
| success            | 交易已成功处理。 |
| failed | 交易失败。 |
| pending | 等待付款确认。 |
| closed | 设置了付款渠道，但是客户没有继续完成付款操作，所以在一段时间后自动关闭。 |

### 付款交易状态

| **状态** | **说明** |
| :--- | :--- |
| success | 资金已计入收款人的帐户 |
| pending | 您的付款要求已收到并将被处理 |
| failed | 该付款请求失败，因此未从发送者的帐户中扣除资金 |
| returned | 收款人尚未领取此款项，因此资金已退还到您的帐户中 |
| refunded | 该付款请求已退还 |
| reversed | 该付款请求已撤消 |
| unclaimed | 此付款的接收者没有PayPal帐户。已把注册PayPal帐户的链接发送给收件人 |
| onhold | 此付款请求正在审核中，已暂停 |
| blocked | 此付款请求已被阻止 |

### 即时付款通知

商家在其网站上创建IPN侦听器页面，然后在请求正文中指定侦听器页面的URL。然后Yuansfer API将会把所有与交易相关的事件的通知发送到该URL。当客户为商品或者服务付款时，API会将包含付款信息\(IPN消息\)的安全的表单POST发送到URL。 IPN侦听器使用商家进程检测并处理IPN消息。 IPN侦听器页面包含一个自定义脚本或程序，该脚本或程序等待后端消息，验证成功状态然后将它们传递给各种后端应用程序进行处理。 IPN侦听器必须向Yuansfer响应“success”字符串（不带引号），否则Yuansfer将发送异步付款通知8次。 IPN与您网站上的操作不同步。 网络连接并不总是完全可靠，因此IPN消息可能会丢失或延迟。 IPN服务会自动重新发送消息，直到侦听器确认为止。该服务在2小时内最多可重新发送消息8次。

### 回调参数

#### 自动付款交易通知

自动付款后会发送成功通知。 此异步回调通知将包含诸如autoDebitNo，autoReference，customerBelognsTo，time，note和verifySign的参数。

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
      <td style="text-align:left">autoDebitNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x81EA;&#x52A8;&#x6263;&#x6B3E;&#x7684;&#x552F;&#x4E00;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">autoReference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x6237;&#x7CFB;&#x7EDF;&#x4E2D;&#x81EA;&#x52A8;&#x6263;&#x6B3E;&#x7684;&#x552F;&#x4E00;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">vendor</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4ED8;&#x6B3E;&#x6E20;&#x9053;&#xFF0C;&#x53EF;&#x80FD;&#x7684;&#x503C;&#x4E3A;&#x201C;
        gcash&#x201D;&#xFF0C;&#x201C; kakaopay&#x201D;&#xFF0C;&#x201C; alipay&#x201D;&#xFF0C;&#x201C;
        alipay_hk&#x201D;&#xFF0C;&#x201C; dana&#x201D;&#xFF0C;&#x201C; truemoney&#x201D;&#xFF0C;&#x201C;
        tng&#x201D;&#xFF0C;&#x201C; easypaisa&#x201D;&#xFF0C;&#x201C; bkash&#x201D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x521B;&#x5EFA;&#x6388;&#x6743;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; YYYYMMDDHHMMSS&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">note</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4ED8;&#x6B3E;&#x6CE8;&#x91CA;&#x3002;</td>
    </tr>
  </tbody>
</table>

#### 付款交易通知

当商家的系统收到Yuansfer系统的回调时，建议商家的系统通过使用verifySign验证回调信息中的参数，以确保数据未被篡改。

Yuansfer在回调\(包括IPN\)中将返回以下参数。

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
      <td style="text-align:left">transactionNo</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Yuansfer&#x7CFB;&#x7EDF;&#x4E2D;&#x7684;&#x4EA4;&#x6613;ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x72B6;&#x6001;</td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4EA4;&#x6613;&#x91D1;&#x989D;(&#x7F8E;&#x5143;)&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>USD&#xFF0C;CNY&#xFF0C;PHP&#xFF0C;IDR&#xFF0C;KRW&#xFF0C;HKD&#x7684;&#x4EA4;&#x6613;&#x5355;&#x4F4D;&#x3002;</p>
        <p>&#x8FD9;&#x662F;&#x5217;&#x51FA;&#x4EF7;&#x683C;&#x7684;&#x8D27;&#x5E01;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">settleCurrency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x8FD9;&#x662F;&#x5C06;&#x5411;&#x5546;&#x5BB6;&#x4ED8;&#x6B3E;&#x7684;&#x8D27;&#x5E01;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>&#x521B;&#x5EFA;&#x6388;&#x6743;&#x7684;&#x65E5;&#x671F;&#x548C;&#x65F6;&#x95F4;</p>
        <p>&#x683C;&#x5F0F;&#xFF1A;&#x201C; YYYYMMDDHHMMSS&#x201D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">reference</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x5546;&#x5BB6;&#x7CFB;&#x7EDF;&#x4E2D;&#x4EA4;&#x6613;&#x7684;&#x53D1;&#x7968;&#x7F16;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">vendorId</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4F9B;&#x5E94;&#x5546;&#x4EA4;&#x6613;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">note</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x4ED8;&#x6B3E;&#x6CE8;&#x91CA;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">verifySign</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&#x53C2;&#x6570;&#x7B7E;&#x540D;&#x3002;</td>
    </tr>
  </tbody>
</table>

### Yuansfer时区

Yuansfer的工作时区为UTC +8。

