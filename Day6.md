# 🚀 Day 5: Containerization, Web Hosting & System Monitoring

## 📝 Summary
The objective for today was to introduce containerization technology using Docker, deploy a live web server, and establish a centralized monitoring dashboard. Modifying the container's internal file system demonstrates practical control over containerized environments, a highly sought-after skill in DevOps and Cybersecurity.

## ✅ Achievements
- [x] **Docker Engine Setup:** Installed the official Docker runtime on Server 1 and configured user privileges for seamless command execution.
- [x] **Nginx Web Server Deployment:** Launched an Nginx container (`ayui-web`) with port mapping (80:80).
- [x] **UFW Firewall Configuration:** Successfully opened TCP ports 80 (HTTP) and 3001 (Monitoring) to allow inbound traffic while maintaining system security.
- [x] **Web Defacement / Customization:** Utilized `docker cp` to overwrite the default Nginx `index.html` with a custom-coded portfolio landing page, demonstrating host-to-container file manipulation.
- [x] **Active Monitoring (Uptime Kuma):** Deployed a persistent Uptime Kuma container using Docker Volumes (`uptime-kuma-data`). Configured HTTP tracking for the Web Server and Ping tracking for the Target Node (Server 2).

## 💻 Key Commands Used
```bash
# Nginx Deployment
docker run -d -p 80:80 --name ayui-web nginx

# Customizing the Web Server (Host-to-Container Copy)
docker cp index.html ayui-web:/usr/share/nginx/html/index.html

# Uptime Kuma Deployment with Persistent Volume
docker volume create uptime-kuma-data
docker run -d --restart=always -p 3001:3001 -v uptime-kuma-data:/app/data --name uptime-kuma louislam/uptime-kuma:1

# Firewall Adjustments
sudo ufw allow 80/tcp
sudo ufw allow 3001/tcp
