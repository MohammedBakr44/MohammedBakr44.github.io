---
author: Mohamed Bakr
pubDatetime: 2025-03-30T03:41:36.086Z
title: Web Enumeration
draft: false
tags:
    - CPTS
    - Getting Started
    - htb academy
    - enumeration
description:
    CPTS Web Enumeration section from the Getting Started module.    
---

> When performing service scanning, we will often run into web servers running on ports **80 and 443**. Webservers host web applications (sometimes more than 1) which often provide a considerable attack surface and a very high-value target during a penetration test.

## GoBuster

> GoBuster is a versatile tool that allows for performing DNS, vhost, and directory brute-forcing. The tool has additional functionality, such as enumeration of public AWS S3 buckets

`gobuster dir -u <target> -w <path_to_wordlist>`

> An HTTP status code of **200** reveals that the resource's request was ***successful***, while a **403** HTTP status code indicates that we are **forbidden** to access the resource. A **301** status code indicates that we are being **redirected**, which is not a failure case.

[list of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).

### DNS Subdomain Enumeration

- Get a [DNS list](https://github.com/danielmiessler/SecLists).
- add a DNS server to `/etc/resolve.conf`.

```bash
gobuster dns -d <target> -w <path_to_seclist>
```

### Banner Grabbing / Web Server Headers

`curl -IL <target>` retrieve server header information.

![](https://i.imgur.com/OCshpjo.png)

> Another handy tool is [EyeWitness](https://github.com/FortyNorthSecurity/EyeWitness), which can be used to take screenshots of target web applications, fingerprint them, and identify possible default credentials.

> We can extract the version of web servers, supporting frameworks, and applications using the command-line tool `whatweb`.

`whatweb <target>`


### Certificates

> SSL/TLS certificates are another potentially valuable source of information if HTTPS is in use. Browsing to `https://10.10.10.121/` and viewing the certificate reveals the details below, including the email address and company name. These could potentially be used to conduct a phishing attack if this is within the scope of an assessment.

![](https://i.imgur.com/yWh8fpM.png)


