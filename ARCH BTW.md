Caelestia shell (hyprland plus quickshell)

==**important configs**==

Keybinds: ~/.config/hypr/hyprland/keybinds.conf

Display manager: /usr/share/sddm/themes/sddm-astronaut-theme/metadata.desktop

Links to all caelestia configs: ~/.config/hypr/hyprland.conf

==**GitHub repos**

Caelestia https://github.com/caelestia-dots/caelestia
SDDM themes: https://github.com/Keyitdev/sddm-astronaut-theme/tree/master

==Updating

To update caelestia: cd ~/.local/share/caelestia then git pull

==External hard drive mounting issues

To see exact path
sudo fdisk -l

to manually mount
sudo mkdir -p /mnt/sda3
sudo mount -t ntfs-3g /dev/sda3 /mnt/sda3

==Formating flash drive

gnome-disks


==Wifi hotspot

https://wiki.archlinux.org/title/Software_access_point

for setting up a virtual interface to allow wifi to be used simultaneously with hotspot 
/etc/systemd/system/create-virtual-interface.service

==Github for syncing obsidian

https://github.com/tobibadejo/Notes

==WORDLIST

https://disk.yandex.ru/d/1spMBmxcEnN95g for rockyou 2024
