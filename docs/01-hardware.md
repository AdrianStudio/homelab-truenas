# 01 - Server Hardware

## Project Scope

This project will use a physical server dedicated to providing services, such as:

- Private Cloud Storage (NextCloud)
- Centralized NAS
- Virtual Machine Storage
- Network-wide DNS filtering
- Infrastructure monitoring
- Secure remote access (VPN)
- Future service expansion (media server, containers, hosting, etc)

All of this is built on dedicated physical hardware running TrueNAS SCALE.

---

## Server Platform

For this project you can use any old desktop that has a 6th generation or newer Intel CPU / AMD Ryzen 5 or newer.

I am using an old HP ProDesk 600 G2 SFF with the next specs:

- Model: HP ProDesk 600 G2 SFF
- CPU: Intel Core i5-6500 (4 cores / 4 threads)
- Architecture: x86_64
- RAM: 16GB DDR4
- Network: Integrated Gigabit Ethernet
- Deployment: On-premise home network

There are many old desktops like this one that run around 70–100€, maybe even an old one you've got sitting at home.

## Why this platform?

- Low power consumption
- Sufficient CPU for virtualization and containers
- Expandable storage options
- Ideal for long-running 24/7 services

---

### 1. Storage

For this project I will use:

- 6 TB WD HDD SATA 3.5
- 500 GB Goldenfir SSD
- 240 GB Kingston SSD
- 800 GB SSD NVMe M.2 (Synology M2D20)

You can adapt this to your needs, I chose these components as they were spare parts I had from other projects, but if you're planning to build a decent sized NAS and other services, I recommend you have at least 3–5 TB in total (for the dedicated OS SSD, storage, backups, etc / distributed in 2/4 disks).

### 2. Operating System Drive

- Model: Goldenfir SSD
- Capacity: 500 GB
- Interface: SATA
- Purpose: Dedicated TrueNAS SCALE installation

**Why dedicated OS disk?**

This is best to do because it isolates the system from data pools, reduces risk of data corruption, simplifies recovery, improves operational stability. I chose to install it on the Goldenfir SSD because it has a faster speed than the other disks and it will boot the system faster. I recommend at least a 120 GB SSD to install your OS, even though 240–500 GB SSD is optimal.

---

### 3. Primary Data Storage

- Model: WD Red HDD
- Capacity: 6 TB
- Type: NAS-grade HDD
- Purpose: Main storage pool

I will use this for my NextCloud data, file storage (SMB/NFS), media storage, backups, ISO storage, etc. 6 TB is not necessary, but I recommend having 2–4 TB minimum, as this will guarantee you have plenty of space and room for future expansions or projects.

**Benefits:**

- Optimized for 24/7 NAS usage
- High capacity
- Cost-efficient per TB

---

### 4. Application Storage

- Model: Kingston SSD
- Capacity: 240 GB
- Interface: SATA
- Purpose: Application and container storage

I will use this to run many services, for now I will run Zabbix, Grafana, Pi-Hole, WireGuard and Docker-based services. This will only take up about 30–60 GB, which will leave me with about 180 GB free for future incorporations. Minimum recommended to run services is 60–120 GB, but 120–240 GB is optimal.

**Benefits:**

- Faster I/O for applications
- Reduced latency
- Improved dashboard responsiveness

---

### 5. Virtualization Storage (NVMe)

- Type: NVMe SSD via PCIe adapter
- Purpose: Virtual machines and lab environments

I will use this to store virtual machine disks, including Linux VMs, Windows Server lab environments, cybersecurity lab systems, test environments, and future infrastructure services. I do this on a NVMe SSD because VMs constantly perform disk reads and writes, OS boot operations, logging, database access, etc, which are I/O intensive.

NVMe provides much faster read/write speeds than SATA SSD, it has extremely low latency and high IOPS (Input/Output Operations Per Second).

I will also use this NVMe storage for Docker container storage, lab environments, testing infrastructure deployments, and temporary environments.

You could do this on a HDD, as a PCIe NVMe SSD can be pricey, but it has its disadvantages:

- High latency
- Slow random access
- Poor VM performance
- System lag under load

---

## Network Design

- Connection type: Gigabit Ethernet
- IP assignment: DHCP (recommended: DHCP reservation)

This server is deployed inside a private LAN and will later be accessible remotely via VPN.

Ethernet is not mandatory, but it's very recommended. Many old PCs don't have wireless WiFi. My recommendations if you can't connect the Ethernet cable are using a WiFi card (not USB WiFi), or using an Ethernet WiFi repeater that you can connect near the PC, and then connect via Ethernet.

---

## Design Principles

This hardware configuration follows:

- Separation of OS and data
- Performance tiering (HDD + SSD + NVMe)
- Expandability
- Service isolation
- 24/7 reliability

---

## Expansion Capability

The system is designed to support future services such as:

- Jellyfin (media streaming)
- Immich (photo backup)
- Reverse proxy hosting
- SIEM platforms
- Additional virtual machines
- Backup replication

---
