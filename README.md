# 安装

在composer.json中添加
~~~
"thefunpower/rpc_php": "dev-main" 
~~~

## curl超时
~~~
yar.timeout = 6000
~~~

## RPC

服务端
~~~
class ServerGetUser{
    public function getInfo($name = 'abc'){
        return ['welcome'=>$name,'token'=>rpc_token()];
    }
}
rpc_server("ServerGetUser");
~~~

客户端
~~~
$client = rpc_client("http://127.0.0.1:5000/rpc.php");
$info = $client->getInfo("test");
print_r($info);
~~~ 
 



### 开源协议 

[Apache License 2.0](LICENSE)