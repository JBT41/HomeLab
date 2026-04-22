# HomeLab – Linux-Based Container Platform

## Overview

This repository documents a self-hosted Linux homelab running on an HP MicroServer.  
The lab is used to explore containerisation, service routing, monitoring, and operational tooling commonly found in production environments.

It is built as a single-node platform using Docker Compose, with an emphasis on service isolation, internal DNS routing, and observability.

---

## Platform

- Host: HP MicroServer (bare metal)
- Operating System: Linux - Ubuntu Server
- Container Runtime: Docker
- Orchestration: Docker Compose
- Network: Private LAN (192.168.0.0/24)

---

## Core Components

### DNS and Reverse Proxy
- AdGuard Home for DNS resolution and ad blocking
- NGINX used as a reverse proxy for hosted services
- Internal domain routing implemented (e.g. `lab.home.com`)
- Traffic routed internally to services such as:
  `lab.home.com → 192.168.0.100:8080`

---

## Hosted Services

- Checkmk  
  Centralised system and service monitoring

- Portainer  
  Container and Docker stack management

- AdGuard Home  
  DNS filtering and local domain resolution

- NGINX  
  Reverse proxy and service routing

- Java Dashboard (custom-built)  
  Lightweight internal portal linking all hosted services

---

## Architecture

Client  
↓  
AdGuard DNS  
↓  
NGINX Reverse Proxy  
↓  
Containerised Services  
- Checkmk  
- Portainer  
- AdGuard  
- Java Dashboard  

---

## Purpose

This homelab exists to replicate realistic operational patterns in a controlled environment, including:

- Linux system ownership
- Containerised service management
- Internal DNS and reverse proxy routing
- Monitoring and observability
- Operating and maintaining long-running services
- Building small tools to improve operational usability

---

## Notes

This environment is used for experimentation and learning.  
Configurations prioritise clarity and reliability over scale.

---

## Disclaimer

All hostnames, domains, and network details are local to the homelab and are not publicly exposed.
---

## Adguard DNS re-writes
<img width="3833" height="971" alt="image" src="https://github.com/user-attachments/assets/ff8e60ad-1f3e-4658-bdfb-10bfaa19d402" />

## Nginx proxy hosts
<img width="3827" height="588" alt="image" src="https://github.com/user-attachments/assets/2636f24f-6119-4556-b3ea-ea66bdaf689e" />

## Aguard Qery log

shows we-writes occuring
<img width="1805" height="908" alt="image" src="https://github.com/user-attachments/assets/e71c9625-391b-4e03-9cd8-f414e306e06b" />

## Spring-Boot dashboard
<img width="3828" height="1379" alt="image" src="https://github.com/user-attachments/assets/a6477ce1-e092-4409-a9c8-9db948da5c48" />

## CheckMk
<img width="2721" height="1233" alt="image" src="https://github.com/user-attachments/assets/3bc31f02-a800-4286-9277-61b0788da407" />




