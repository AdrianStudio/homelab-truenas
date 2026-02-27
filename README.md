# HomeLab TrueNAS Server

![Platform](https://img.shields.io/badge/platform-TrueNAS_SCALE-blue)
![Storage](https://img.shields.io/badge/storage-ZFS-green)
![Virtualization](https://img.shields.io/badge/virtualization-KVM-orange)
![Containers](https://img.shields.io/badge/containers-Docker-blue)
![Network](https://img.shields.io/badge/network-Gigabit_Ethernet-red)
![License](https://img.shields.io/badge/license-Personal_Project-lightgrey)

Enterprise-grade HomeLab infrastructure built using TrueNAS SCALE, designed to provide centralized storage, private cloud services, virtualization, infrastructure monitoring, and secure remote access.

This project documents the complete deployment process, including hardware configuration, operating system installation, storage architecture, network configuration, and service deployment.

---

## Overview

This HomeLab server runs on dedicated physical hardware and provides a fully isolated infrastructure environment. The system is designed using a tiered storage architecture, separating operating system, applications, and storage workloads to improve performance, stability, and scalability.

The server operates 24/7 inside a private network and will support secure remote access using VPN.

---

## Technologies Used

Operating System  
TrueNAS SCALE (Linux-based NAS operating system)

Filesystem  
ZFS (Zettabyte File System)

Virtualization  
KVM Hypervisor (integrated in TrueNAS SCALE)

Container Platform  
Docker / Kubernetes (TrueNAS Apps subsystem)

Network Services  
SMB, NFS, SSH, DNS, VPN

Monitoring Stack  
Zabbix, Grafana

Cloud Platform  
NextCloud (private cloud storage)

VPN  
WireGuard

---

## Storage Architecture

The system uses dedicated disks for each workload tier.

OS Tier  
Goldenfir SSD  
Hosts TrueNAS SCALE operating system and boot environment.

Application Tier  
Kingston SSD  
Hosts container storage, application data, monitoring services, and infrastructure tools.

Storage Tier  
WD Red HDD  
Primary storage pool for NAS data, backups, and cloud storage.

Virtualization Tier  
Synology NVMe SSD  
Used for virtual machines, lab environments, and infrastructure testing.

This separation improves performance, prevents resource contention, and simplifies maintenance.

---

## Features

Centralized NAS storage  
Private cloud storage using NextCloud  
Virtual machine hosting for lab environments  
Container-based application deployment  
Infrastructure monitoring using Zabbix and Grafana  
Secure remote access using WireGuard VPN  
Backup storage and ISO repository  
Expandable architecture for future services

---

## Installation

Step 1  
Download TrueNAS SCALE ISO from the official website:

https://www.truenas.com/download-truenas-scale/

Step 2  
Create bootable USB using Balena Etcher.

Step 3  
Boot the server from USB and install TrueNAS SCALE on the dedicated OS SSD.

Step 4  
Access the Web Interface using:

https://SERVER_IP

Step 5  
Create storage pools and datasets.

Step 6  
Configure application storage and deploy services.

Full installation documentation is available in:

docs/02-truenas-installation.md

---

## Repository Structure
