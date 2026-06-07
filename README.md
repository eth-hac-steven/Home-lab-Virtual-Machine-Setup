# Home Lab Virtual Machine Setup

A comprehensive repository containing configurations, setup and documentation for virtual machines in my home lab environment running on VirtualBox.

## 📋 Overview

This project provides:
- **VM Configuration Templates** - Pre-configured settings for VirtualBox virtual machines
- **System Configurations** - Network, storage, and performance tuning
- **Documentation** - Step-by-step guides for environment setup

## 🚀 Getting Started

### Prerequisites
- VirtualBox installed and configured
   - [Download it from here](https://www.virtualbox.org/wiki/Downloads)
   - [Also get this(VC redist) just is case](https://aka.ms/vc14/vc_redist.x64.exe) 
- Host machine with adequate resources (RAM, CPU, storage)
- Basic knowledge of virtualization concepts

## 🔧 VM Network Configurations

[Add details about your VM setups here]

### Available VMs
- Windows Server 2022 - ACtive Directory simulation and more
- Pfsense firewall - to simulate an enterprise setup
- Windows 11 cleint pc - For simulating help desk fix and running test
- True Nas - For to simulate a centralize storage for users
- kali linux - For a little bit of Purple teaming

## 💾 Backup & Recovery

 Before any major config on Any VM make use  the snapshot feature. 
 - A snapshot captures the exact state of a system, file, or virtual machine at a specific point in time, allowing you to revert to that precise condition later if needed.

## 🤝 Contributing

Feel free to suggest improvements or additions to these configurations.

## Virtual Machine Notes
 - If you start a VM, then start another VM while both have the VDIs, the second on will crash.
 - kernel issue on virtual box(kali)

## 📧 Contact

- For questions or issues, feel free to open an issue or contact me directly.
- Yes, tried VMware and had conflict issues.

