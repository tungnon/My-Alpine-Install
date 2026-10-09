# My-Alpine-Install
An opinionated way to install Umbriel + Noctalia on Alpine Linux for desktop use

## Goal
This aims to setup Alpine Linux edge with Umbriel and Noctalia on ext4 root partition.

## Setup-Alpine
Setup-Alpine already offers absurdly minimal install. You don't need to do it manually. Here's what I used:
```
BOOTLOADER=limine setup-alpine
```
If you don't want swap partition. You can do:
```
BOOTLOADER=limine SWAP_SIZE=0 setup-alpine
```
Answer what it says. But here are the important stuff:
- When asked to setup repositories: use fastest mirror. Then change from 3.2X to Edge
- When asked about ntp: type chrony
- When asked about disk: type sys to install Alpine on your SSD
- Answer default if you do not know what to answer
That's it really. Reboot to your system.

## Installing our essentials
```
doas apk add micro fish fastfetch networkmanager booster
```
(to be continued)

