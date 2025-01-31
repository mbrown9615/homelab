# homelab
This is a repo I will use to share config files and so forth.

## Proxmox server build

This was my introduction to homelabing.


### Hardware
  
  I used my old gaming pc as a the base for my server. 

  * Asus motherboard
  * i5 5500k cpu
  * 970 GTX
  * 850w PSU
  * as well as 4 shucked (8TB) HDD's

### Services

  * Ubuntu server (Nextcloud, Jellyfin, Docker) with the GPU passed through for hardware encoding
  * Kali Linux VM to play with some hacking labs
  * Truenas scale VM passing through the HDD's to set up a pool

### NextCloud

  This was my fist experience with nextcloud, I ended up spinning up a VM in Linode with a free trial. I bought a domain, and used cloudflare.

  In the future I plan on creating a cloud storage that is accessable through VPN


## Setting up a Kubernetes cluster with referbished laptops

## Hardware

  (1) Dell Precision 6700
  (3) HP Probook 640 G5
        4 core i5-8365U 
        16Gb Ram
        500Gb NVME

  
### Configuring the Laptops

  Install Ubuntu server on all laptops. I started by first changing the bios settings to suit linux. I dissabled secure boot and enabled legacy boot. While testing I did run into an issue where Linux couldn't detect the nvme drive. To get around this I flashed Windows onto the laptop and followed these steps:

  * Run cmd as admin
  * bcdedit /set safeboot minimal
  * reboot into bios
  * Change SATA operations mode to AHCI from RAID
  * Save and exit
  * Boot back into Windows
  * Run cmd as admin
  * bcdedit /delevalue safeboot
  * Now Linux should detect the drive

  Because I'm running this cluster on laptops, I would like them to function with the lid closed and not go to sleep, but still have the screen sleep so it's not on 24/7.
  
  * Edit /etc/systemd/logind.conf
  * HandleSuspendKey=ignore
  * HandleLidSwitch=ignore
  * HandleSwitchDocked=ignore
  * sudo systemctl restart systemd-logind





