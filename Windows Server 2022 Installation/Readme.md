# Windows Server 2022 Installation

## Description

Windows Server 2022 is an important part of this home lab. It helps simulate an enterprise environment, and Active Directory is one of the many features you can install and test on this server.

## Requirements

- [Windows Server 2022 ISO](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)
  - Download the LTSC version if needed.

## Installation

1. Launch VirtualBox.
2. Click New.

![Launch VirtualBox](/windows%2011%20client%20pc%20Installation/images/launch-virtual-box.png)

### Virtual Machine Name and OS

- Enter a name for the virtual machine, for example Win-Serv-2022.
- Leave the VM folder at the default setting.
- Select the Windows Server 2022 ISO you downloaded.
- Leave unattended install unchecked unless you specifically want it enabled.

![VM name](/Windows%20Server%202022%20Installation/images/win-server-vm-name.png)

### Specify Virtual Hardware

- Set the base memory (RAM) to 6 GB.
- Set the CPU to 2 cores.


![Starting the machine](/Windows%20Server%202022%20Installation/images/win-server-ram.png)

### Specify Virtual Hard Disk

- Set the disk size to 80 GB or more.

![VM name](/Windows%20Server%202022%20Installation/images/win-server-storage.png)

- Click Finish. You should see the VM in the VirtualBox manager.
- Click Start.



- While the machine is starting, pay attention and press any key to boot from the CD/DVD.
