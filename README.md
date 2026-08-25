# 🛡️ Enterprise Infrastructure & Cybersecurity Lab

![Badge: Status](https://img.shields.io/badge/Status-Completed-success)
![Badge: Role](https://img.shields.io/badge/Role-Cloud%20&%20Security%20Engineer-blue)

## 📌 Project Overview
This repository documents a comprehensive, hands-on lab designed to simulate a real-world enterprise IT environment. The project covers the end-to-end lifecycle of infrastructure deployment, containerization, network reconnaissance (Red Team), and system hardening (Blue Team). 

**Objective:** To demonstrate practical proficiency in Linux server administration, Docker containerization, network security, and incident monitoring.

## 🛠️ Technology Stack
* **OS & Infrastructure:** Debian/Ubuntu Linux, SSH Key Authentication, Static IP Routing.
* **Containerization:** Docker Engine, Docker Volumes.
* **Web Services:** Nginx.
* **Security & Networking:** UFW (Uncomplicated Firewall), Nmap, tcpdump, Apache Benchmark (`ab`), Rate Limiting (Fail2Ban logic).
* **Monitoring:** Uptime Kuma (Real-time alerting).

## 🚀 Lab Progression (8-Day Journey)

| Phase | Day | Focus Area | Key Achievements |
| :--- | :---: | :--- | :--- |
| **I. Infrastructure** | [Day 1 & 2](Day1-2.md) | OS & Networking | Deployed dual Linux servers, configured Static IPs, DNS resolution (`/etc/hosts`), and storage formatting (`ext4` automount). |
| | [Day 3 & 4](Day3-4.md) | Security Basics | Implemented passwordless SSH authentication (RSA keys) and UFW traffic filtering. |
| **II. Deployment** | [Day 5](Day5.md) | Containerization | Installed Docker (rootless), deployed Nginx web server, and customized internal container files (`docker cp`). |
| | [Day 5](Day5.md) | Active Monitoring | Deployed Uptime Kuma to track application uptime and latency metrics in real-time. |
| **III. Cyber Attack** | [Day 6](Day6.md) | Reconnaissance | Executed `nmap` stealth scans and monitored packet-level traffic on the target node using `tcpdump`. |
| | [Day 7](Day7.md) | DoS Simulation | Conducted HTTP Flood stress testing using `ab` to analyze server resource exhaustion and Uptime Kuma latency spikes. |
| **IV. Defense** | [Day 8](Day8.md) | Hardening | Implemented Application-Level Rate Limiting in Nginx, successfully mitigating the DoS attack by dropping 97.7% of malicious traffic. |

## 🎓 Key Takeaways
This project bridges the gap between theoretical knowledge and practical execution. By building the infrastructure from scratch, breaking it via simulated attacks, and ultimately hardening it, I have developed a holistic understanding of how systems operate and how to secure them against modern threats.

---
*Managed and documented by Ayui.*
