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

This infrastructure uses the following technologies:

- Operating System: TrueNAS SCALE  
- File System: ZFS  
- Virtualization: KVM (built into TrueNAS SCALE)  
- Container System: Docker (TrueNAS Apps)  
- Monitoring: Zabbix and Grafana  
- DNS Filtering: Pi-hole  
- Private Cloud: NextCloud  
- Networking: Gigabit Ethernet  
- Remote Access: WireGuard VPN  
- Architecture: x86_64  
- Deployment: On-premise physical server  

---

## Hardware Requirements

Minimum recommended hardware:

- CPU: Intel Core i5 (6th generation or newer) or AMD Ryzen 5 or newer  
- RAM: Minimum 8GB (16GB recommended)  
- OS Drive: Minimum 120GB SSD (240GB–500GB recommended)  
- Storage Drive: Minimum 2TB HDD (4TB–6TB recommended)  
- Application Drive: Minimum 120GB SSD (240GB recommended)  
- Network: Gigabit Ethernet  

Optional but recommended:

- NVMe SSD for virtualization  
- Additional HDD for RAID redundancy  
- UPS for power protection  

---

## Main Services Provided

This server provides multiple infrastructure services:

- Private Cloud Storage using NextCloud  
- Centralized NAS storage  
- File storage using SMB/NFS  
- Backup storage  
- Virtual machine storage  
- Docker container hosting  
- Infrastructure monitoring using Zabbix and Grafana  
- Network-wide DNS filtering using Pi-hole  
- Secure remote access using WireGuard VPN  
- Future service expansion  

---

## Storage Architecture

The storage is separated into multiple disks, each with a specific purpose.

- OS SSD → TrueNAS SCALE system installation  
- HDD Storage → Main storage pool (files, backups, NextCloud, media)  
- Application SSD → Docker containers, monitoring tools, VPN services  
- NVMe SSD (optional) → Virtual machines and lab environments  

This separation improves:

- Performance  
- Stability  
- Scalability  
- Data safety  

---

## Network Configuration

The server is connected using Gigabit Ethernet for maximum stability and performance.

Example access address:

https://192.168.x.x

This allows access to the TrueNAS web interface from any device inside the network.

Remote access is configured using WireGuard VPN.

---

## Why TrueNAS SCALE

TrueNAS SCALE provides a complete infrastructure platform with enterprise-grade features.

Benefits:

- ZFS filesystem with data integrity protection  
- Built-in Docker container support  
- Virtual machine support  
- Web-based management interface  
- Stable 24/7 operation  
- Designed for NAS and infrastructure workloads  

---

## System Design Principles

This server follows important infrastructure design principles:

- Separation of OS and data  
- Dedicated storage for applications  
- Dedicated storage for virtualization  
- Stable 24/7 operation  
- Scalable architecture  
- Secure remote access  

---

## Future Expansion

This system is designed for future expansion, including:

- Jellyfin media server  
- Immich private photo storage  
- Reverse proxy hosting  
- Cybersecurity lab environments  
- Additional virtual machines  
- RAID storage configuration  
- Backup replication  

---

## Author

Developed and maintained by AdrianStudio  

This project is part of a personal HomeLab used for storage, monitoring, virtualization, and infrastructure testing.

---

## Continue Reading

<p align="center">
  <a href="docs/01-hardware.md">
    <img src="https://img.shields.io/badge/START-01_Server_Hardware-blue?style=for-the-badge">
  </a>
</p>

---

