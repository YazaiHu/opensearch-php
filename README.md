# Opensearch PHP
PHP Client for Aliyun Opensearch

## Work with Swoole

```php
go(function() {

    $coClient = new OpenSearch\Client\OpenSearchClient('some-key', 'some-secret',
            'http://opensearch-cn-hangzhou.aliyuncs.com');
    $coClient->setHttpHandler(new OpenSearch\Client\Handler\SwooleHttpHandler()); // 更换请求处理器

    $resultObj = $coClient->get('/apps');
    $resultJSON = $resultObj->result;
    $result = json_decode($resultJSON, true);
    fprintf(STDOUT, "name=%s" . PHP_EOL, $result['result']['name']);

});
```