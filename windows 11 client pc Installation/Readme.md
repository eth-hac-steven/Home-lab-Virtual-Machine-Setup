# Windows 11 Client Installation

## Description

The Windows 11 client system is an important VM for this homelab. It allows you to simulate a user’s view of the network and provides a safe environment for testing and troubleshooting.

## Requirements

- [Windows 11 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)
  - Download the LTSC version if required.

## Installation

1. Launch VirtualBox.
2. Click New.

![Launch VirtualBox](/windows%2011%20client%20pc%20Installation/images/launch-virtual-box.png)

### Virtual Machine Name and OS

- Enter a name for the virtual machine, for example Win 11.
- Leave the VM folder at the default setting.
- Select the Windows 11 ISO you downloaded.
- Leave the unattended install option unchecked unless you specifically want it enabled.

![VM name](/windows%2011%20client%20pc%20Installation/images/vm-name.png)

### Specify Virtual Hardware

- Set the base memory (RAM) to 4 GB.
- Set the CPU to 2 cores.

![VM memory](/windows%2011%20client%20pc%20Installation/images/vm-memory.png)

### Specify Virtual Hard Disk

- Set the disk size to 80 GB or more.

![VDI configuration](/windows%2011%20client%20pc%20Installation/images/VDi-customization.png)

- Click Finish. You should see the VM in the VirtualBox manager.
- Click Start.

![Starting the machine](/windows%2011%20client%20pc%20Installation/images/starting-the-machine.png)

- While the machine is starting, pay attention and press any key to boot from the CD/DVD.

### Windows 11 Setup

The VM should boot into the Windows 11 setup wizard.

- Select your preferred language and time settings.

![Setup wizard](/windows%2011%20client%20pc%20Installation/images/win-11-setup.png)

- Click Next.
- Select the keyboard layout.

![Keyboard layout](/windows%2011%20client%20pc%20Installation/images/keybpard-setting.png)

- Click Next.
- Select the setup option to install Windows 11.

![Setup option](/windows%2011%20client%20pc%20Installation/images/setup-option.png)

- Accept the license terms.
- Click Next.

![Terms and conditions](/windows%2011%20client%20pc%20Installation/images/terms-and-conditions.png)

- Click Accept.

![Drive allocation](/windows%2011%20client%20pc%20Installation/images/drive-allocation.png)

- Click Next.

The system will check your configuration and prepare the installation.

![Ready to install](/windows%2011%20client%20pc%20Installation/images/ready-to-install.png)

- Click Install.

![Installation begins](/windows%2011%20client%20pc%20Installation/images/installing-begins.png)
