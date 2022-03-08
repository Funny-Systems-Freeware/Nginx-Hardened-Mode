# Nginx-Hardened-Mode v1.0-L3-CDN

Hardened Mode for Nginx

- [Nginx-Hardened-Mode v1.0-L3-CDN](#nginx-hardened-mode-v10-l3-cdn)
  - [Requirements](#requirements)
  - [Usage](#usage)
    - [nginx.conf](#nginxconf)
    - [hardened_cdn.conf](#hardened_cdnconf)
  - [Features](#features)
    - [Drop Requests from Untrusted Source Address](#drop-requests-from-untrusted-source-address)
    - [Get Latest IPs List of Trusted Service Automatically](#get-latest-ips-list-of-trusted-service-automatically)
    - [Immediately Error Reporting](#immediately-error-reporting)
    - [Any Other Features?](#any-other-features)
  - [Contact Us](#contact-us)

## Requirements
+ libcjson1
+ nginx==1.18.0

## Usage
### [nginx.conf](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/nginx.conf.example) 
```
load_module /etc/nginx/modules/ngx_http_hardened_module.so;

events {}

http {
  include conf.d/*.conf;
}
```
### [hardened_cdn.conf](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/conf.d/hardened_cdn.conf.example)
```

# Funny Systems, Inc.		
# Hardened Mode for Nginx		
# Web App and API Protection (WAAP) Solution		
# E-mail : info+hardened@funny.systems		

# conf version
hardened_mode_version 1;

# accept: on | off
hardened_mode on;

# L3 IP
# accept: off | cloudflare | fastly
hardened_allow_ip_cdn off;

# accept: on | off
hardened_allow_ip_localhost on;

# L3 Fetch Tool
# accept: wget | curl
hardened_fetch_tool wget;

# accept: uint
hardened_fetch_retry_times 2;

# Notification by WebHook, GET only
# accept: http://* | https://*
# hardened_notify_webhook_get 'http://example.com/webhook?msg=some_msg_here&key=key_if_needed';
```

## Features

### Drop Requests from Untrusted Source Address
+ If a request comes from **an address out of trusted list**, it'll be drop immediately.

### Get Latest IPs List of Trusted Service Automatically
+ Make it easier to deal with **IPs lists provided by numerous well-known services** which changed frequently. <br> Currently supported: **CloudFlare, Fastly**.

### Immediately Error Reporting
+ **Auto reporting** while failed over to Normal Mode (Behavior of Original Nginx) by WebHook.
 
### Any Other Features?
+ Checkout [Nginx-Harden-Mode v1.0-L7-HOST](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/README_HOST.md)
+ Or [mail us]((mailto://info+hardened@funny.systems)) to know more

## Contact Us
[Funny Email](mailto://info+hardened@funny.systems) 😍
