# Windows 11 Client Installation

## Description  
  
The window 11 client system is a very important vm for this homelab, as it allows us to simulate a users view on this network and provides and consequence free device for various configuration

## Requirements

- Windows 11 iso

## Installation

- launch Virtual box
- click on New

![installation-begins](/Windows%2011%20Client%20Installation/launch-virtual-box.png)


   ### Virtual Machine Name and OS
   
   - Enter the name for Virtual machine e.g ***Win 11*** 
   - Leave VM folder as the defaults
   - ISO image : Navigate to where the Win 11 iso was downloaded to
   - uncheck unintended install
   
   ![Virtual-machine-name-and-os](/Windows%2011%20Client%20Installation/vm-name.png)

   ### Specify Virtual Hardware
   
   - Set the base memory (RAM) to 4gb
   - Set the CPU to 2 cores
   
![vm-memory](/Windows%2011%20Client%20Installation/vm-memory.png)

   ### Specify virtual Hard disk
   
   - Set disk size to 80gb or more

![VDI](/Windows%2011%20Client%20Installation/VDi-customization.png)

- Click on finish,You should see the VM
- click on start

![starting-the-machine](/Windows%2011%20Client%20Installation/starting-the-machine.png)

-While the machine is starting make sure to pay attention and ```press any key to boot into the CD or dvd```

### Windows 11 setup

 The VM should boot up and display the win 11 setup wizard

 - Select the language and Time of your choice

![setup wizard](/Windows%2011%20Client%20Installation/win-11-setup.png)

 - click Next
 - Select the keyboard format.

![keyboard format](/Windows%2011%20Client%20Installation/keybpard-setting.png)

 - click Next
 - Select a setup option (Install Windows 11)

![setup-option](/Windows%2011%20Client%20Installation/setup-option.png)

 - Check the " i agree with ....."
 - Click Next

![terms and condition](/Windows%2011%20Client%20Installation/terms-and-conditions.png)

 - Click Accept

![drive-allocation](/Windows%2011%20Client%20Installation/drive-allocation.png)

 - click Next

 your pc will be checked and be made ready

 ![installation-begins](/Windows%2011%20Client%20Installation/ready-to-install.png)

- click Install

 ![installation-begins](/Windows%2011%20Client%20Installation/installing-begins.png)
