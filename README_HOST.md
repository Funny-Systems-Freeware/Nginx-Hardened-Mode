# Nginx-Hardened-Mode v1.0-L7-HOST

Hardened Mode for Nginx

- [Nginx-Hardened-Mode v1.0-L7-HOST](#nginx-hardened-mode-v10-l7-host)
  - [Requirements](#requirements)
  - [Usage](#usage)
    - [nginx.conf](#nginxconf)
    - [hardened_host.conf](#hardened_hostconf)
  - [Features](#features)
    - [Drop Requests for Unknown Server Name](#drop-requests-for-unknown-server-name)
    - [Immediately Error Reporting](#immediately-error-reporting)
    - [Any Other Features?](#any-other-features)
  - [Contact Us](#contact-us)

## Requirements
+ nginx==1.18.0

## Usage
### [nginx.conf](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/nginx.conf.example) 
```
load_module /etc/nginx/modules/ngx_http_hardened_oss_module.so;

events {}

http {
  include conf.d/*.conf;
}
```
### [hardened_host.conf](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/conf.d/hardened_host.conf.example)
```
# Funny Systems, Inc.		
# Hardened Mode for Nginx		
# Web App and API Protection (WAAP) Solution		
# E-mail : info+hardened@funny.systems		

# string "on" | "off"
hardened_mode "on" ;
# int 1
hardened_mode_version 1 ;
			
#L3 Fetch Tool
# string "wget" | "curl"
hardened_fetch_tool "wget" ;
# int 3
hardened_fetch_retry_times 3 ;
#L7 Host
# string "on" | "off" 
hardened_check_http_host "on" ;
			
#Notify	WebHook
# string "http://" 
hardened_notify_webhook_get "https://example.com/";
```

## Features

### Drop Requests for Unknown Server Name
+ If a request ask for **server name out of trusted list**, it'll be drop immediately.

### Immediately Error Reporting
+ **Auto reporting** while failed over to Normal Mode (Behavior of Original Nginx) by WebHook.

### Any Other Features?
+ Checkout [Nginx-Harden-Mode v1.0-L3-CDN](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/README_CDN.md)
+ Or [mail us]((mailto://info+hardened@funny.systems)) to know more

## Contact Us
[Funny Email](mailto://info+hardened@funny.systems) 😍
