# Kali Linux Installation on VirtualBox

## Step 1: Required Tools

- [Kali Linux for VirtualBox](https://www.kali.org/get-kali/#kali-virtual-machines)

## Step 2: Installation

1. Navigate to the folder where you downloaded the Kali Linux archive.
2. Extract the file to get the VirtualBox image, for example `Kali-Linux-2026.1-virtualbox-amd64.7z`.
3. Open VirtualBox.
4. Click New.
5. Enter a VM name, such as Kali Linux.
6. Set the operating system to Linux.
7. Set the version to Debian.

![Kali installation step 1](kali%20installation%20images/Kali-installation-step-1.png)

8. Click Specify Virtual Hardware.
9. Set the memory to 4 GB.
10. Set the CPU count to 2.
    - Note: Adjust this based on your computer’s resources.

![Kali installation step 1](kali%20installation%20images/specify-virtual%20hardware.png)

11. Click Specify Virtual Hard Disk File.
12. Select Use an Existing Virtual Hard Disk.
13. Click the folder icon on the right side of the screen.
14. Click Add.

![Kali installation step 2](kali%20installation%20images/kali-installation-step-2.png)

15. Navigate to the extracted Kali Linux files.
16. Open the folder and select the VDI file.

![Kali installation step 3](kali%20installation%20images/kali-installation-step-3.png)

17. Click Open.
18. Click Choose.
19. Kali Linux should now appear in VirtualBox.

### Login Details

- Username: Kali
- Password: Kali

With this, Kali Linux has been installed on VirtualBox.

### Alternative Method

After extracting the Kali Linux files, you can double-click the VDI file and it should open in VirtualBox automatically. Then log in with the credentials above.

