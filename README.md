# HomeLab TrueNAS Server

![platform](https://img.shields.io/badge/platform-TrueNAS_SCALE-blue?style=for-the-badge)
![storage](https://img.shields.io/badge/storage-ZFS-green?style=for-the-badge)
![services](https://img.shields.io/badge/services-NextCloud_|_Zabbix_|_Docker-orange?style=for-the-badge)
![network](https://img.shields.io/badge/network-Gigabit_Ethernet-red?style=for-the-badge)
![remote](https://img.shields.io/badge/remote-WireGuard_VPN-purple?style=for-the-badge)

---

## Project Overview

This project consists of building a complete HomeLab server using TrueNAS SCALE running on dedicated physical hardware.

The purpose of this server is to replace cloud services like iCloud, provide centralized storage, run applications, host virtual machines, monitor infrastructure, and allow secure remote access from anywhere.

This server runs 24/7 inside a home network and is accessible locally and remotely through VPN.

---

## Platform and Technology

Operating System: TrueNAS SCALE  
File System: ZFS  
Virtualization: KVM (built into TrueNAS SCALE)  
Container System: Docker (TrueNAS Apps)  
Monitoring: Zabbix and Grafana  
Networking: Gigabit Ethernet  
Remote Access: WireGuard VPN  
Architecture: x86_64  
Deployment: On-premise physical server  

---

## Main Services Provided

This server provides multiple infrastructure services:

Private Cloud Storage using NextCloud  
Centralized NAS storage for files, backups and media  
Virtual machine storage and lab environments  
Network-wide DNS filtering using Pi-hole  
Infrastructure monitoring using Zabbix and Grafana  
Secure remote access using WireGuard VPN  
Docker container hosting  
Future services such as media streaming, reverse proxy hosting and infrastructure testing  

---

## Storage Architecture

The storage is separated into multiple disks, each with a specific purpose.

Operating System SSD  
Used only for TrueNAS SCALE installation. This ensures system stability and prevents data corruption.

Main Storage HDD  
Used for file storage, backups, NextCloud data, media and ISO storage.

Application SSD  
Used for Docker containers, monitoring tools, VPN services and infrastructure applications.

NVMe SSD (optional)  
Used for virtual machines and lab environments, providing maximum performance and low latency.

This separation improves performance, stability and scalability.

---

## Network Configuration

The server is connected using Gigabit Ethernet to ensure maximum stability and performance.

Example access address:

https://192.168.x.x

This IP address allows access to the TrueNAS web interface from any device inside the network.

Remote access is configured later using WireGuard VPN, allowing secure access from outside the network.

---

## Why TrueNAS SCALE

TrueNAS SCALE was chosen because it provides enterprise-grade storage, virtualization and container support in a single platform.

Main benefits:

ZFS file system with data integrity protection  
Built-in Docker container support  
Virtual machine support  
Web-based management interface  
High stability for 24/7 operation  
Designed specifically for NAS and infrastructure workloads  

---

## System Design Principles

This server follows important infrastructure design principles:

Separation between OS, applications and data  
Dedicated storage for each workload type  
High reliability for continuous operation  
Scalable architecture for future expansion  
Secure remote access through VPN  
Centralized infrastructure management  

---

## Future Expansion

This server is designed to support future infrastructure and services such as:

Jellyfin media streaming server  
Immich private photo storage  
Reverse proxy hosting  
Cybersecurity lab environments  
Additional virtual machines  
Backup replication systems  
Additional storage expansion  

---

## Author

Developed and maintained by AdrianStudio  

This project is part of a personal infrastructure lab used for learning, storage, monitoring and service hosting.

---

## Documentation

This repository contains full step-by-step documentation of the entire setup process, including hardware configuration, TrueNAS installation, storage configuration, application deployment and remote access setup.

---

## Continue Reading

<p align="center">
  <a href="docs/01-server-hardware.md">
    <img src="https://img.shields.io/badge/START-01_Server_Hardware-blue?style=for-the-badge">
  </a>
</p>

---
