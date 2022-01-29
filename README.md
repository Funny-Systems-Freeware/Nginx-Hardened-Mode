# Nginx-Hardened-Mode

Hardened Mode for Nginx

+ [Requirements](#requirements)
+ [Features](#features)
  + [drop requests from unrusted source address](#drop-requests-from-untrusted-source-address)
  + [get latest ips list of trusted service automatically](#get-latest-ips-list-of-trusted-service-automatically)
  + [immediately error reporting](#immediately-error-reporting)
+ [Roadmap](#roadmap)
+ [Known Issue](#known-issue)
+ [Contact Us](#contact-us)

## Requirements
+ libcjson1
+ nginx==1.18.0

## Features
### Drop Requests from Untrusted Source Address
　If a request comes from an address out of trusted list, it'll be drop immediately.

### Get Latest IPs List of Trusted Service Automatically
　Make it easier to deal with IPs lists provided by numerous well-known services which changed frequently. Currently supported: CloudFlare, Fastly.

### Immediately Error Reporting
　Auto reporting while failed over to Normal Mode (Behavior of Original Nginx) by WebHook.
 
 ## Roadmap
 + ✅ Source IP address validation
 + ✅ IP List of CDN (ex: cloudflare, fastly...etc)
 + 🚀 IP List of Public Cloud (ex: gcp, azure, aws, akamai... etc)
 + 🚀🚀 Secret Sauce :)

## Known Issues
+ Commands `nginx -s reload` and `nginx -s stop` might fail in certain conditions. If encounter such error, you might have to kill nginx processes manually.
+ Binary compatibility (ex: Nginx MODULE SIGNATURE)

## Contact Us
[Funny Email](mailto://info+hardened@funny.systems) 😍
