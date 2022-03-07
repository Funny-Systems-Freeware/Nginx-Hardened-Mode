# Nginx-Hardened-Mode

Hardened Mode for Nginx

+ [Requirements](#requirements)
+ [Features](#features)
  + [drop requests for unknown server name](#drop-requests-for-unknown-server-name-v10-l7-host)
  + [drop requests from untrusted source address](#drop-requests-from-untrusted-source-address-v10-l3-cdn)
  + [get latest ips list of trusted service automatically](#get-latest-ips-list-of-trusted-service-automatically-v10-l3-cdn)
  + [immediately error reporting](#immediately-error-reporting)
+ [Roadmap](#roadmap)
+ [Known Issue](#known-issue)
+ [Contact Us](#contact-us)

## Requirements
+ nginx==1.18.0

## Features
||v1.0-L7-Host|v1.0-L3-CDN|
| --- | :---: | :---: |
|server name validation|O|❌|
|source ip address validation|❌|O|

### Drop Requests for Unknown Server Name (v1.0-L7-Host)
　If a request ask for server name out of trusted list, it'll be drop immediately.

### Drop Requests from Untrusted Source Address (v1.0-L3-CDN)
　If a request comes from an address out of trusted list, it'll be drop immediately.

### Get Latest IPs List of Trusted Service Automatically (v1.0-L3-CDN)
　Make it easier to deal with IPs lists provided by numerous well-known services which changed frequently. Currently supported: CloudFlare, Fastly.

### Immediately Error Reporting
　Auto reporting while failed over to Normal Mode (Behavior of Original Nginx) by WebHook.

## Roadmap
 + ✅ Server name validation
 + ✅ Source IP address validation
 + ✅ IP List of CDN (ex: cloudflare, fastly...etc)
 + 🚀 IP List of Public Cloud (ex: gcp, azure, aws, akamai... etc)
 + 🚀🚀 Secret Sauce :)

## Known Issues
+ Commands `nginx -s reload` and `nginx -s stop` might fail in certain conditions. If encounter such error, you might have to kill nginx processes manually.

## Contact Us
[Funny Email](mailto://info+hardened@funny.systems) 😍
