# Kali Linux installation on VirtualBox

## Step 1: Required Tools

- Kali Linux for VirtualBox: https://www.kali.org/get-kali/#kali-virtual-machines
- VirtualBox (latest version recommended): https://www.virtualbox.org/wiki/Downloads

## Step 2: Installation (import a prebuilt VirtualBox appliance)

1. Download the Kali VirtualBox archive (example file: `Kali-Linux-2026.1-virtualbox-amd64.7z`) and extract it.
2. Start VirtualBox and click `File → Import Appliance` if an OVA/OVF was provided, or click `New` to create a VM and choose `Use an existing virtual hard disk file` to select the extracted `.vdi`.
3. When creating a new VM manually:
   - Name: `kali-linux` (or any name you prefer)
   - Type: `Linux`
   - Version: `Debian (64-bit)`
   - Memory: 4 GB (adjust to your host capacity)
   - CPUs: 2

4. To use an existing VDI: choose `Use an existing virtual hard disk file`, click the folder icon → `Add` → select the `.vdi` file → `Choose`.

![Kali Installation Step 1](/kali-linux-installation/kali-installation-images/Kali-installation-step-1.png)

### Login details and security

Some prebuilt images include example accounts for convenience. If the image you downloaded ships with a default account (for example, `kali` / `kali`), treat it as a temporary test account only:

- DO NOT leave default credentials in place on machines connected to any network you do not control.
- Immediately change any default password after first login.

If you prefer to install from ISO instead of importing a prebuilt VM, download the Kali ISO and install as you would any Debian-based distribution.

### Notes

- Performance settings (memory, CPU) depend on your host machine. If you run multiple VMs, increase host RAM/CPU as needed.
- If you encounter kernel/module compatibility issues with VirtualBox, update VirtualBox Guest Additions or use the official Kali VirtualBox images from the Kali downloads page.

