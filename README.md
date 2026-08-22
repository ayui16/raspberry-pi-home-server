# Raspberry Pi Home Lab Server

![Status](https://img.shields.io/badge/status-in%20development-yellow)

A personal home lab project built using Raspberry Pi hardware, external SSD storage and Ethernet networking.

The goal of this project is to build a small, reliable and well-documented home server while learning Linux system administration, networking, storage, Docker, security, backup and monitoring.

---

## Project Status

🚧 **Status: In Development**

### Current Phase

**Day 1 - Hardware and OS Preparation**

---

## Hardware

| Component | Specification | Role |
|---|---|---|
| Raspberry Pi 4 | 4GB RAM | Main Server |
| Raspberry Pi 4 | 1GB RAM | Secondary / Backup Server |
| External SSD | 480GB | Server Storage |
| microSD Card | 64GB | Main Server OS |
| microSD Card | 32GB | Secondary Server OS |
| Ethernet Cable | Cat6 | Network Connection |

---

## Planned Architecture

```text
                    INTERNET
                       |
                    ROUTER
                  /         \
               Cat6         Cat6
                /             \
               /               \
      Raspberry Pi 4      Raspberry Pi 4
          4GB                  1GB
      Main Server          Backup Node
           |
         USB 3
           |
      480GB SSD
       Data Storage
---
