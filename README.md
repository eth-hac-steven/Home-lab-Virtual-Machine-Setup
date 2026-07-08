# 🏠 Home Lab Virtual Machine Setup

A comprehensive set of step-by-step guides, screenshots, and tips to help beginners build a small home lab using VirtualBox. This repo contains VM setup instructions for pfSense, TrueNAS, Kali Linux, Windows Server/clients, and related configuration notes.

---

![Virtual-Box_VM](/vm-screen.png)

## Quick Start (for absolute beginners)

Follow these minimal steps to get one VM running from a fresh machine:

1. Install VirtualBox:
   - Windows/macOS/Linux: download and install from https://www.virtualbox.org/wiki/Downloads
   - On Windows, after installing VirtualBox also install the Visual C++ Redistributable (VC++ 2015-2019/2022) if prompted: https://aka.ms/vs/17/release/vc_redist.x64.exe
2. Pick a VM guide in this repository (for example `PFsense Firewall Installation/Readme.md`) and download the referenced ISO or VDI file from the links in that guide.
3. In VirtualBox:
   - To import an appliance (OVA/OVF): File → Import Appliance → select the file and follow the prompts.
   - To create a new VM and attach an ISO/VDI: New → give it a name → set OS type → create or choose existing virtual disk (use the guide's recommended settings).
4. Start the VM. If the guide mentions default credentials, change the password immediately and follow any additional post-install steps listed in the VM's folder.

If you get stuck, open an issue describing the step you were on and paste the error text or a screenshot.

---

## 📋 Overview

This project provides a complete home lab infrastructure setup with:

- ✅ VM Configuration Templates - Pre-configured settings and best practices for VirtualBox virtual machines
- ✅ System Configurations - Network, storage, and performance tuning guides
- ✅ Documentation - Step-by-step setup guides and troubleshooting resources

---

## 🧰 Prerequisites (short)

- VirtualBox (latest version recommended)
- Host machine: minimum 16GB RAM recommended for multiple VMs; SSD recommended for VM storage.
- Basic willingness to follow step-by-step instructions. No coding experience required.

---

## Available Virtual Machines

| VM Name | OS | Purpose | Status |
|---------|-----|---------|--------|
| **Windows Server 2022** | Windows Server | Active Directory simulation & enterprise domain setup | ✅ Configured |
| **pfSense Firewall** | BSD-based | Enterprise firewall & network gateway simulation | ✅ Configured |
| **Windows 11 Client** | Windows 11 | Help desk scenarios, troubleshooting, testing | ✅ Configured |
| **TrueNAS** | FreeBSD | Centralized storage & file server for lab users | ✅ Configured |
| **Kali Linux** | Linux | Purple team exercises & security testing | ✅ Configured |
| **Windows XP** | Windows (legacy) | Target machine | Work in progress |

---

## 💾 Backup & Recovery

Always create snapshots before major configuration changes. Snapshots capture the VM state and allow you to revert if something goes wrong. Use snapshots judiciously — they use disk space.

---

## ⚠️ Known Issues & Troubleshooting (high level)

- Multiple VMs won't start simultaneously if they share the same VDI. Use separate VDI copies for each VM or use immutable disks / linked clones correctly.
- Kali Linux: if you hit kernel/compatibility issues, update to a recent Kali ISO or use the official Kali VirtualBox image from https://www.kali.org.
- VMware compatibility: choose one hypervisor at a time (VirtualBox or VMware) to avoid conflicts.

---

## 🤝 Contributing

See CONTRIBUTING.md for how to file issues and contribute edits, screenshots, and fixes.

---

## 📧 Contact & Support

Open an issue in this repository for questions or step-by-step help.

---

**Last Updated:** July 2026 | **Status:** Active Development ✨
