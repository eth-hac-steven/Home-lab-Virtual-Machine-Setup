# TrueNAS Installation (Network Attached Storage)

This guide demonstrates how to add a TrueNAS VM to your VirtualBox home lab using an existing VDI or ISO.

Requirements

- TrueNAS ISO: https://www.truenas.com/download/ or prebuilt VDI from OSBoxes
- VirtualBox

Recommended VM settings

- Type: BSD
- Memory: 2 GB (more for production/test loads)
- CPUs: 1+ (depending on host)
- Disk: use an existing VDI or create a dedicated virtual disk

Quick steps

1. In VirtualBox click New → name the VM (e.g., `truenas`) and set OS type to BSD.
2. Attach an existing VDI (if using OSBoxes) or attach the TrueNAS ISO to install.
3. Configure network: Attached to: Internal Network and use the same internal network name used by pfSense.
4. Start the VM and follow the TrueNAS installer or boot into the prebuilt image.

Access

- After installation, access the TrueNAS web UI from a system on the same internal network using the IP address assigned to the TrueNAS VM.

Notes

- For production-like testing, increase memory and CPU. TrueNAS benefits from more RAM.

