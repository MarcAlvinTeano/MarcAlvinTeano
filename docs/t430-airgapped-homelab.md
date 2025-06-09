## 🔧 Proxmox VE 8.4 Standalone Installation (ZFS RAID1, Airgapped Ready)

### 🗓️ Date:
June 09, 2025

### 🖥️ Hardware:
- Dell PowerEdge T430  
- 2x 1TB SSDs (ZFS mirror)  
- PERC H730 RAID controller (configured with 2x RAID0 virtual disks)  
- USB keyboard/mouse and monitor  
- Airgapped lab environment (no internet access)

---

### 🛠️ Installation Summary:
- Proxmox VE 8.4 ISO flashed to USB  
- BIOS boot override used to launch installer  
- Accepted EULA and entered graphical installer  
- Selected both 1TB SSDs configured as separate RAID0 volumes on PERC H730  
- Configured ZFS mirror (RAID1) at installer disk selection  
- Skipped enterprise repo for now  
- Static network config:  
  - Hostname: `core.pve.malac.local`  
  - IP: `192.168.100.2/24`  
  - Gateway/DNS: `192.168.100.1`  
- Successful first boot confirmed via terminal  
- Verified ZFS pool with `zpool status`

---

### 📁 ISO Bank (Local Repository):
- `debian-live-12.11.0-amd64-standard.iso`  
- `debian-live-12.11.0-amd64-xfce.iso`  
- `ubuntu-22.04.5-live-server-amd64.iso`  
- `Rocky-9.6-x86_64-dvd.iso`  
- `kali-linux-2025.1c-installer-amd64.iso`  
- `securityonion-2.4.150-20250522.iso`

---

### 🛫 Offline Package Loadout:
All `.deb` packages downloaded and verified for offline GUI install, monitoring, file systems, net-tools, security, and scripting.  
Includes:
- XFCE, Firefox, Thunar, Mousepad  
- `htop`, `iotop`, `ncdu`, `tmux`, `screen`  
- `nmap`, `traceroute`, `curl`, `wget`, `git`  
- `zfsutils-linux`, `exfatprogs`, `parted`, `net-tools`  
- GnuPG full chain, `chkrootkit`, `rkhunter`, `lynis`, etc.

---

### 🔢 Install Script:
Created `install_all_debs.sh` for repeatable, logged offline installation of `.deb` files in batch mode.

---

### ✅ Status:
> Proxmox VE operational with mirrored ZFS root, offline-ready package bank, and ISO vault. Ready for VM provisioning and GUI enhancement.

---

### 📄 Screenshots (not included here):
- BIOS boot menu  
- PERC H730 config screen  
- Proxmox ZFS mirror selection  
- Final install summary screen  
- Console login with IP and ZFS pool status
