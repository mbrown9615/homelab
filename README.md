# homelab
This is a repo I will use to share config files and so forth.


## Setting up a Kubernetes cluster with referbished laptops

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

  


