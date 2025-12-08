---
title: "Blog 1"
date: 2025-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# How AWS Protects Customers from DDoS Events

## Overview  
Since late August 2023, AWS detected and protected against a new kind of DDoS event: an **HTTP/2 request flood**, specifically called an **HTTP/2 rapid reset attack**, targeting Amazon CloudFront. These floods suddenly sent huge volumes of HTTP/2 connection requests followed rapidly by resets, overwhelming servers by forcing them to log and parse requests before cancellation. :contentReference[oaicite:0]{index=0}

## Key Event Details  
- The spike occurred **August 28–29, 2023**, peaking at **over 155 million requests per second** via CloudFront. :contentReference[oaicite:1]{index=1}  
- AWS observed and mitigated multiple of these HTTP/2 rapid reset events in that period, then continued seeing them into September. :contentReference[oaicite:2]{index=2}  
- Customers with **DDoS-resilient architectures** — using services like CloudFront, AWS Shield — maintained availability during those attacks. :contentReference[oaicite:3]{index=3}

## Understanding HTTP/2 Rapid Reset Attacks  
- HTTP/2 allows multiple logical streams over one session, different from HTTP/1.x. :contentReference[oaicite:4]{index=4}  
- Attackers issue many requests, then quickly reset each stream. Servers still incur overhead: parsing, logging, etc., even if response isn't delivered. :contentReference[oaicite:5]{index=5}  
- These are a subclass of HTTP request floods; important to detect and absorb malicious traffic before it reaches origin systems. :contentReference[oaicite:6]{index=6}

## AWS’s Defensive Measures and Best Practices  
- AWS provides built-in DDoS protection across its infrastructure. :contentReference[oaicite:7]{index=7}  
- Key services to use for resilience: Amazon CloudFront, AWS Shield (including Shield Advanced), AWS WAF, Amazon Route 53, Route 53 Application Recovery Controller. These help when serving traffic from global edge locations, preventing unnecessary requests from reaching origin servers. :contentReference[oaicite:8]{index=8}  
- Use caching at edge (e.g. CloudFront), careful filtering (WAF), and global routing/resiliency (Route 53) to absorb or block malicious traffic. :contentReference[oaicite:9]{index=9}  

## Threat Intelligence, Monitoring, and Collaboration  
- AWS continuously monitors for unusual traffic patterns and works proactively to detect threats. :contentReference[oaicite:10]{index=10}  
- Engineers combine global threat intelligence, telemetry, and automated mitigation to stay ahead of new DDoS methods. :contentReference[oaicite:11]{index=11}  
- AWS collaborates with external entities (CERTs, ISPs, registrars, other cloud providers) to trace, mitigate, and sometimes dismantle sources of large DDoS attacks. :contentReference[oaicite:12]{index=12}  

## Summary  
AWS responded swiftly to a novel HTTP/2 rapid reset DDoS attack in late August/early September 2023. Thanks to built-in protections + resilience-focused architectures using services like CloudFront, Shield, WAF, and Route 53, customers were able to maintain availability. Ongoing monitoring, threat intelligence, and infrastructure-level mitigations are central to AWS’s approach to protecting from evolving DDoS threats.  
