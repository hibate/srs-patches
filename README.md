# SRS 补丁

## 补丁说明

* srs-with-http-server-crossdomain

对应 SRS 版本: 2.0.243
说明: 添加 http 跨域配置，支持 HLS、HTTP-FLV 跨域

## 打补丁

```shell
$ cd srs-2.0-r2
$ patch -p1 < ./patch-to-srs-with-http-server-crossdomain.patch
```

## 配置

### HTTP 跨域

在 `http_server` 中加入 `crossdomain` 即可，默认为 `off`。

```
http_server {
    enabled         on;
    listen          8080;
    dir             ./objs/nginx/html;
    # whether enable crossdomain request.
    # default: off
    crossdomain     on;
}
```
