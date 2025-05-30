---
author: Mohamed Bakr
pubDatetime: 2025-03-29T03:41:36.086Z
title: Pentesting Process
featured: true
draft: false
tags:
    - CPTS
    - Getting Started
    - htb academy
    - red teaming
    - pentesting
description:
    Pentesting process summary.
---

> A pentest aims to uncover and identify ALL vulnerabilities in the systems under investigation and improve the security for the tested systems.


![](https://i.imgur.com/Zvh6QMX.png)

![](https://i.imgur.com/tytHi35.png)

### Vulnerability Assessment
Scanning the system for vulnerabilities, and rank them based on severity.

- Nessus
- nuclei
### Exploitation
After scanning the system for vulns, we start using the vunls to exploit the system.

### Post-Exploitation and Lateral Movement
Using *Prevesc* to move between accounts or devices in the system.

### Post-Engagement
Cleaning the tools and scripts used for exploitation.


## Information Gathering
- Open-Source Intelligence.
- Infrastructure Enumeration.
- Service Enumeration.
- Host Enumeration.

### OSINT
The process or finding publicly available information on a target.

### Infrastructure Enumeration
Using OSINT and other services, we try to gather information about the infrastructure used by the target.


### Service Enumeration
Identify the services we use to interact with the target.
