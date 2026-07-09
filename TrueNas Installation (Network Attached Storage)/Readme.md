# TrueNAS Installation

![TrueNAS](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-4.png)

## Description

TrueNAS is a centralized storage solution that allows you to share and store files on the network.

## Requirements

Download it from the official site:

- [TrueNAS ISO](https://www.truenas.com/download/)

Or from OSboxes:

- [TrueNAS ISO for VirtualBox](https://www.osboxes.org/truenas/)

This guide uses the OSboxes image.

## Installation

1. Launch VirtualBox.
2. Click New.

### Virtual Machine Name and OS

- Enter a name for the virtual machine, for example TrueNAS.
- Leave the VM folder at the default setting.
- Set the OS type to BSD.

![VM name](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image.png)

### Specify Virtual Hardware

- Set the base memory (RAM) to 2 GB.
- Set the CPU to 1 core.

![Base memory](/PFsense%20Firewall%20Installation/images/base-memory.png)

### Virtual Hard Disk

- Select Use an Existing Virtual Hard Disk File.
- Click the folder icon on the right side of the screen.
- Click Add.

![Virtual hard disk](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/Existing-vdi.png)

- Navigate to the extracted TrueNAS files.
- Click Open.
- Click Choose.

![Selection screen](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-1.png)

- Click Finish. You should see the VM in the VirtualBox manager.
- Click Settings.

![Finished VM](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-2.png)

- Click Network.
- Click Adapter 1.
- Change Attached to to Internal Network.
- Enter the same internal network name you used for pfSense.

![Network adapter](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-3.png)

- Click OK.
- Click Start.

### Done

![Installation complete](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-5.png)

To access this NAS, use a system that is connected to the same internal network.