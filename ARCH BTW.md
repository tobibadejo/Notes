Caelestia shell (hyprland plus quickshell)

==**important configs**==

Keybinds: ~/.config/hypr/hyprland/keybinds.conf

Display manager: /usr/share/sddm/themes/sddm-astronaut-theme/metadata.desktop

Links to all caelestia configs: ~/.config/hypr/hyprland.conf

https://wiki.hypr.land/Configuring/Variables/#input

==Connecting to wifi

sudo nmcli device wifi connect CSIS_EIE_WIFI pasword 12345678 (not sure thoo)

==**GitHub repos**

Caelestia https://github.com/caelestia-dots/caelestia
SDDM themes: https://github.com/Keyitdev/sddm-astronaut-theme/tree/master

==Updating

To update caelestia: cd ~/.local/share/caelestia then git pull

==Mounting windows partition

sudo mkdir -p /mnt/windows
sudo mount -t ntfs3 -o ro /dev/nvme1n1p2 /mnt/windows
ls /mnt/windows/Users/Tobi

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

==Things you should probably do 

https://www.reddit.com/r/archlinux/comments/1o5kmrw/things_you_probably_should_do/

# Material colours
    primary_scheme = get_scheme(scheme.variant)(primary, not light, 0)
    if hasattr(MaterialDynamicColors, "all_colors"):  # materialyoucolor-python >= 3.0.0
        dyn_colours = MaterialDynamicColors()
        for colour in dyn_colours.all_colors:
            colours[colour.name] = colour.get_hct(primary_scheme)
    else:
        for colour in vars(MaterialDynamicColors).keys():
            colour_name = getattr(MaterialDynamicColors, colour)
            if hasattr(colour_name, "get_hct"):
                colours[colour] = colour_name.get_hct(primary_scheme)



    # Harmonize terminal colours
    for i, hct in enumerate(light_gruvbox if light else dark_gruvbox):
        if scheme.variant == "monochrome":
            colours[f"term{i}"] = grayscale(hct, light)
        else:
            colours[f"term{i}"] = harmonize(
                hct, colours["primary_paletteKeyColor"], (0.35 if i < 8 else 0.2) * (-1 if light else 1)
            )