# 🚀 Day 4: Secondary Server Setup & Inter-Server Communication

## 📝 Summary
The objective for today was to finalize the setup for Server 2 (Target/Testing Node) and establish a secure, passwordless communication bridge from Server 1 (Main Infrastructure). This architecture is critical for simulating real-world enterprise environments and future Red/Blue team exercises.

## ✅ Achievements
- [x] **Static IP Configuration:** Assigned a persistent static IP to Server 2 (`192.168.xx.xxx`) ensuring consistent connectivity for future network scanning and lab testing.
- [x] **Storage Provisioning:** Replicated the external SSD configuration on Server 2, including the UASP hardware bypass in `cmdline.txt`, `ext4` formatting, and `/etc/fstab` auto-mounting.
- [x] **SSH Key Authentication:** Generated a 4096-bit RSA key pair on Server 1 to serve as the master control node.
- [x] **Passwordless Access:** Authorized Server 1's public key on Server 2 using `ssh-copy-id`. Successfully verified direct SSH access from Server 1 to Server 2 without password prompts, paving the way for seamless automation.

## 💻 Key Commands Used
```bash
# Generate RSA SSH Key on Server 1 (Master)
ssh-keygen -t rsa -b 4096

# Install public key onto Server 2 (Target)
ssh-copy-id ayui@<SERVER2_IP>

# Verify passwordless entry
ssh ayui@<SERVER2_IP>
