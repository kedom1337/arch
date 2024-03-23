> [!NOTE]
>
> These packages are inteded to complement an install made with [archinstall](https://github.com/archlinux/archinstall)
> using btrfs and the KDE Plasma 6 desktop preset

## Installation
Enable color and parallel downloads for pacman (optional)

`sed -i '/Color/s/^#//g' /etc/pacman.conf`

`sed -i '/ParallelDownloads/s/^#//g' /etc/pacman.conf`

Update and install pacman packages

`pacman -Syyu && pacman -S --needed - < ./paclist.txt`

Install yay

`pacman -S --needed base-devel && git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si && cd .. && rm -rf yay`

Install yay packages

`yay -S --needed - < ./aurlist.txt`

Enable system services/timers

`systemctl enable avahi-daemon`

`systemctl enable cups`

`systemctl enable firewalld`

`systemctl enable reflector.timer`
