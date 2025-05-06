# magic mirror

## setup

```sh
xzcat 2024-11-19-raspios-bookworm-armhf-lite.img.xz | sudo dd of=/dev/mmcblk0 bs=64k oflag=dsync status=progress
sudo raspi-config # ssh, timezone, overclock config
sudo apt-get update
sudo apt full-upgrade
sudo apt-get install -y git
# https://docs.docker.com/engine/install/raspberry-pi-os/
```

## start

```sh
npm run install-mm
npm run start
```

## calendar module

```sh
git submodule add https://github.com/kolbyjack/MMM-MonthlyCalendar.git modules/MMM-MonthlyCalendar
git submodule add https://github.com/jalibu/MMM-RAIN-MAP modules/MMM-RAIN-MAP
# git submodule add https://github.com/hermanho/MMM-GooglePhotos.git modules/MMM-GooglePhotos
git submodule update --init --recursive
```
