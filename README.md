# INSTALL LINUX STARTER PACK
I prefer my Linux to be an Arch-based distro or Arch Linux itself so, if you use Ubuntu, you could search up other guidance rather than mine. But still, there are some universal stuff you could get if you do read the whole paragraph. Cheers.

LANGUAGE:
>- [🇮🇩 ID](./README.id.md)
>- [🇺🇸 EN](./README.md)

# Quick Links to My Rices
>- [bspwm](https://github.com/JavaneseBoi/404)
>- [qtile](https://github.com/JavaneseBoi/404)
>- [KDE/Plasma](https://github.com/JavaneseBoi/404)
>- [Dwm](https://github.com/JavaneseBoi/404)
>- [Xmonad](https://github.com/JavaneseBoi/404)
>- [linuxSidra](https://github.com/JavaneseBoi/404)
>- [polybar](https://github.com/JavaneseBoi/404)
>- [oh my zsh](https://github.com/JavaneseBoi/404)
>- [alacritty](https://github.com/JavaneseBoi/404)
>- [firefox](https://github.com/JavaneseBoi/404)

# Table of Contents
>- [Overview](#overview)
>- [Arch installation](#arch-installation)
>- [Login and window manager](#login-and-window-manager)
>- [Basic system utilities](#basic-system-utilities)
>  - [Wallpaper](#wallpaper)
>  - [Fonts](#fonts)
>  - [Audio](#audio)
>  - [Monitors](#monitors)
>  - [Storage](#storage)
>  - [Network](#network)
>  - [Systray](#systray)
>  - [Notifications](#notifications)
>  - [Xprofile](#xprofile)
>- [Further configuration and tools](#further-configuration-and-tools)
>  - [AUR helper](#aur-helper)
>  - [Media Transfer Protocol](#media-transfer-protocol)
>  - [File Manager](#file-manager)
>  - [Trash](#trash)
>  - [GTK Theming](#gtk-theming)
>  - [Qt](#qt)
>  - [Lightdm theming](#lightdm-theming)
>  - [Multimedia](#multimedia)
>    - [Images](#images)
>    - [Video and audio](#video-and-audio)
>  - [Start Hacking](#start-hacking)
>- [Gallery](#gallery)
>  - [Qtile](#qtile)
>  - [Spectrwm](#spectrwm)
>  - [Openbox](#openbox)
>  - [Xmonad](#xmonad)
>  - [Dwm](#dwm)
>- [Keybindings](#keybindings)
>  - [Windows](#windows)
>  - [Apps](#apps)
>- [Software](#software)
>  - [Basic utilities](#basic-utilities)
>  - [Fonts, theming and GTK](#fonts-theming-and-gtk)
>  - [Apps](#apps-1)

What-to-do-after-installing-Arch-Linux.sh is to update your lovely Arch
`
sudo pacman -Syu
sudo reboot
`


What-to-do-after-installing-Arch-Linux-2.sh
`
#!/bin/bash
# set as root
su

# install app you need 
pacman -S ntp firefox telegram-desktop git gimp libreoffice-still pcmanfm 7-zip vlc libmtp lightdm-webkit2-greeter alacritty geeqie nitrogen pulseaudio pavucontrol arandr network-manager-applet udiskie ntfs-3g libnotify notification-daemon volumeicon cbatticon xorg-xinit rofi picom zsh

# install AUR helper
cd /opt/
sudo git clone https://aur.archlinux.org/yay-git.git
sudo chown -R shitdra:shitdra yay-git/
cd yay-git
makepkg -si
cd

# install app from AUR
yay -S discord-ptb brave simple-mtpfs visual-studio-code-bin lightdm-webkit-theme-aether

# set your time to match ntp. timedatectl set-ntp bool
timedatectl set-ntp true
`



Run these Manually
`
# set firefox profile 
firefox --ProfileManager

# Change your GTK theme
# Fonts, I'mma add my fonts to github. My fonts: System San Francisco, Iosevka, Material Design
yay -S ttf-yosemite-san-francisco-font-git ttf-iosevka ttf-dejavu ttf-liberation noto-fonts
# git clone https://github.com/JavaneseBoi/linuxSidra/fonts
# Icons

# Change your Qt theme, #FYI, GTK themes ain't applied to Qt applications, mate.
`

Config Manually
`
# 1. Config lightdm
/etc/lightdm/lightdm.conf
[Seat:*]
# ...
# Uncomment this line and set this value
greeter-session = lightdm-webkit2-greeter
# ...

# /etc/lightdm/lightdm-webkit2-greeter.conf
[greeter]
# ...
webkit_theme = lightdm-webkit-theme-aether


# 2. Config Alacritty

# 3. Config Xprofile for systemtray
touch ~/.xprofile
xrandr
#copy your xrandr output (Ctrl+Shift+C is to copy in terminal)
xrandr --output SEARCHING PLEASE I HAVEN'T FIX THIS SHIT  &
setxkbmap id &
nm-applet &
udiskie -t &
volumeicon &
cbatticon &

# 4. Change your shell if you want, I use zsh. Aint't forget to download p10k and config it
chsh /bin/zsh
p10k configure
`
