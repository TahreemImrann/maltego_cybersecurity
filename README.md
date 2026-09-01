# Maltego OSINT Reconnaissance — Systems Limited (systemsltd.com)

## Overview
This repository documents an Open Source Intelligence (OSINT) reconnaissance exercise performed using **Maltego CE** on Kali Linux, targeting the publicly available digital footprint of **Systems Limited** (`systemsltd.com`), a technology consulting firm.

The exercise was completed as part of a cybersecurity internship task focused on link-analysis and attack-surface mapping using Maltego's transform engine.

## Objective
Starting from a single root entity (`systemsltd.com`), run a structured sequence of Maltego transforms to map:
- DNS infrastructure (NS, MX, SOA, SPF records)
- Mail protection / hosting providers
- Associated netblocks and IP addresses (IPv4/IPv6)
- Geographic location of hosting infrastructure
- Related domains and subdomains

## Environment
- **OS:** Kali Linux
- **Tool:** Maltego CE (Community Edition) 4.12.1
- **License:** Community/Basic plan (200 transform credits)

## Methodology
1. Installed Maltego via `sudo apt install -y maltego`
2. Created a new graph and initialized a **Domain** entity: `systemsltd.com`
3. Ran 18 transforms across CTI, DNS, search-engine, and local property-extraction categories (full list and results in `Maltego.docx` / report)
4. Documented each transform's output, including one failed transform (blacklist check via URLhaus — 401 Unauthorized)
5. Compiled findings into a final topology graph and written report

## Key Findings
- Mail protection routed through Microsoft 365 (`*.mail.protection.outlook.com`)
- Four authoritative UltraDNS name servers (`edns3.ultradns.com/.net/.org/.biz`)
- SPF and SOA records revealing administrative contacts and backup name server
- Multiple netblocks and dual-stack IPv4/IPv6 host addresses
- Hosting infrastructure geolocated to the United States

## Files
- `Maltego.docx` — Full write-up with screenshots and transform-by-transform results
- `graph/` — Exported Maltego graph file(s) *(if included)*

## Disclaimer
This reconnaissance was conducted using **passive and non-intrusive OSINT techniques only**, against publicly available information, for educational purposes as part of an internship assignment. No active exploitation, unauthorized access, or intrusive scanning was performed.

## Author
Tahreem Imran — BS Computer Science, Roll No. F23-0114
