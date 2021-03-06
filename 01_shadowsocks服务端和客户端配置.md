# shadowsocks 
```
Shadowsocks 的原理：它发出的 TCP 包，没有明显包特征，可以通过GFW 审查。
```
官网：
https://shadowsocks.org/en/download/clients.html

* windows shadowsocks 服务端下载:
```
https://github.com/shadowsocks/libQtShadowsocks/releases

下载：
shadowsocks-libqss-v2.0.2-win64.7z
```

* windows客户端下载：
```
https://github.com/shadowsocks/shadowsocks-windows/releases

下载 Shadowsocks-4.4.0.185.zip
```

### shadowsocks 服务端配置
```json
{
    "server":"127.0.0.1",
    "server_port":1110,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"xxxxx",
    "timeout":600,
    "method":"aes-256-gcm",
    "auth": false
}

相关参数文档：
{
    "server":"localhost",        //配置服务端地址，不需要修改
    "server_port":623,           //服务端端口，可以根据需要修改，建议改成大点的不会被占用的端口
    "local_address":"127.0.0.1", //本地地址，不需要修改
    "local_port":1080,           //本地端口，可以根据需要修改
    "password":"Orange",         //密码
    "timeout":600,               //连接超时时间
    "method":"rc4-md5",          //加密方式
    "http_proxy": false,         //代理
    "auth": false                //需要验
}
```

windows 运行shadowsocks 服务端
在终端运行：
```
shadowsocks-libqss.exe -c config.json -S
```

### ubuntu shadowsocks 客户端配置实现科学上网
<br>
配置完成记得开启全局代理，配置参考：
https://shadowsockshelp.github.io/Shadowsocks/linux.html
或则 参考下面Windows shadowsocks配置
···
安装客户端
右键单击 “Shadowsocks-Qt5-x.x.x-x86_64.AppImage” > 选择 “Properties” > 单击 “Permissions” > 在”Allow excuting file as program” 上打勾。

配置：
执行下列操作：
双击Shadowsocks-Qt5-x.x.x-x86_64.AppImage > “Connection” > “Add” > “Manually”。

ubuntu 设置全局代理：
http: 127.0.0.1 1080
https: 127.0.0.1 1080
···

## windows客户端配置实现科学上网：
配置比较简单,gui 操作，把服务器ip，和端口，加密方式填入，点击全局代理即可,此时发送的请求将经过公网转发，最后到达window处理。
```
https://github.com/shadowsocks/shadowsocks-windows/releases

下载 Shadowsocks-4.4.0.185.zip
```

## 参考文档：
<br>
```
1.frp + shadowsocks强强组合，内网穿透访问局域网其他主机
https://www.codeleading.com/article/8495900005/
```