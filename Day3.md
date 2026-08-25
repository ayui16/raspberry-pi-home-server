### 🚀 Day 3: External Storage Setup & UASP Troubleshooting
**Goal:** Configure, format, and establish persistent auto-mounting for the external SSD.
* **Storage Inspection:** Temporarily mounted the drive to inspect the existing `exfat` filesystem, ensuring no critical data was lost before wiping.
* **Filesystem Formatting:** Formatted the 447GB SSD to `ext4` for optimal Linux performance, reliability, and permission management.
* **Persistent Mounting (Auto-mount):** Configured the `/etc/fstab` file using the drive's unique UUID. Added the `nofail` parameter to ensure the server can still boot safely even if the drive is disconnected.
* **Permissions & Testing:** Assigned ownership of the mount point (`/mnt/ssd`) to the primary user (`ayui`) and successfully conducted read/write storage tests.

**🎯 Challenges & Solutions:**
* **Challenge:** The formatting process (`mkfs.ext4`) froze indefinitely at the "Creating journal" stage. Diagnosed this as a known UASP (USB Attached SCSI Protocol) hardware conflict between the Raspberry Pi's USB 3.0 controller and the Netac SSD controller (`0dd8:0562`).
* **Solution:** Bypassed the UASP protocol specifically for this drive by appending a USB storage quirk (`usb-storage.quirks=0dd8:0562:u`) to the `/boot/firmware/cmdline.txt` file. After a hard reboot, the formatting completed smoothly in seconds.

**💻 Key Commands Used:**
```bash
# UASP Quirk Fix (Appended to the end of the line)
sudo nano /boot/firmware/cmdline.txt # Added: usb-storage.quirks=0dd8:0562:u

# Formatting and Mounting
sudo mkfs.ext4 /dev/sda1
sudo mkdir -p /mnt/ssd
sudo mount /dev/sda1 /mnt/ssd
sudo chown -R ayui:ayui /mnt/ssd

# Auto-mount (fstab configuration)
echo 'UUID=a4f2fa78-35d6-4174-8e2a-cb5ca8f6362e /mnt/ssd ext4 defaults,noatime,nofail 0 2' | sudo tee -a /etc/fstab
