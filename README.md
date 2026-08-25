# 🖥️ Raspberry Pi Home Lab & Infrastructure Project

![Badge: Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Badge: Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi-red)
![Badge: OS](https://img.shields.io/badge/OS-Raspberry%20Pi%20OS-blue)
![Badge: Networking](https://img.shields.io/badge/Network-Ethernet-green)

## 📌 Project Overview

This repository documents the design, deployment and configuration of a Raspberry Pi-based home lab server.

The project was created to gain practical, hands-on experience with Linux server administration, networking, storage management, system security, and infrastructure services.

The lab is built progressively, with each stage documented to record the configuration process, testing, troubleshooting and lessons learned.

The project also serves as a personal technical portfolio demonstrating practical experience with Raspberry Pi, Linux, networking and server infrastructure.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Build a functional Raspberry Pi home server.
- Develop practical Linux system administration skills.
- Configure and manage Ethernet networking.
- Implement SSH-based remote administration.
- Configure external SSD storage for server data.
- Learn Linux filesystem and storage management.
- Develop basic server security practices.
- Document the complete infrastructure setup using Git and GitHub.
- Gradually expand the lab with additional infrastructure and security services.

---

## 🖥️ Hardware

| Component | Specification | Role |
|---|---|---|
| Raspberry Pi 4 | 4GB RAM | Main Server |
| Raspberry Pi 4 | 1GB RAM | Secondary / Future Backup Node |
| External SSD | 480GB | Server Storage |
| microSD Card | 64GB | Main Server OS |
| microSD Card | 32GB | Secondary Server OS |
| Ethernet Cable | Cat6 | Network Connectivity |

---

## 🏗️ Current Architecture

```text
                         INTERNET
                            │
                            │
                         ROUTER
                            │
                          Cat6
                            │
                            ▼
                  ┌──────────────────┐
                  │  Raspberry Pi 4  │
                  │      4GB         │
                  │   Main Server    │
                  └────────┬─────────┘
                           │
                         USB 3.0
                           │
                           ▼
                  ┌──────────────────┐
                  │    480GB SSD     │
                  │   Server Data    │
                  └──────────────────┘


                  ┌──────────────────┐
                  │  Raspberry Pi 4  │
                  │      1GB         │
                  │ Secondary Node   │
                  └──────────────────┘
