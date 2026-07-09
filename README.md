# 🏠 Home Lab Virtual Machine Setup

A comprehensive repository containing configurations, setup guides, and documentation for virtual machines in a home lab environment that uses VirtualBox.

---

![Virtual-Box VM](/vm-screen.png)

## 📋 Overview

This project provides a complete home lab infrastructure setup with:

- ✅ VM configuration templates with recommended VirtualBox settings
- ✅ System configuration guides for networking, storage, and performance tuning
- ✅ Step-by-step documentation and troubleshooting resources

---

## 🚀 Getting Started

### Prerequisites

Before setting up your home lab, make sure you have:

- VirtualBox (latest version recommended)
  - 📥 [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  - 📥 [Download the VC++ Redistributable](https://aka.ms/vc14/vc_redist.x64.exe)

- Host machine requirements
  - Minimum 16 GB RAM (32 GB or more is recommended for multiple VMs)
  - A multi-core processor (4+ cores recommended)
  - Sufficient storage, preferably SSD-based storage for VM files

- Basic knowledge requirements
  - A basic understanding of virtualization concepts
  - Familiarity with Windows or Linux administration is helpful
  - A basic understanding of VirtualBox networking concepts

---

## Downloading and Installing VirtualBox and the VC++ Redistributable

### 1. Install the VC++ Redistributable

The VC++ Redistributable usually downloads automatically after you click the link.

1. Open the folder where the file was saved.
2. Double-click the downloaded file or press Enter.
3. Click Next.
4. Accept the license terms and click Install.
5. Restart your computer if prompted.

### 2. Install VirtualBox

1. Open the VirtualBox download page and select the version for your operating system.
2. A download prompt should appear. Save the installer to your preferred location.
3. Open the downloaded installer.
4. Follow the on-screen prompts to complete the installation.
5. Restart your computer if prompted.

![VirtualBox download and install screen](/VB-down%20and%20install.png)

> If the installer asks for permission to make changes, click Yes to continue.

---

## 🔧 VM Network Configurations

### Network Architecture

Detailed network configurations for inter-VM communication, external connectivity, and security policies are documented in the individual VM setup guides.

### Available Virtual Machines

| VM Name | OS | Purpose | Status |
|---------|-----|---------|--------|
| **Windows Server 2022** | Windows Server | Active Directory simulation and enterprise domain setup | ✅ Configured |
| **pfSense Firewall** | BSD-based | Enterprise firewall and network gateway simulation | ✅ Configured |
| **Windows 11 Client** | Windows 11 | Help desk scenarios, troubleshooting, and testing | ✅ Configured |
| **TrueNAS** | FreeBSD | Centralized storage and file server for lab users | ✅ Configured |
| **Kali Linux** | Linux | Purple team exercises and security testing | ✅ Configured |
| **Windows XP** | Windows | Target machine | Working on it |

---

## 💾 Backup and Recovery

### Snapshot Best Practices

**Always create snapshots before major configuration changes.**

A snapshot captures the exact state of a virtual machine at a specific point in time, allowing you to quickly revert to that state if something goes wrong.

**Snapshot strategy:**
- Create a snapshot before any significant system changes
- Name snapshots descriptively, for example `Before-AD-Setup` or `Post-Security-Update`
- Maintain a clean baseline snapshot for quick VM resets
- Delete old snapshots periodically to save disk space

> ⚠️ Snapshots consume disk space and can affect performance. Use them strategically rather than for every change.

---

## ⚠️ Known Issues and Troubleshooting

### Virtual Machine Conflicts

| Issue | Solution |
|-------|----------|
| **Multiple VMs will not start simultaneously** | If you start one VM and then another while both share the same VDI, the second VM may crash. Use separate VDI copies for each VM instance. |
| **Kali Linux kernel issues** | There is a known compatibility issue with some Kali Linux versions on VirtualBox. Update to the latest Kali ISO or check the [Kali Linux documentation](https://www.kali.org/) for patches. |
| **VMware compatibility** | VMware was tested, but significant conflicts were observed while VirtualBox was installed. Choose one platform for this lab. |

---

## 🤝 Contributing

Found an issue or have a suggestion? Feel free to:

1. Open an issue to report problems or suggest improvements
2. Submit a pull request with your changes
3. Share feedback and configuration ideas

---

## 📧 Contact and Support

- Questions? Open an issue in this repository.
- For specific setup questions or lab configuration requests, contact the maintainer directly.
- VirtualBox is the primary hypervisor for this lab setup.

---

## 📚 Additional Resources

- [VirtualBox Documentation](https://www.virtualbox.org/wiki/Documentation)
- [Windows Server Documentation](https://learn.microsoft.com/en-us/windows-server/)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [TrueNAS Documentation](https://www.truenas.com/docs/)

---

**Last Updated:** July 2026 | **Status:** Active Development ✨
