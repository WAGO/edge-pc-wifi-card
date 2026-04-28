📶 Setup Wi-Fi on Edge PC

Follow these steps to configure and enable Wi-Fi on your Edge PC.
---
Prerequisites
Wi-Fi card is physically installed in the Edge PC
Using Cockpit UI (Recommended)
Open the Cockpit Web Interface
Go to the sidebar and open the Terminal

Run the following commands:
```bash
nmcli device wifi rescan
```
**** Scans for available Wi-Fi networks
```bash
nmcli device wifi list
```
**** Lists all detected Wi-Fi networks
```bash
nmcli device wifi connect YOUR-WIFI password YOUR-PASSWORD
```
**** Connects to the selected Wi-Fi network
---
