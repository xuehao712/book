# API参数签名

签名API参数可让您通过使用MD5加密和经过身份验证的散列算法来保护Yuansfer API的调用。

为了构建API调用的参数，您将需要从Yuansfer的概要面板来获取您的API令牌。API参数必须使用MD5加密进行签名。

### 构建API参数签名

您需要以下几个步骤来签名API参数:

1. 根据参数名称的字母顺序对参数进行排序。
2. 使用'='和'＆'字符连接参数名称和数值。
3. 将MD5加密过的API令牌添加到带有“＆”前缀的参数尾端。
4. 把第三步骤的结果再次进行MD5加密。

### 范例

**请参考以下参数**

* amount = '1.00'
* storeNo = '300014'
* currency = 'USD'
* merchantNo = '200043'
* callbackUrl = 'https://wx.yuansfer.yunkeguan.com/wx'
* terminal = 'ONLINE'
* ipnUrl = 'https://wx.yuansfer.yunkeguan.com/wx'
* reference = 'seq\_1525922323'
* vendor = 'alipay'
* goodsInfo = '\[{"goods\_name":"Yuansfer","quantity":"1"}\]'
* timeout = '120'

**1.对参数进行排序**

* amount = '1.00'
* callbackUrl = 'https://wx.yuansfer.yunkeguan.com/wx'
* currency = 'USD'
* goodsInfo = '\[{"goods\_name":"Yuansfer","quantity":"1"}\]'
* ipnUrl = 'https://wx.yuansfer.yunkeguan.com/wx'
* merchantNo = '200043'
* reference = 'seq\_1525922323'
* storeNo = '300014'
* terminal = 'ONLINE'
* timeout = '120'
* vendor = 'alipay'

**2.使用'='和'＆'字符连接参数名称和数值**

> amount=1.00&callbackUrl=https://wx.yuansfer.yunkeguan.com/wx& currency=USD&goodsInfo=\[{"goods\_name":"Yuansfer","quantity":"1"}\]&ipnUrl=https://wx.yuansfer.yunkeguan.com/wx&merchantNo=200043&reference=seq\_1525922323&storeNo=300014&terminal=ONLINE&timeout=120&vendor=alipay

**3.将MD5加密过的API令牌添加到带有“＆”前缀的参数尾端**

假设API令牌为5cbfb079f15b150122261c8537086d77a时，MD5加密后的哈希值为186abea4b8610d7ff03768255588597a。

所以结果字符串是:

> amount=1.00&callbackUrl=https://wx.yuansfer.yunkeguan.com/wx& currency=USD&goodsInfo=\[{"goods\_name":"Yuansfer","quantity":"1"}\]&ipnUrl=https://wx.yuansfer.yunkeguan.com/wx&merchantNo=200043&reference=seq\_1525922323&storeNo=300014&terminal=ONLINE&timeout=120&vendor=alipay&186abea4b8610d7ff03768255588597a

**4.将步骤3的结果字符串再次进行MD5加密**

MD5加密后的哈希值为b6bfd66531ae7c9499115c7480a2c8aa。

