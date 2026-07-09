
# TrueNas Installation

![TrueNas](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-4.png)

### Description
   True-NAS(Network attached storage) is a centralized storage medium that allows use to be able to share and store files on the network.

### Requirements
 Download it from the offical site at
- [True-NAS iso ](https://www.truenas.com/download/)

or From 

OSboxes
- [True-NAS iso for Virtual-box](https://www.osboxes.org/truenas/)

i will be installing from OSboxes

### Installation 

- Launch virtualbox
- click on New

### Virtual Machine Name and OS
   
   - Enter the name for Virtual machine e.g ***True NAS*** 
   - Leave VM folder as the defaults
   - set the OS to BSD
   
   ![vm-name](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image.png)

   ### Specify Virtual Hardware
   
   - Set the base memory (RAM) to 2gb
   - Set the CPU to 1 cores
   
  ![base-memory](/PFsense%20Firewall%20Installation/images/base-memory.png)

   ### virtual Hard disk
   
   - Check ```using an existing Virtual hard disk file```
   - Click on the ```folder``` on the right hand side of the screen
   - Click on ```add```

![Virtual hard disk](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/Existing-vdi.png)


- Navigate to where the extacted  True Nas file is 
- click on open
- click on choose


![click-on-setting](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-1.png)

- Click on finish,You should see the VM
- Click on settings

![finished-vm](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-2.png)

- click on ```Network```
- click on ```Adapter 1```
- change the ```Attached to ``` Internal Network
- Enter the name of the same internal network in PFsense.

![Network-adpater](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-3.png)


- click on okay
- click on start

### Done

![installation-complete](/TrueNas%20Installation%20(Network%20Attached%20Storage)/images/image-5.png)

- To access this NAS use a systein the same internal network.