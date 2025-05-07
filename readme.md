# magic mirror

## setup

```sh
xzcat 2024-11-19-raspios-bookworm-armhf-lite.img.xz | sudo dd of=/dev/mmcblk0 bs=64k oflag=dsync status=progress
sudo raspi-config # ssh, timezone, overclock config
sudo apt-get update
sudo apt full-upgrade
sudo apt-get install -y git vim
mkdir git
cd git
git clone https://github.com/trevorbox/MagicMirror.git
cd MagicMirror
npm run install-mm
```

setup pm2

```sh
# https://docs.magicmirror.builders/configuration/autostart.html#starting-your-magicmirror2-with-pm2
vim ~/mm.sh
# cd ./git/MagicMirror
# DISPLAY=:0 npm run server
chmod +x ~/mm.sh
pm2 start mm.sh
pm2 save
pm2 logs mm
pm2 show mm
```

## start

```sh
npm run install-mm
npm run server
```

## calendar module

```sh
git submodule add https://github.com/kolbyjack/MMM-MonthlyCalendar.git modules/MMM-MonthlyCalendar
git submodule add https://github.com/jalibu/MMM-RAIN-MAP modules/MMM-RAIN-MAP
# git submodule add https://github.com/hermanho/MMM-GooglePhotos.git modules/MMM-GooglePhotos
git submodule update --init --recursive
```
