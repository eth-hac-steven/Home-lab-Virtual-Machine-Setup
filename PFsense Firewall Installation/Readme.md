# PFsense Firewall Installation
 
 A firewall is a key part of any network infrastructure this will help filter unwanted traffic,access to different Devices on the network.

## Requirement

- [PFsense Firewall iso](https://pfsense.com/download/)

## Downloading PFsense Firewall iso

- click on Download 
- On ```installation media``` select ```AMD64 ISO ipmi/virtual machine```
- click on ```add to cart```
- click on ```Enter cart```
- click on ```Checkout```
- Create an Account
- It free to get it 
- Download the ISO.gz file
- Extract the file

## Installation

- Launch virtualbox
- click on New

### Virtual Machine Name and OS
   
   - Enter the name for Virtual machine e.g ***PFsense Firewall*** 
   - Leave VM folder as the defaults
   - ISO image : Navigate to where the PFsense Firewall iso was downloaded to
   
   ![vm-name](/PFsense%20Firewall%20Installation/images/vm-name.png)

   ### Specify Virtual Hardware
   
   - Set the base memory (RAM) to 1gb
   - Set the CPU to 2 cores
   
  ![base-memory](/PFsense%20Firewall%20Installation/images/base-memory.png)

   ### Specify virtual Hard disk
   
   - Set disk size to 20gb or more

![Virtual hard disk](/PFsense%20Firewall%20Installation/images/base-memory.png)

- Click on finish,You should see the VM
- Click on settings

![click-on-setting](/PFsense%20Firewall%20Installation/images/click-on-settings.png)

- click on Network
- click on Adapter 2

![Network-adpater](/PFsense%20Firewall%20Installation/images/Screenshot%202026-06-15%20195108.png)

- change the ```Attached to ``` Internal Network
- Enter a name of Choice or stick to Default

![etwork](/PFsense%20Firewall%20Installation/images/internal%20network.png)

- click on okay
- click on start

### Set-up 
 After starting the machine should see the this page

 ![netgate-installer](/PFsense%20Firewall%20Installation/images/Netgate-installer.png)

- Click Accept

![Welcome](/PFsense%20Firewall%20Installation/images/welcome-page.png)

- Select install
- Clck ok

![click-on-okay](/PFsense%20Firewall%20Installation/images/click-ok.png)

- click ok


