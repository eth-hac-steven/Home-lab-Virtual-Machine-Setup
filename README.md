# 🏠 Home Lab Virtual Machine Setup

A comprehensive repository containing configurations, setup, and documentation for virtual machines in my home lab environment running on **VirtualBox**.

---

![Virtual-Box_VM](/vm-screen.png)

## 📋 Overview

This project provides a complete home lab infrastructure setup with:

- ✅ **VM Configuration Templates** - Pre-configured settings and best practices for VirtualBox virtual machines
- ✅ **System Configurations** - Network, storage, and performance tuning guides
- ✅ **Documentation** - Step-by-step setup guides and troubleshooting resources

---

## 🚀 Getting Started

### Prerequisites

Before setting up your home lab, ensure you have:

- **VirtualBox** (latest version recommended)
  - 📥 [Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  - 📥 [VC++ Redistributable](https://aka.ms/vc14/vc_redist.x64.exe) (recommended for Windows hosts)

- **Host Machine Requirements**
  - Minimum 16GB RAM (32GB+ recommended for multiple VMs)
  - Multi-core processor (4+ cores recommended)
  - Adequate storage (SSD recommended for VM storage)

- **Knowledge Requirements**
  - Basic understanding of virtualization concepts
  - Familiarity with Windows/Linux administration (helpful but not required)

---

## 🔧 VM Network Configurations

### Network Architecture

Detailed network configurations for inter-VM communication, external connectivity, and security policies are documented in individual VM setup guides.

### Available Virtual Machines

| VM Name | OS | Purpose | Status |
|---------|-----|---------|--------|
| **Windows Server 2022** | Windows Server | Active Directory simulation & enterprise domain setup | ✅ Configured |
| **pfSense Firewall** | BSD-based | Enterprise firewall & network gateway simulation | ✅ Configured |
| **Windows 11 Client** | Windows 11 | Help desk scenarios, troubleshooting, testing | ✅ Configured |
| **TrueNAS** | FreeBSD | Centralized storage & file server for lab users | ✅ Configured |
| **Kali Linux** | Linux | Purple team exercises & security testing | ⚠️ See Notes |

---

## 💾 Backup & Recovery

### Snapshot Best Practices

**Always create snapshots before major configuration changes!**

A snapshot captures the exact state of a virtual machine at a specific point in time, allowing you to quickly revert to that condition if something goes wrong.

**Snapshot Strategy:**
- Create a snapshot before any significant system changes
- Name snapshots descriptively (e.g., `Before-AD-Setup`, `Post-Security-Update`)
- Maintain a clean baseline snapshot for quick VM resets
- Delete old snapshots periodically to save disk space

> ⚠️ **Warning:** Snapshots consume disk space and can impact performance. Use them strategically, not for every change.

---

## ⚠️ Known Issues & Troubleshooting

### Virtual Machine Conflicts

| Issue | Solution |
|-------|----------|
| **Multiple VMs won't start simultaneously** | If you start a VM, then attempt to start another VM while both share the same VDI, the second VM will crash. Use separate VDI copies for each VM instance. |
| **Kali Linux kernel issues** | There's a known kernel compatibility issue with Kali Linux on VirtualBox. Update to the latest Kali ISO or check the [Kali Linux documentation](https://www.kali.org/) for patches. |
| **VMware compatibility** | Tested VMware but experienced significant conflicts—VirtualBox is the recommended platform for this lab. |

---

## 🤝 Contributing

Found improvements or have suggestions? Feel free to:

1. Open an **Issue** to report problems or suggest enhancements
2. Submit a **Pull Request** with your improvements
3. Share your feedback and configurations

---

## 📧 Contact & Support

- **Questions?** Open an issue in this repository
- **Direct contact:** Reach out with specific setup questions or lab configuration requests
- **Note:** VirtualBox is the primary hypervisor for this lab setup

---

## 📚 Additional Resources

- [VirtualBox Documentation](https://www.virtualbox.org/wiki/Documentation)
- [Windows Server Documentation](https://docs.microsoft.com/en-us/windows-server/)
- [Kali Linux Docs](https://www.kali.org/docs/)
- [TrueNAS Documentation](https://www.truenas.com/docs/)

---

**Last Updated:** June 2026 | **Status:** Active Development ✨
