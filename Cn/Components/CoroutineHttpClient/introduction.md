<head>
     <title>EasySwoole 协程Http客户端|swoole 协程Http客户端|swoole 协程Http|php 协程客户端</title>
     <meta name="keywords" content="EasySwoole 协程Http客户端|swoole 协程Http客户端|swoole 协程Http|php 协程客户端"/>
     <meta name="description" content="php用swoole里面的协程客户端，实现对http请求封装的基本库"/>
</head>
---<head>---

## EasySwoole 协程HTTPClient组件
协程httpClient组件,基于swoole [异步http client客户端](https://wiki.swoole.com/wiki/page/p-http_client.html)实现,可在协程内发起http请求不被阻塞,可用于下载文件,请求api,爬虫等一系列需求当中

## 安装

```bash
composer require easyswoole/http-client
```

## 单次请求
```php
<?php
$url = 'http://docker.local.com/test.php/?get1=get1';
$test = new \EasySwoole\HttpClient\HttpClient($url);
//$test->post();

$test->addCookie('c1','c1')->addCookie('c2','c2');

$test->setHeader('myHeader','myHeader');

$ret = $test->postJSON(json_encode(['json'=>1]));

var_dump($ret->getBody());
```

## 并发请求

关于Http Client的并发请求章节，我们推荐用户使用 EasySwoole组件中提供的[Csp封装](../Component/csp.md)。
