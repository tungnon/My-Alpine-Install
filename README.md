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
- When asked to setup repositories: use fastest mirror
- When asked about ntp: type chrony
- When asked about disk: make sure to answer correct one and when asked how, answer sys
- Answer default if you do not know what to answer

That's it really. Reboot to your system.

## Installing our essentials
```
doas apk add micro fish fastfetch networkmanager booster 
```
Do `chsh -s /usr/bin/fish` then next time you relogin your default user shell will be fish

## Upgrading to Edge
```
doas micro /etc/apk/repositories
```
Make sure to have these
```
https://dl-cdn.alpinelinux.org/alpine/edge/main
https://dl-cdn.alpinelinux.org/alpine/edge/community
@testing https://dl-cdn.alpinelinux.org/alpine/edge/testing
```
We will treat testing repo as some sort of COPR/AUR except it's hosted on Alpine official repo. Do not blindly remove @testing in front of testing repo, your system can legit break from that.

then do
```
doas apk upgrade
```
Once it's done: reboot.

### Optional
You can also install `linux-stable` before reboot then on Limine, boot to that kernel instead if you prefer fresh new kernel

(to be continued)
