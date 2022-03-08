# Nginx-Hardened-Mode

Hardened Mode for Nginx

- [Nginx-Hardened-Mode](#nginx-hardened-mode)
  - [Features](#features)
    - [1. Drop Requests for Unknown Server Name](#1-drop-requests-for-unknown-server-name)
    - [2. Drop Requests from Untrusted Source Address](#2-drop-requests-from-untrusted-source-address)
    - [3. Get Latest IPs List of Trusted Service Automatically](#3-get-latest-ips-list-of-trusted-service-automatically)
    - [4. Immediately Error Reporting](#4-immediately-error-reporting)
  - [Distribution of Nginx-Hardened-Mode](#distribution-of-nginx-hardened-mode)
  - [Roadmap](#roadmap)
  - [Known Issues](#known-issues)
  - [Contact Us](#contact-us)

## Features
||v1.0-L7-Host|v1.0-L3-CDN|
| --- | :---: | :---: |
|1. Server Name Validation|O|❌|
|2. Source IP Address Validation|❌|O|
|3. Auto Update Trusted IPs List|❌|O|
|4. Immediately Error Reporting|O|O|

### 1. Drop Requests for Unknown Server Name
+ If a request ask for **server name out of trusted list**, it'll be drop immediately.

### 2. Drop Requests from Untrusted Source Address
+ If a request comes from **an address out of trusted list**, it'll be drop immediately.

### 3. Get Latest IPs List of Trusted Service Automatically
+ Make it easier to deal with **IPs lists provided by numerous well-known services** which changed frequently. <br> Currently supported: **CloudFlare, Fastly**.

### 4. Immediately Error Reporting
+ **Auto reporting** while failed over to Normal Mode (Behavior of Original Nginx) by WebHook.

## Distribution of Nginx-Hardened-Mode
+ **v1.0-***
  + [Instruction for v1.0-L3-CDN](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/README_CDN.md)
  + [Instruction for v1.0-L7-Host](https://github.com/Funny-Systems-Freeware/Nginx-Hardened-Mode/blob/main/README_HOST.md)

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
