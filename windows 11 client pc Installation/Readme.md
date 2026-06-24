# Windows 11 Client Installation

## Description  
  
The window 11 client system is a very important vm for this homelab, as it allows us to simulate a users view on this network and provides and consequence free device for various configuration

## Requirements

- [Windows 11 iso](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-11-enterprise)
   - Download the LTSC version


## Installation

- launch Virtual box
- click on New

![installation-begins](/windows%2011%20client%20pc%20Installation/images/launch-virtual-box.png)


   ### Virtual Machine Name and OS
   
   - Enter the name for Virtual machine e.g ***Win 11*** 
   - Leave VM folder as the defaults
   - ISO image : Navigate to where the Win 11 iso was downloaded to
   - uncheck unintended install
   
   
   ![vm-name](/windows%2011%20client%20pc%20Installation/images/vm-name.png)

   ### Specify Virtual Hardware
   
   - Set the base memory (RAM) to 4gb
   - Set the CPU to 2 cores
   
![vm-memory](/windows%2011%20client%20pc%20Installation/images/vm-memory.png)

   ### Specify virtual Hard disk
   
   - Set disk size to 80gb or more

![VDI](/windows%2011%20client%20pc%20Installation/images/VDi-customization.png)

- Click on finish,You should see the VM
- click on start

![starting-the-machine](/windows%2011%20client%20pc%20Installation/images/starting-the-machine.png)

-While the machine is starting make sure to pay attention and ```PRESS ANY KEY TO BOOT INTO CD OR DVD```

### Windows 11 setup

 The VM should boot up and display the win 11 setup wizard

 - Select the language and Time of your choice

![setup wizard](/windows%2011%20client%20pc%20Installation/images/win-11-setup.png)

 - click Next
 - Select the keyboard format.

![keyboard format](/windows%2011%20client%20pc%20Installation/images/keybpard-setting.png)

 - click Next
 - Select a setup option (Install Windows 11)

![setup-option](/windows%2011%20client%20pc%20Installation/images//setup-option.png)

 - Check the " i agree with ....."
 - Click Next

![terms and condition](/windows%2011%20client%20pc%20Installation/images/terms-and-conditions.png)

 - Click Accept

![drive-allocation](/windows%2011%20client%20pc%20Installation/images/drive-allocation.png)

 - click Next

 your pc will be checked and be made ready

 ![installation-begins](/windows%2011%20client%20pc%20Installation/images/ready-to-install.png)

- click Install

 ![installation-begins](/windows%2011%20client%20pc%20Installation/images/installing-begins.png)
