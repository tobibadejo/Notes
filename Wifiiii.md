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

