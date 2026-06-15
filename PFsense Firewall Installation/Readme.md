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
   
   - Set disk size to 30gb or more



- Click on finish,You should see the VM
- click on start