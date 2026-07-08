# pfSense Firewall Installation

This guide walks you through installing pfSense in VirtualBox with recommended VM settings for a home lab.

Requirements

- pfSense ISO: https://pfsense.com/download/
- VirtualBox: https://www.virtualbox.org/wiki/Downloads

Quick steps

1. In VirtualBox click New and create a VM named `pfsense-firewall`.
   - Type: BSD
   - Version: FreeBSD (64-bit) or select the closest BSD option
   - Memory: 1 GB (minimum)
   - CPUs: 2
   - Disk: 20 GB or larger
2. Attach the downloaded pfSense ISO to the VM (Settings → Storage → Controller: IDE → Add Optical Drive).
3. Start the VM and follow the installer prompts. When asked to remove the ISO after install, unmount/eject the installer image before rebooting.

Notes & troubleshooting

- Interface names in VirtualBox (em0/em1) are assigned inside pfSense — choose the WAN interface and the LAN interface as prompted.
- If you see DHCP incorrectly spelled or other UI wording, look for the DHCP client option when configuring the WAN.

Images used in this guide are in the repository under the original images directory. If you cannot see them here, open the images in the repo browser.

