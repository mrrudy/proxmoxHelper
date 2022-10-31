# Proxmox Helper

Set of scripts to help in deployment of containers into Proxmox.

based on great work of https://github.com/tteck/Proxmox

# Kodi Media Manager LXC 

## To create a new Proxmox Kodi Media Manager, run the following in the Proxmox Shell.

```yaml
bash -c "$(wget -qLO - https://raw.githubusercontent.com/mrrudy/proxmoxHelper/main/ct/kodi-v1.sh)"
```
Kodi should be attached to TTY7 console

## To Update Kodi Media Manager:

Run in the LXC console
```yaml
apt update && apt upgrade -y
```
## Issue with X on Ubuntu 20.04 and Unprivileged

If you really need to use Ubuntu below 22.04 there is an issue with access rights that prevents Xorg from starting on TTY7 on an Unprivileged container. Workaround exists but a change on the host machine is required so please accept the risk beforehand. In the Proxmox Shell:
```yaml
chmod 660 /dev/tty7
```
