# PHP SDK

### 需求

* PHP &gt;=5.3
* CURL拓展程序

### 安装

#### 使用Composer\(推荐\)

1.安装composer:

```bash
$ curl -sS https://getcomposer.org/installer | php
```

2.运行composer指令来安装最新版的的SDK

```bash
php composer.phar require yuansfer/yuansfer-php-sdk
```

3.添加Composer的autoloader到您的PHP脚本\(假设它和Composer安装在相同的目录\)

```bash
require('vendor/autoload.php');
```

#### PHAR 打包依赖项

{% hint style="warning" %}
不推荐使用！使用Composer来管理PHP是一种更现代化的方式。
{% endhint %}

1.下载 [PHAR file](https://github.com/yuansfer/yuansfer-php-sdk/releases/tag/v1.1.0)

2.添加文件:

```bash
require('path-to-sdk/yuansfer-php-sdk.phar');
```

请注意打包的依赖项可能会影响项目的其他依赖项。

### 范例

#### 1. 初始化

```php
use Yuansfer\Yuansfer;

$config = array(
    Yuansfer::MERCHANT_NO => 'The merchant NO.',
    Yuansfer::STORE_NO => 'The store NO.',
    Yuansfer::API_TOKEN => 'Yuansfer API token',
    Yuansfer::TEST_API_TOKEN => 'Yuansfer API token for test mode',
);

$yuansfer = new Yuansfer($config);
```

#### 2. 创建 API

```php
$api = $yuansfer->createSecurePay();
```

#### 3. 设置API参数

```php
$api
    ->setAmount(9.9) //The amount of the transaction.
    ->setCurrency('USD') // The currency, USD, CAD supported yet.
    ->setVendor('alipay') // The payment channel, alipay, wechatpay, unionpay, enterprisepay are supported yet.
    ->setTerminal('ONLINE') // ONLINE, WAP
    ->setReference('44444') //The unque ID of client's system.
    ->setIpnUrl('http://domain/example/callback_secure_pay_ipn.php') // The asynchronous callback method.
    ->setCallbackUrl('http://domain/example/callback_secure_pay.php'); // The Synchronous callback method.
```

#### 4.1 发送

```php
$response = $api->send();
```

#### 4.2 使用测试模式

```php
$yuansfer->setTestMode();
$response = $api->send();
```

#### 5. API返回JSON, 已经解码为数组

```php
if ($response['ret_code'] === '000100') {
	header('Location: ' . $response['result']['cashierUrl']);
}
```

#### 6. 发送时的异常

```php
try {
    $response = $api->send();
} catch (\Yuansfer\Exception\YuansferException $e) {
    // required param is empty
    if ($e instanceof \Yuansfer\Exception\RequiredEmptyException) {
        $message = 'The param: ' . $e->getParam() . ' is empty, in API: ' . $e->getApi();
    }

    // http connect error
    if ($e instanceof \Yuansfer\Exception\HttpClientException) {
        $message = $e->getMessage();
    }

    // http response status code < 200 or >= 300, 301 and 302 will auto redirect
    if ($e instanceof \Yuansfer\Exception\HttpErrorException) {
        /** @var \Httpful\Response http response */
        $response = $e->getResponse();
    }
}
```



