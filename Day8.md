# 🚀 Day 8: Infrastructure Hardening & Defensive Security (Blue Team)

## 📝 Summary
Following the DoS simulation, today's objective shifted to defensive security (Blue Teaming). The goal was to implement Application-Level Rate Limiting on the Nginx web server to mitigate HTTP Flood attacks and protect server resources from abuse.

## ✅ Achievements
- [x] **Nginx Configuration Modification:** Created a custom `nginx-secure.conf` file overriding the default settings to implement strict traffic control.
- [x] **Rate Limiting Implementation:** Configured `limit_req_zone` to restrict inbound traffic to **10 requests per second (10r/s)** per IP address, with a burst allowance of 20.
- [x] **Container Hot-Swapping:** Used `docker cp` to inject the new configuration into the live Nginx container and restarted the service to apply changes without downtime.
- [x] **Defense Validation & Testing:** Reran the Apache Benchmark (`ab`) DoS attack to verify the defense mechanism.
  - **Key Metrics Logged:**
    - `Total Requests`: 1,000
    - `Non-2xx responses`: 977 (Confirming the server successfully intercepted and dropped 97.7% of the malicious traffic by serving HTTP 503 errors).

## 💻 Key Configurations Used
```nginx
# Defining the memory zone and rate limit (10 req/sec)
limit_req_zone $binary_remote_addr zone=perisai_ayui:10m rate=10r/s;

# Applying the limit to the web root with a burst queue of 20
limit_req zone=perisai_ayui burst=20 nodelay;
