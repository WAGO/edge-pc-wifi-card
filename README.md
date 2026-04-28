# 📶 Setup Wi-Fi on Edge PC

Follow these steps to configure and enable Wi-Fi on your Edge PC.

---

## ✅ Prerequisites

- Wi-Fi card is physically installed in the Edge PC

---

## 🖥️ Using Cockpit UI (Recommended)

1. Open the **Cockpit Web Interface** (http://IP-EDGE:9090)
   
3. Open the **Terminal** via the sidebar

### Scan and Connect to Wi-Fi

```bash
nmcli device wifi rescan
```
Scans for available Wi-Fi networks
```bash
nmcli device wifi list
```
Lists all detected Wi-Fi networks
```bash
nmcli device wifi connect YOUR-WIFI password YOUR-PASSWORD
```
Connects to the selected Wi-Fi network

### 🌐 Configure Network Settings

After connecting:

- Open **Networking** in Cockpit  
- Select the **Wi-Fi adapter**  
- Configure:
  - Static IP  
  - Gateway / Router  
  - DNS  

Use this if you need manual network configuration instead of DHCP.
Use this if you need manual network configuration instead of DHCP.
---
### ⚙️ Alternative: Full Configuration via Terminal

If the connection fails, configure everything manually:
```bash
nmcli device wifi list
```
Shows available Wi-Fi networks
```bash
nmcli dev status
```
Displays device status and interface names
```bash
nmcli connection add type wifi ifname wlan0 ssid YOUR-WIFI
```
Creates a new Wi-Fi connection profile
```bash
nmcli connection edit wifi-wlan0
```
Opens interactive editor for configuration

Inside the Interactive Editor
```bash
goto wifi
set mode infrastructure
set ssid YOUR-WIFI
back
```

Sets Wi-Fi mode and SSID
```bash
goto wifi-sec
set key-mgmt wpa-psk
set psk YOUR-PASSWORD
back
```
Configures Wi-Fi security and password
```bash
save
quit
```
Saves configuration and exits editor
---
### 🔄 Final Steps
```bash
nmcli radio wifi on
```
Enables Wi-Fi radio
```bash
systemctl restart NetworkManager
```
Restarts the network service to apply changes
---
### ✅ Done

Your Edge PC should now be connected to Wi-Fi.

