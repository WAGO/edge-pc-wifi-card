✅ 1. GitHub README (clean & professionell)
# 📶 Setup Wi-Fi on Edge PC

Follow these steps to configure and enable Wi-Fi on your Edge PC.

## Prerequisites
- Wi-Fi card is physically installed in the Edge PC

---

## Using Cockpit UI (Recommended)

1. Open the **Cockpit Web Interface**
2. Open the **Terminal** from the sidebar

### Scan and connect to Wi-Fi

```bash
nmcli device wifi rescan

Scans for available Wi-Fi networks

nmcli device wifi list

Lists all detected Wi-Fi networks

nmcli device wifi connect YOUR-WIFI password YOUR-PASSWORD

Connects to the selected Wi-Fi network

Configure Network Settings

After connecting:

Go to Networking
Select the Wi-Fi adapter
Configure:
Static IP
Gateway
DNS

Use this for manual configuration instead of DHCP.

Alternative: Manual Setup via Terminal

If the connection fails, configure it manually:

nmcli device wifi list
nmcli dev status

Shows networks and device status

nmcli connection add type wifi ifname wlan0 ssid YOUR-WIFI

Creates a Wi-Fi connection profile

nmcli connection edit wifi-wlan0

Opens interactive configuration

Configure Wi-Fi
goto wifi
set mode infrastructure
set ssid YOUR-WIFI
back
Configure Security
goto wifi-sec
set key-mgmt wpa-psk
set psk YOUR-PASSWORD
back
save
quit

Save and exit

Final Steps
nmcli radio wifi on
systemctl restart NetworkManager

Enable Wi-Fi and restart network service

✅ Done

Your Edge PC should now be connected to Wi-Fi.


---

# 🚀 2. Advanced Version (für Doku-Tools wie MkDocs / Docusaurus)

👉 Mit Tabs + besserer UX (funktioniert NICHT nativ auf :contentReference[oaicite:0]{index=0}, aber z. B. mit :contentReference[oaicite:1]{index=1} + Material Theme)

```markdown
# 📶 Setup Wi-Fi on Edge PC

## Prerequisites
- Installed Wi-Fi card

---

## Setup Methods

=== "Cockpit UI (Recommended)"

    1. Open Cockpit Web UI
    2. Open Terminal

    ```bash
    nmcli device wifi rescan
    nmcli device wifi list
    nmcli device wifi connect YOUR-WIFI password YOUR-PASSWORD
    ```

    Then configure network settings in **Networking**:
    - Static IP
    - Gateway
    - DNS

=== "Manual (Terminal)"

    ```bash
    nmcli device wifi list
    nmcli dev status
    nmcli connection add type wifi ifname wlan0 ssid YOUR-WIFI
    nmcli connection edit wifi-wlan0
    ```

    Configure:

    ```bash
    goto wifi
    set mode infrastructure
    set ssid YOUR-WIFI
    ```

    ```bash
    goto wifi-sec
    set key-mgmt wpa-psk
    set psk YOUR-PASSWORD
    ```

    ```bash
    save
    quit
    ```

    ```bash
    nmcli radio wifi on
    systemctl restart NetworkManager
    ```

---

## ✅ Result

Wi-Fi is configured and active.
