# JAVA SDK

### 需求

* JAVA &gt;= 1.6

### 安装

```text
<dependency>
    <groupId>com.yuansfer</groupId>
    <artifactId>yuansfer-payment</artifactId>
    <version>2.0.0</version>
</dependency>
```

### 范例

#### 1. 初始化

```java
YuanpayConfig config = new YuanpayConfig();
config.setEnv(EnviromentEnums.SANDBOX.getValue())
      .setMerchantNo("200043")
      .setStoreNo("300014")
      .setToken("5cbfb079f15b150122261c8537086d77a");

YuanpayClient client = new YuanpayV200Client(config);                
```

#### 2. 在线API

```java
JSONArray goods = new JSONArray();
JSONObject item = new JSONObject();
item.put("goods_name","name1");
item.put("quantity", "1");
goods.add(item);


OnlineSecurepayRequest request = new OnlineSecurepayRequest();
request.setAmount("0.01")
        .setCurrency("USD")
        .setVendor("alipay")
        .setTerminal("ONLINE")
        .setReference(System.nanoTime()+"")
        .setIpnUrl("http://zk-tys.yunkeguan.com/ttest/test")
        .setCallbackUrl("http://zk-tys.yunkeguan.com/ttest/test2?status={status}")
        .setDescription("testDescription")
        .setNote("testNote")
        .setGoodsInfo(goods.toString());

OnlineSecurepayResponse response = client.execute(request);
System.out.println(JSONObject.fromObject(response));        
```

#### 3. 线下API

```java
InstoreCreateTranQrcodeRequest request = new InstoreCreateTranQrcodeRequest();
        
request.setAmount("0.01")
        .setCurrency("USD")
        .setIpnUrl("http://zk-tys.yunkeguan.com/ttest/test")
        .setNeedQrcode("true")
        .setReference(System.nanoTime()+"")
        .setTimeout(120)
        .setVendor("alipay");

InstoreCreateTranQrcodeResponse response = client.execute(request);
System.out.println(JSONObject.fromObject(response));
```

#### 4. 手机API

```java
MobilePrepayRequest request = new MobilePrepayRequest();
request.setAmount("0.01")
        .setCurrency("USD")
        .setDescription("testDescription")
        .setIpnUrl("http://zk-tys.yunkeguan.com/ttest/test")
        .setNote("testNote")
        .setReference(System.nanoTime()+"")
        .setTerminal("APP")
        .setVendor("alipay");

MobilePrepayResponse response = client.execute(request);
System.out.println(JSONObject.fromObject(response));
```

#### 5. 数据API

```java
RefundRequest request = new RefundRequest();
        
request.setAmount("0.01")
        .setRefundReference("refund" + System.nanoTime())
        .setTransactionNo("297553630266977466");
        
RefundResponse response = client.execute(request);
System.out.println(JSONObject.fromObject(response));
```



