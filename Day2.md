# 🚀 Day 2: Network Stabilization, SSH Keys & Firewall Security

## 📝 Summary
Today's focus was on ensuring network stability, enabling passwordless login (SSH Keys), and strengthening basic security (Firewall) for both **Server 1** and **Server 2**.

After encountering Windows Internet Connection Sharing (ICS) issues that caused DNS errors ("Temporary failure in name resolution") and MTU packet drops, I decided to bypass the laptop and connect the servers directly to the main router (TP-Link Deco Mesh). As a result, the internet speed is now maximized, and the IP connections are incredibly stable!

## ✅ Today's Achievements
- [x] **Network Migration:** Switched the IP configuration from `<Manual>` to `<Automatic>` (DHCP) using `nmtui` and connected the LAN cables directly to the router.
- [x] **IP Tracking:** Successfully tracked the devices on the network using a combination of the router app, `ping raspberrypi.local`, and `arp -a` checks.
- [x] **SSH Key Authentication:** Injected the public key (`id_rsa.pub`) from Windows into the server's `~/.ssh/authorized_keys` file for automated, passwordless logins.
- [x] **UFW (Uncomplicated Firewall):** Installed and enabled UFW on both servers. 
- [x] **Port Security:** Ensured Port 22 (SSH) was explicitly allowed before enabling the firewall to prevent being locked out of the servers.

## 💻 Key Commands Used
**1. Network Configuration (DHCP/Auto):**
```bash
sudo nmtui
# Edit a connection -> Wired connection 1 (eth0) -> IPv4 Configuration <Automatic>

