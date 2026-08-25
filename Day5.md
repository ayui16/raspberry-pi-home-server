# 🚀 Day 5: Containerization & Docker Web Server Deployment

## 📝 Summary
The objective for today was to introduce containerization technology using Docker on Server 1. Running services inside isolated containers instead of directly on the host OS is an industry-standard best practice for security, resource efficiency, and scalability.

## ✅ Achievements
- [x] **Docker Engine Setup:** Downloaded and installed the official Docker engine on Server 1.
- [x] **Privilege Management:** Configured user permissions by adding the primary user (`ayui`) to the `docker` group, allowing container management without `sudo`.
- [x] **Container Lifecycle Test:** Successfully executed the `hello-world` test container to verify the container runtime environment.
- [x] **Nginx Web Server Deployment:** Deployed an official Nginx web server inside a detached container named `web-main`, mapping host port 80 to container port 80.
- [x] **Verification:** Confirmed public accessibility by browsing the server's static IP and validating the default "Welcome to nginx!" landing page.

## 💻 Key Commands Used
```bash
# Install Docker
curl -fsSL [https://get.docker.com](https://get.docker.com) -o get-docker.sh
sudo sh get-docker.sh

# Add user to docker group & refresh group session
sudo usermod -aG docker ayui
newgrp docker

# Run Nginx Web Server Container in background (detached mode)
docker run -d -p 80:80 --name ayui-web nginx
