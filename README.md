# upyun-resty

UPYUN's open source software for OpenResty development.

![](http://iresty.b0.upaiyun.com/assets/upyun-resty.png_/fw/400)

# Table of Contents

* [What is UPYUN](#what-is-upyun)
* [What is OpenResty](#what-is-openresty)
* [Tech Talks](#tech-talks)
  * [201411 Beijing OSC](#201411-beijing-osc)
  * [201511 Beijing OpenResty Con](#201511-beijing-openresty-con)
  * [201608 Guangzhou UPYUN OpenTalk](#201608-guangzhou-upyun-opentalk)
  * [201612 Shenzhen OpenResty Con](#201612-shenzhen-openresty-con)
  * [201712 Hangzhou OpenResty Meetup](#201712-hangzhou-openresty-meetup)
  * [201811 Hangzhou OpenResty Con](#201811-hangzhou-openresty-con)
  * [201901 Shenzhen OpenResty x OpenTalk](#201901-shenzhen-openresty-x-opentalk)
  * [201903 Beijing OpenResty x OpenTalk](#201903-beijing-openresty-x-opentalk)
* [Projects](#projects)
  * [Middleware](#middleware)
    * [Project Slardar](#project-slardar)
  * [Nginx Modules](#nginx-modules)
    * [base64-nginx-module](#base64-nginx-module)
    * [zstd-nginx-module](#zstd-nginx-module)
  * [Libraries](#libraries)
    * [checkups](#checkups)
    * [httpipe](#httpipe)
    * [redis-ratelimit](#redis-ratelimit)
    * [sync](#sync)
    * [ctxdump](#ctxdump)
    * [consul](#consul)
    * [load](#load)
    * [requests](#requests)
    * [limit-rate](#limit-rate)
  * [Community Contributions](#community-contributions)
    * [slice filter and If-Range requests](#slice-filter-and-if-range-requests)
    * [autoindex module and request body](#autoindex-module-and-request-body)
    * [ngx.req.raw_header with single line break](#ngx.req.raw_header-with-single-line-break)
    * [ngx_lua and filter finalize problem](#ngx_lua-and-filter-finalize-problem)
    * [segmentation fault might occur when SSL renegotiation happens](#segmentation-fault-might-occur-when-SSL-renegotiation-happens)
* [Work at UPYUN](#work-at-upyun)

# What is UPYUN

- website: https://www.upyun.com
- github: https://github.com/upyun
- blog: http://io.upyun.com

# What is OpenResty

- website: https://openresty.org
- github: https://github.com/openresty

OpenResty is a full-fledged web platform by integrating the standard Nginx core, LuaJIT, many carefully written Lua libraries, lots of high quality 3rd-party Nginx modules, and most of their external dependencies. It is designed to help developers easily build scalable web applications, web services, and dynamic web gateways.

# Tech Talks

## 201411 Beijing OSC

- Using ngx_lua in UPYUN ([Slide](http://iresty.b0.upaiyun.com/slides/using-ngxlua-in-upyun.pdf) | [Github](https://github.com/timebug/using-ngxlua-in-upyun)) - @timebug

![](http://iresty.b0.upaiyun.com/assets/using-ngxlua-in-upyun.png_/fw/400)

## 201511 Beijing OpenResty Con

- Using ngx_lua in UPYUN 2 ([Slide](http://iresty.b0.upaiyun.com/slides/using-ngxlua-in-upyun-2.pdf) | [Github](https://github.com/timebug/using-ngxlua-in-upyun)) - @timebug

![](http://iresty.b0.upaiyun.com/assets/using-ngxlua-in-upyun-2.png_/fw/400)

## 201608 Guangzhou UPYUN OpenTalk

- 基于 ngx_lua 的动态服务路由方案 ([Slide](http://iresty.b0.upaiyun.com/slides/%E5%9F%BA%E4%BA%8Engx_lua%E7%9A%84%E5%8A%A8%E6%80%81%E6%9C%8D%E5%8A%A1%E8%B7%AF%E7%94%B1%E6%96%B9%E6%A1%88.pdf)) - @yejingx

![](http://iresty.b0.upaiyun.com/assets/%E5%9F%BA%E4%BA%8Engx_lua%E7%9A%84%E5%8A%A8%E6%80%81%E6%9C%8D%E5%8A%A1%E8%B7%AF%E7%94%B1%E6%96%B9%E6%A1%88.png_/fw/400)

## 201612 Shenzhen OpenResty Con

- OpenResty 在云处理服务器集群中的应用 ([Slide](http://iresty.b0.upaiyun.com/slides/OpenResty%E5%9C%A8%E4%BA%91%E5%A4%84%E7%90%86%E6%9C%8D%E5%8A%A1%E9%9B%86%E7%BE%A4%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8.pdf)) - @yejingx

![](http://iresty.b0.upaiyun.com/assets/OpenResty%E5%9C%A8%E4%BA%91%E5%A4%84%E7%90%86%E6%9C%8D%E5%8A%A1%E9%9B%86%E7%BE%A4%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8.png_/fw/400)

## 201712 Hangzhou OpenResty Meetup

- OpenResty TCP 服务代理和动态路由 ([Slide](https://iresty.b0.upaiyun.com/HangzhouMeetup201712/OpenResty%20TCP%20%E6%9C%8D%E5%8A%A1%E4%BB%A3%E7%90%86%E5%92%8C%E5%8A%A8%E6%80%81%E8%B7%AF%E7%94%B1.pdf)) - @huangnauh

![](https://iresty.b0.upaiyun.com/assets/OpenResty%20TCP%20%E6%9C%8D%E5%8A%A1%E4%BB%A3%E7%90%86%E5%92%8C%E5%8A%A8%E6%80%81%E8%B7%AF%E7%94%B1.png_/fw/400)

- OpenResty 项目性能优化实践 ([Slide](https://iresty.b0.upaiyun.com/HangzhouMeetup201712/OpenResty%20%E9%A1%B9%E7%9B%AE%E6%80%A7%E8%83%BD%E4%BC%98%E5%8C%96%E5%AE%9E%E8%B7%B5.pdf)) - @tokers

![](https://iresty.b0.upaiyun.com/assets/OpenResty%20%E9%A1%B9%E7%9B%AE%E6%80%A7%E8%83%BD%E4%BC%98%E5%8C%96%E5%AE%9E%E8%B7%B5.png_/fw/400)

## 201811 Hangzhou OpenResty Con

- 又拍云 OpenResty/Nginx 服务优化实践 ([Slide](https://github.com/tokers/tech-slides/blob/master/%E5%8F%88%E6%8B%8D%E4%BA%91%E6%9C%8D%E5%8A%A1%E4%BC%98%E5%8C%96%E5%AE%9E%E8%B7%B5%E2%80%94%E2%80%94%E5%BC%A0%E8%B6%85.pdf)) - @tokers

![](https://iresty.b0.upaiyun.com/assets/openresty-2018-upyun-alex.png_/fw/400)

## 201901 Shenzhen OpenResty x OpenTalk

- OpenResty 动态流控的几种姿势 ([Slide](https://iresty.b0.upaiyun.com/slides/OpenResty%20%E5%8A%A8%E6%80%81%E6%B5%81%E6%8E%A7%E7%9A%84%E5%87%A0%E7%A7%8D%E5%A7%BF%E5%8A%BF.pdf)) - @timebug

![](https://iresty.b0.upaiyun.com/assets/OpenResty%20%E5%8A%A8%E6%80%81%E6%B5%81%E6%8E%A7%E7%9A%84%E5%87%A0%E7%A7%8D%E5%A7%BF%E5%8A%BF.jpeg_/fw/400)

## 201903 Beijing OpenResty x OpenTalk

- OpenResty 在又拍云容器平台中的应用 ([Slide](https://iresty.b0.upaiyun.com/slides/OpenResty%E5%9C%A8%E5%8F%88%E6%8B%8D%E4%BA%91%E5%AE%B9%E5%99%A8%E5%B9%B3%E5%8F%B0%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8.pdf)) - @yejingx

![](https://iresty.b0.upaiyun.com/assets/OpenResty%E5%9C%A8%E5%8F%88%E6%8B%8D%E4%BA%91%E5%AE%B9%E5%99%A8%E5%B9%B3%E5%8F%B0%E4%B8%AD%E7%9A%84%E5%BA%94%E7%94%A8.jpeg_/fw/400)

# Projects

## Middleware

### Project Slardar

- github: https://github.com/upyun/slardar

Slardar is a HTTP load balancer based on Nginx and lua-nginx-module, by which you can update your upstream list and run lua scripts without reloading Nginx.

## Nginx Modules

### base64-nginx-module

- github: https://github.com/timebug/base64-nginx-module

This module allows for on-the-fly base64 encode. As same as the standard ngx\_http\_gzip_module.

### zstd-nginx-module

- github: https://github.com/tokers/zstd-nginx-module

Nginx module for the [Zstandard compression](https://facebook.github.io/zstd/).

## Libraries

### checkups

- github: https://github.com/upyun/lua-resty-checkups

Manage Nginx upstreams in pure ngx_lua.

* Periodically heartbeat to upstream servers
* Proactive and passive health check
* Dynamic upstream update
* Balance by weighted round-robin or consistent-hash
* Synchronize with Nginx upstream blocks
* Try clusters by levels or by keys

### httpipe

- github: https://github.com/timebug/lua-resty-httpipe

Lua HTTP client cosocket driver for OpenResty / ngx_lua, interfaces are more flexible.

* HTTP 1.0/1.1 and HTTPS
* Flexible interface design
* Streaming reader and uploads
* Chunked-encoding request / response body
* Sets the timeout for read and send operations
* Limit the maximum response body size
* Keepalive

### redis-ratelimit

- github: https://github.com/timebug/lua-resty-redis-ratelimit

This lua library is a request processing rate limit module for ngx_lua. It is used to limit the request processing rate per a defined key between multiple NGINX instances. The limitation is done using the "leaky bucket" method.

### sync

- github: https://github.com/upyun/lua-resty-sync

This lua-resty library help you to synchronize data(from redis, mysql, memcached and so on) based on the version changes.

It will check the freshness by comparing the version cached by itself(stored in shared memory) and the one from your external suits, data will be updated when the cached one is stale or for the first time.

### ctxdump

- github: https://github.com/tokers/lua-resty-ctxdump

`ngx.ctx` is a magic table provided by ngx_lua, it can be used to store per-request Lua context data, however the lifetime is limited to the current location.

See this [issue](https://github.com/openresty/lua-nginx-module/issues/1057) for the details.

This lua-resty library can help you to bypass this limitation, i.e. it stashes and applies the old `ngx.ctx` for avoiding being destoried after Nginx internal redirect happens.

### consul

- github: https://github.com/huangnauh/lua-resty-consul

This Lua library can help OpenResty/ngx_lua users to load config from consul.

### load

- github: https://github.com/huangnauh/lua-resty-load

This Lua library can help OpenResty/ngx_lua users to dynamically load lua files/scripts.

### requests

- https://github.com/tokers/lua-resty-requests

Yet Another HTTP library for OpenResty.

### limit-rate

- https://github.com/upyun/lua-resty-limit-rate

Lua module for limiting request rate for OpenResty/ngx_lua, using the "token bucket" method.

## Community Contributions

### slice filter and If-Range requests

The semantic of If-Range isn't implemented correctly when using nginx's slice module.

See [here](https://trac.nginx.org/nginx/ticket/1357) for the details.

### autoindex module and request body

The autoindex module doesn't discard the request body explicitly,  
hence request body will be treated as a pipelined request, and most of time
another unexpected response will be sent to client.

See [here](https://trac.nginx.org/nginx/ticket/1439) for the details.

### ngx.req.raw_header with single line break

When the header delimiter is `\n`(rather than `\r\n`),  
`ngx.req.raw_header` cannot get the complete protocol headers in some case.

See [here](https://github.com/openresty/lua-nginx-module/issues/1200) for the details.

### ngx_lua and filter finalize problem

some ngx_lua's APIs(like `ngx.flush`) don't handle the nginx filter finalize correctly,  
thus the Lua VM may raise some exceptions.

See [here](https://github.com/openresty/lua-nginx-module/issues/1131) for the details.

### segmentation fault might occur when SSL renegotiation happens

When the SSL/TLS handshake reuses a existing session and the connection upgrades to HTTP/2,
segmentation fault might occur when SSL/TLS renegotiation happens.

This problem only happens under the specific Nginx and OpenSSL combinations.

See [here](https://github.com/openresty/lua-nginx-module/issues/1354) for the details.

# Work at UPYUN

- See more: http://io.upyun.com/join-our-team/
