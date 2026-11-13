# Week 2: Footprinting & Network Scanning (Penetration Testing Report)

**Author:** Diallo Mulyata
**Program:** Cybersecurity program at Networkwalks | **Batch:** B034 | **Week:** 02
**Date:** 13 November 2026

## Overview

This project covers the reconnaissance and scanning phases of a penetration test. I gathered public information about the networkwalks.com domain, practised passive information gathering with theHarvester, and scanned my own local network with Zenmap. The full write-up is in the report.

## Modules Completed

| Module | Topic | Phase |
| --- | --- | --- |
| W2-PM1 | Multiple Kali Linux tools | Reconnaissance & Footprinting |
| W2-PM4 | theHarvester | Reconnaissance & Footprinting |
| W2-PM5 | Zenmap network scanning | Scanning & Network Discovery |

## Tools Used

| Tool | Purpose |
| --- | --- |
| WHOIS | Domain registration details |
| WhatWeb | Fingerprint web technologies |
| nslookup | Resolve the domain to an IP address |
| curl -I | Read HTTP response headers |
| wafw00f | Detect a Web Application Firewall |
| DNSRecon | Enumerate DNS records |
| theHarvester | Collect public emails, hosts and IPs (OSINT) |
| Zenmap (Nmap GUI) | Discover live hosts on the local subnet |

## Key Findings

**Footprinting (networkwalks.com)**
- Registered through GoDaddy.com, LLC, created 6 November 2019
- Name servers: NS6135.HOSTGATOR.COM and NS6136.HOSTGATOR.COM, DNSSEC unsigned
- Resolves to 192.232.216.135 and runs WordPress on an Apache server
- Protected by ModSecurity (SpiderLabs) WAF
- HTTP headers expose the WordPress REST API endpoint (`/wp-json/`)
- DNS records show mail, SPF, SRV records and the BIND version of both name servers

**theHarvester**
- A Baidu-only search returned no IPs, emails, people or hosts
- Other data sources failed because no API keys were configured
- Lesson: OSINT results depend on the sources and API keys available

**Zenmap (local network)**
- Subnet scanned: `172.20.10.0/28`
- Two live hosts found: `172.20.10.1` and `172.20.10.4` (both my own devices)
- Network topology saved as a PDF

## Risk Summary

The report rates each observation (Low or Medium) and lists recommendations, such as reviewing publicly exposed technology information, keeping software updated, and limiting version disclosure in DNS. These are observations from information gathering, not confirmed vulnerabilities.

## Report

The full report (introduction, tools, activities, risk analysis, recommendations, conclusion and screenshot evidence) is in:

`W2-PM-FINAL_Report_Diallo_Mulyata.docx`

## Disclaimer

These activities were performed only on systems and devices where I had permission or that I own. This material is for education and research only. Do not use anything shown here against systems you do not have written permission to test.
