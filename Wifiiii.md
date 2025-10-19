==Commands used:

! See interfaces 
ip addr iwconfig

!kill processes 
sudo airmon-ng check kill

!Start monitor mode
sudo airmon-ng start wlan0

!Verify that monitor mode is used
sudo airmon-ng

!You could also use iwconfig to check that interface is in monitor mode
iwconfig

! Get the AP's MAC address and channel
sudo airodump-ng wlan0mon

! AP-MAC & channel - you need to select your own here:
ESSID: 90:9A:4A:B8:F3:FB
Channel used by AP for SSID: 2

!1st Window:
!Make sure you replace the channel number and bssid with your own
