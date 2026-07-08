# 🏠 Home Lab Virtual Machine Setup

A comprehensive set of step-by-step guides, screenshots, and tips to help beginners build a small home lab using VirtualBox. This repo contains VM setup instructions for pfSense, TrueNAS, Kali Linux, Windows Server/clients, and related configuration notes.

---

![Virtual-Box_VM](/vm-screen.png)

## Table of Contents

- Quick Start
- Available VM Guides
  - pfSense Firewall Installation
  - pfSense Captive Portal (Default)
  - TrueNAS Installation (Network Attached Storage)
  - Kali Linux Installation
  - Windows Server 2022
  - Windows 11 Client
- Contributing

## Quick Start (for absolute beginners)

Follow these minimal steps to get one VM running from a fresh machine:

1. Install VirtualBox:
   - Windows/macOS/Linux: download and install from https://www.virtualbox.org/wiki/Downloads
   - On Windows, after installing VirtualBox also install the Visual C++ Redistributable (VC++ 2015-2022) if prompted: https://aka.ms/vs/17/release/vc_redist.x64.exe
2. Pick a VM guide in this repository (for example `pfsense-firewall-installation/README.md`) and download the referenced ISO or VDI file from the links in that guide.
3. In VirtualBox:
   - To import an appliance (OVA/OVF): File → Import Appliance → select the file and follow the prompts.
   - To create a new VM and attach an ISO/VDI: New → give it a name → set OS type → create or choose existing virtual disk (use the guide's recommended settings).
4. Start the VM. If the guide mentions default credentials, change the password immediately and follow any additional post-install steps listed in the VM's folder.

If you get stuck, open an issue describing the step you were on and paste the error text or a screenshot.

---

## Available VM Guides

- pfSense Firewall: pfsense-firewall-installation/README.md
- pfSense Captive Portal: pfsense-captive-portal/README.md
- TrueNAS: truenas-installation/README.md
- Kali Linux: kali-linux-installation/README.md
- Windows Server 2022: windows-server-2022-installation/README.md
- Windows 11 Client: windows-11-client-installation/README.md

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
