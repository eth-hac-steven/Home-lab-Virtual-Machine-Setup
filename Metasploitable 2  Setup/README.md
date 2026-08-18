# Metasploitable 2 Setup
This is a test environment that provides a secure place to perform penetration testing and security research. For your test environment, 
The following sections describe the requirements and instructions for setting up a vulnerable target. Downloading and Setting Up Metasploitable 
2 The easiest way to get a target machine is to use Metasploitable 2, which is an **intentionally** vulnerable Ubuntu Linux virtual machine 
that is designed for testing common vulnerabilities. 
This virtual machine (VM) is compatible with VMWare, VirtualBox, and other common virtualization platforms.

## Downloading and Setting Up Metasploitable 2

- Step-1. Metasploitable 2 is available at:

    - [Rapid7](https://information.rapid7.com/metasploitable-download.html)
    - [sourceforge.net](https://sourceforge.net/projects/metasploitable/)

- Step-2. Extracting the File 
 The compressed file is about 800 MB and can take a while to download over a slow connection. After you have downloaded the Metasploitable 2 file, you will need to unzip the file to see its contents.
   - Navigate to the file where the download was saved
   - Right click on it Then extract it

- Step-3. Setting Metasploitable 2 in Virtualbox
   - Open virtaulbox 
   - click on New 
   - Name the V-machine e.g Metasploitable-2
   - Select Linux as the OS
    
  ![Ms2-setup1](https://github.com/eth-hac-steven/Home-lab-Virtual-Machine-Setup/blob/main/Metasploitable%202%20%20Setup/Ms2-set-up.png)
 

    - Click on "Specify on virtual Disk"
    - Select "Use an Existing Virtual Hard disk"
    - Click on the folder icon towards the  right hand side of the screen
    - click on "Add"
    - Navigate to the where Metasploitable 2  Extracted
    - Click on "open"
    - click on "Choose"
    - Click on "Finish"
    
  ![Ms2-setup2](https://github.com/eth-hac-steven/Home-lab-Virtual-Machine-Setup/blob/main/Metasploitable%202%20%20Setup/Ms2-set-up2.png)

- Step-4 : Networking Setup

    By Default your machine should be set to NAT, we want kali to be able to Communicate with this machine to that will set the Network adapter to 
   [NAT network]([https://information.rapid7.com/metasploitable-download.html](https://github.com/eth-hac-steven/Home-lab-Virtual-Machine-Setup/blob/main/virtualbox_network_modes.md)). To do that we:
   - Click on "Network"
   - Click on "NAT-Network"
   - click on "Create"
   - This should create a NAT-network for this lab 
   - Enter a name or leave the Default(NATnetwork) 
   - Enter a custom IP address block range or leave the Default 
   - Enable DHCP
   - click on apply

  ![Ms2-set-up3](https://github.com/eth-hac-steven/Home-lab-Virtual-Machine-Setup/blob/main/Metasploitable%202%20%20Setup/Ms2-set-up3.png)
   
  Now on the Virtual Machine 
  
   - Select Metasploitable 2 
   - Click on "setting"
   - Click on " Network"
   - On Adapter 1
   - Change "Attached to: NAT network"
   - Select the name (NATnetwork)
   - Click on "ok"
   - Do the same for Kali-linux

  ![Ms2-setup4](https://github.com/eth-hac-steven/Home-lab-Virtual-Machine-Setup/blob/main/Metasploitable%202%20%20Setup/Ms2-set-up4.png)
   
  With this Metasploitable 2 has been setup  and is on the same network with Kali to test check the IP s of both Machines
   
  
