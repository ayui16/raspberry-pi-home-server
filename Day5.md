# 🚀 Day 5: Containerization, Web Hosting & System Monitoring

## 📝 Summary
Today's focus was on modern infrastructure deployment using containerization. I successfully set up Docker, deployed a live web server (Nginx), and established a centralized monitoring dashboard (Uptime Kuma). I also demonstrated container file system manipulation and real-time troubleshooting, which are essential skills in DevOps and Cybersecurity.

## ✅ Achievements
- [x] **Docker Engine Setup:** Installed the official Docker runtime on Server 1 and configured user privileges for seamless command execution without `sudo`.
- [x] **Nginx Web Server Deployment:** Launched an Nginx container (`ayui-web`) with port mapping (80:80) to serve as the primary web service and future testing target.
- [x] **UFW Firewall Configuration:** Successfully opened TCP ports 80 (HTTP) and 3001 (Monitoring) to allow inbound traffic while maintaining core system security.
- [x] **Host-to-Container Manipulation:** Utilized `docker cp` to overwrite the default Nginx `index.html` with a custom HTML/CSS portfolio landing page.
- [x] **Live Container Troubleshooting:** Successfully used `docker exec` to execute commands inside a running container to remove mistakenly created files and clean up the directory structure.
- [x] **Active System Monitoring:** Deployed a persistent Uptime Kuma container using Docker Volumes (`uptime-kuma-data`). Configured HTTP tracking for the Web Server and Ping tracking for the Target Node (Server 2).

## 💻 Key Commands Used
```bash
# 1. Install Docker & Configure Permissions
curl -fsSL [https://get.docker.com](https://get.docker.com) -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ayui
newgrp docker

# 2. Deploy Nginx Web Server
docker run -d -p 80:80 --name ayui-web nginx

# 3. Customizing Web Server & Troubleshooting
# Overwrite default index.html with custom portfolio page
docker cp index.html ayui-web:/usr/share/nginx/html/index.html
# Clean up misconfigured files directly inside the running container
docker exec ayui-web rm /usr/share/nginx/html.index.html

# 4. Deploy Uptime Kuma with Persistent Volume
docker volume create uptime-kuma-data
docker run -d --restart=always -p 3001:3001 -v uptime-kuma-data:/app/data --name uptime-kuma louislam/uptime-kuma:1

# 5. Configure Firewall (UFW)
sudo ufw allow 80/tcp
sudo ufw allow 3001/tcp
