# PFsense Firewall Installation

   ![pfsense-thumbnail](/PFsense%20Firewall%20Installation/images/pfsense-header.png)
  
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
- Its free to get it 
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

- click on ```Network```
- click on ```Adapter 2```
- click on ```Enable Network Adapter```

![Network-adpater](/PFsense%20Firewall%20Installation/images/Screenshot%202026-06-15%20195108.png)

- change the ```Attached to ``` Internal Network
  - This Internal network act as layer 2 switch for the device that will be on this network.
- Enter a name of Choice or stick to the Default.

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

### Selecing a WAN interface 
  A WAN(wide Area Netowrk) interface is required to be able to recieve and send .

- select ```em0```
- click ok

![em0-interface](/PFsense%20Firewall%20Installation/images/em0-interface.png)

### WAN network Setup 

![WAN network Setup](/PFsense%20Firewall%20Installation/images/image.png)
 Leave as Default 
 - click ok

 - ***interface mode : DCHP(client)*** : This was set because to the ISP aka my Router assigns IP dynamically , if set to static this would cause a collision  in the future.
     

### Selecing a WAN interface 
  The LAN(Local Area Netowrk) interface is required  for System on the internal Network to be able to access the internet.

![LAN network Setup ](/PFsense%20Firewall%20Installation/images/image-2.png)

- Select ```em1``` 
- click  ok

### LAN network Setup 

- Leave as default 
  - You can change any options by Selecting and hit enter
- I change the DHCP range, you can still leave as default.
- click ok

![LAN network Setup](/PFsense%20Firewall%20Installation/images/image-3.png)

Click continue

![alt text](/PFsense%20Firewall%20Installation/images/image-4.png)

You should see a popup about trying to connect,if you have internet connection this should not take long , if not it might fail.

![alt text](/PFsense%20Firewall%20Installation/images/image-13.png)

### Next

![alt text](/PFsense%20Firewall%20Installation/images/image-5.png)

- Select ```install CE```
- Hit Enter

### Selecting File System

![alt text](/PFsense%20Firewall%20Installation/images/image-6.png)

- Leave As Default
- select OK
- hit Enter

![alt text](/PFsense%20Firewall%20Installation/images/image-7.png)

- select OK
- hit Enter

![alt text](/PFsense%20Firewall%20Installation/images/image-8.png)

- select OK
- hit Enter

![alt text](/PFsense%20Firewall%20Installation/images/image-9.png)

- select OK
- Hit Enter

![alt text](/PFsense%20Firewall%20Installation/images/image-10.png)

### Stable Version Selection

![stable-version](/PFsense%20Firewall%20Installation/images/image-11.png)

- select OK
- Hit Enter

![installation-begins](/PFsense%20Firewall%20Installation/images/image-12.png)

Installation started, wait for it to be completed
 - Have a good internet connection to avoid failures, which will cause you to start again.

***serval minutes later*** yes, i did not have good network(internet connection) :).

![Installation-complete](/PFsense%20Firewall%20Installation/images/image14.png)

- select ok
- Hit Enter

![another-step](/PFsense%20Firewall%20Installation/images/image-15.png)

 This step is very important we are going to remove the iso , if we do not  the set up process will repeat each time you start the machine

 and here is how 

- Right  the disc as shown below

![removing-the-iso](/PFsense%20Firewall%20Installation/images/image-16.png)

- uncheck the ```Netgate-installer....iso

which should show you this 

![force-unmount-iso](/PFsense%20Firewall%20Installation/images/image-17.png)

- click ```Force unmount```
-  Select ```Reboot```
- Hit Enter
- or shut the machine down the restart it.

### Done
 
![set-up complete](/PFsense%20Firewall%20Installation/images/image-18.png)




#### more
 [If i was not clear enough check here](https://simplificandoredes.com/en/install-pfsense-on-virtualbox/)
