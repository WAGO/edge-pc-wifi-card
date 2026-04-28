# edge-pc-wifi-card
Set up the Wi-Fi adapter and enable wireless connectivity on the Edge PC

📶 Setup Wi-Fi on Edge PC

Follow these steps to configure and enable Wi-Fi on your Edge PC.

Prerequisites
Wi-Fi card is physically installed in the Edge PC
Using Cockpit UI (Recommended)
Open the Cockpit Web Interface
Go to the sidebar and open the Terminal

Run the following commands:

nmcli device wifi rescan

**** Scans for available Wi-Fi networks

nmcli device wifi list

**** Lists all detected Wi-Fi networks

nmcli device wifi connect YOUR-WIFI password YOUR-PASSWORD

**** Connects to the selected Wi-Fi network

Configure Network Settings

After connecting:

Go to Networking section in Cockpit
Select the Wi-Fi adapter
Configure settings like:
Static IP
Gateway / Router
DNS

**** Use this if you need manual network configuration instead of DHCP

Alternative: Full Configuration via Terminal

If the connection fails, you can configure everything manually:

nmcli device wifi list

**** Shows available Wi-Fi networks

nmcli dev status

**** Displays device status and interface names

nmcli connection add type wifi ifname wlan0 ssid YOUR-WIFI

**** Creates a new Wi-Fi connection profile

nmcli connection edit wifi-wlan0

**** Opens interactive editor for configuration

Inside the interactive editor:
goto wifi
set mode infrastructure
set ssid YOUR-WIFI
back

**** Sets Wi-Fi mode and SSID

goto wifi-sec
set key-mgmt wpa-psk
set psk YOUR-PASSWORD
back

**** Configures Wi-Fi security and password

save
quit

**** Saves configuration and exits editor

Final Steps
nmcli radio wifi on

**** Enables Wi-Fi radio

systemctl restart NetworkManager

**** Restarts the network service to apply changes

✅ Done

Your Edge PC should now be connected to Wi-Fi.
