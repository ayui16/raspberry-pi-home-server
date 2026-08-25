# 🚀 Day 7: Denial of Service (DoS) Simulation & Stress Testing

## 📝 Summary
Today's objective was to simulate a Denial of Service (DoS) condition (specifically an HTTP Flood attack) against the Nginx web server. The goal was to understand server capacity, monitor resource exhaustion in real-time, and analyze post-attack benchmarking logs to assess the infrastructure's resilience under heavy load.

## ✅ Achievements
- [x] **Stress Testing Tool Deployment:** Installed `apache2-utils` on Server 1 to utilize the Apache Benchmark (`ab`) tool for generating high-volume, concurrent HTTP requests.
- [x] **HTTP Flood Simulation (Red Team):** Successfully launched a controlled HTTP flood attack, generating over 500,000 total requests with a concurrency level of 500 against the target web server.
- [x] **Live Performance Monitoring:** Monitored the attack's impact via the Uptime Kuma dashboard. Discovered practical limitations of polling intervals (60s vs 20s) in detecting short-burst traffic spikes.
- [x] **Post-Attack Log Analysis:** Analyzed the benchmark output to evaluate server performance. 
  - **Key Metrics Logged:**
    - `Requests per second`: ~3,400+ req/sec
    - `Failed requests`: 0 (Demonstrating Nginx's event-driven architecture efficiency)
    - `Max latency`: Increased to 235ms during peak load

## 💻 Key Commands Used
```bash
# 1. Install Benchmarking/Stress Tool
sudo apt update && sudo apt install apache2-utils -y

# 2. Launch HTTP Flood Attack (500,000 requests, 500 concurrency)
ab -n 500000 -c 500 http://<TARGET_IP>/
