# Hyprland-Dots
Required downloads:

1. Hyprland
2. Kitty
3. Wofi
4. Dolphin
5. Waybar
6. Hyprpaper
7. Neovim
8. ttf-jetbrains-mono
9. otf-font-awesome

10. Nvidia-open
11. Nvidia-utils
12. Lib32-nvidia-utils
13. egl-wayland
14. libva-nvidia-driver

sudo pacman -S hyprland kitty wofi dolphin waybar hyprpaper neovim ttf-jetbrains-mono otf-font-awesome nvidia-open nvidia-utils lib32-nvidia-utils egl-wayland libva-nvidia-driver

Nvidia:

1. Edit /etc/mkinitcpio.conf. In the MODULES array, add the following module names: MODULES=(... nvidia nvidia_modeset nvidia_uvm nvidia_drm ...)
2. Then, create and edit /etc/modprobe.d/nvidia.conf. Add this line to the file: options nvidia_drm modeset=1 fbdev=1
3. Lastly, rebuild the initramfs with sudo mkinitcpio -P, and reboot.
4. To verify that DRM is actually enabled, run cat /sys/module/nvidia_drm/parameters/modeset which should return Y.
