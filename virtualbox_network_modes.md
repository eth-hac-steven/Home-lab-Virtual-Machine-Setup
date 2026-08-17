# VirtualBox Network Modes - Quick Reference

## Network Mode Comparison Table

| Mode | VM → Internet | VM ↔ VM | VM ↔ Host | Host → VM | Use Case |
|------|--------------|---------|-----------|-----------|----------|
| **NAT** | ✓ Yes | ✗ No | ✗ No | ✗ No | Single isolated VM needing internet |
| **NAT Network** | ✓ Yes | ✓ Yes (same network) | ✗ No | ✗ No | Multi-VM lab with internet |
| **Bridged** | ✓ Yes | ✓ Yes | ✓ Yes | ✓ Yes | VM as real network device |
| **Internal** | ✗ No | ✓ Yes (same network) | ✗ No | ✗ No | Isolated VM-to-VM network |
| **Host-Only** | ✗ No | ✓ Yes | ✓ Yes | ✓ Yes | VM ↔ Host communication |

---

## Detailed Breakdown

### 1. NAT (Network Address Translation)
**What it does:**
- VM gets 10.0.2.15 (always the same IP for every NAT VM)
- VirtualBox translates VM's requests to host's IP
- One-way internet access only

**Pros:**
- Simple, zero configuration
- Instant internet access
- Isolated and secure

**Cons:**
- VMs cannot see each other (even multiple NAT VMs)
- Cannot access VM from host
- No incoming connections possible

**Use when:**
- Quick single VM testing
- Need internet but want complete isolation
- Running untrusted software

---

### 2. NAT Network
**What it does:**
- Creates a virtual router with DHCP, DNS, and routing
- VMs share a custom network (e.g., 192.168.6.0/24)
- Built-in services handle everything

**Pros:**
- VMs can communicate with each other
- Still get internet access
- Easy multi-VM setup

**Cons:**
- Built-in routing bypasses your virtual firewall/router
- Can't access VMs from host
- Less control over network behavior

**Use when:**
- Quick multi-VM lab
- Don't need fine-grained network control
- NOT when building firewall/router VMs (it defeats the purpose!)

**⚠️ WARNING for pfSense/firewall labs:**
DO NOT use NAT Network for LAN side - it has built-in routing that bypasses your firewall!

---

### 3. Bridged Adapter
**What it does:**
- VM appears as real device on your physical network
- Gets IP from your home/office router
- Fully exposed to network

**Pros:**
- VM is a "real" network device
- Can be accessed from anywhere on network
- Works with network services (printer sharing, file sharing, etc.)

**Cons:**
- Exposes VM to network attacks
- Uses real network IP addresses
- Depends on physical network configuration

**Use when:**
- Need VM accessible from other physical machines
- Testing network services
- VM needs to be on production network

---

### 4. Internal Network
**What it does:**
- Pure Layer 2 virtual switch
- NO built-in routing, DHCP, or internet
- Just connects VMs together

**Pros:**
- Complete isolation from external networks
- Forces all traffic through your virtual router/firewall
- Perfect for network labs
- Full control over routing and services

**Cons:**
- No internet access without a router VM
- Must configure DHCP manually or use static IPs
- Requires more setup

**Use when:**
- Building pfSense/firewall labs ✓
- Network segmentation practice
- Fully isolated test environments
- Want complete control over routing

**✓ RECOMMENDED for pfSense LAN side!**

---

### 5. Host-Only Adapter
**What it does:**
- Creates network between host and VMs only
- VirtualBox creates virtual adapter on host (vboxnet0, etc.)
- Isolated from external network

**Pros:**
- Host can access VMs easily
- VMs can access host
- Secure - isolated from external network

**Cons:**
- No internet access for VMs
- Requires host-side network configuration

**Use when:**
- Need to access VM web interfaces from host
- Management/admin access to VMs
- File sharing between host and VMs
- Perfect for pfSense management interface!

---

## Common Homelab Configurations

### Basic pfSense Firewall Lab
```
pfSense VM:
├── Adapter 1: NAT (WAN - internet access)
├── Adapter 2: Internal Network "LAN" (for client VMs)
└── Adapter 3: Host-Only (management/web GUI access)

Client VMs (DC, Win11, etc.):
└── Adapter 1: Internal Network "LAN" (forces traffic through pfSense)
```

### Multi-Segment Network
```
pfSense VM:
├── Adapter 1: NAT (WAN)
├── Adapter 2: Internal Network "DMZ"
├── Adapter 3: Internal Network "LAN"
└── Adapter 4: Host-Only (management)

Web Server:
└── Adapter 1: Internal Network "DMZ"

Client VMs:
└── Adapter 1: Internal Network "LAN"
```

---

## IP Address Patterns

| Mode | Typical IP Range | Who assigns? |
|------|-----------------|--------------|
| NAT | 10.0.2.15/24 | VirtualBox (fixed) |
| NAT Network | Custom (e.g., 192.168.6.0/24) | VirtualBox DHCP or manual |
| Bridged | Same as physical network | Physical router |
| Internal | Manual or your DHCP server | You configure |
| Host-Only | 192.168.56.0/24 (default) | VirtualBox DHCP or manual |

---

## VMware Equivalents

### VirtualBox → VMware Workstation/Fusion

| VirtualBox | VMware | Notes |
|------------|--------|-------|
| NAT | NAT | Same concept - isolated VM with internet |
| NAT Network | NAT (with virtual network editor) | VMware's NAT can do VM-to-VM by default |
| Bridged | Bridged | Identical functionality |
| Internal Network | LAN Segment (Workstation) / Private (Fusion) | Same - isolated VM-to-VM only |
| Host-Only | Host-Only | Nearly identical |

### Key VMware Differences:

**VMware NAT is more flexible:**
- VMs on same NAT can communicate by default (like VirtualBox NAT Network)
- Can customize network ranges easily
- Has built-in DHCP like NAT Network

**VMware LAN Segments (Workstation):**
- Same as VirtualBox Internal Network
- Can create multiple isolated segments
- Perfect for firewall labs

**VMware Private Network (Fusion - Mac):**
- Same as Internal Network
- VMs can talk to each other, nothing else

**VMware vSphere/ESXi (Enterprise):**
- Much more advanced virtual networking
- Distributed switches, VLANs, port groups
- Professional-grade features

---

## Quick Decision Tree

**Need internet access?**
- Single VM only → **NAT**
- Multiple VMs, simple lab → **NAT Network**
- Building router/firewall → **NAT (WAN) + Internal (LAN)**
- VM on real network → **Bridged**

**No internet needed?**
- VM-to-VM only → **Internal Network**
- Host-to-VM access → **Host-Only**
- Complete isolation → **Internal Network**

**Building security lab?**
- WAN side → **NAT**
- LAN side → **Internal Network** ✓
- Management → **Host-Only**

---

## Common Mistakes to Avoid

❌ Using NAT Network for pfSense LAN
- Traffic bypasses your firewall completely
- Defeats the purpose of having pfSense

❌ Using Bridged for everything
- Exposes lab VMs to your real network
- Security risk
- Wastes real IP addresses

❌ Forgetting to set gateway on Internal Network VMs
- VMs can talk to each other but not internet
- Must point to your router VM (e.g., pfSense)

❌ Mixing network modes randomly
- Creates confusing routing scenarios
- Makes troubleshooting impossible

✓ **For pfSense labs: NAT (WAN) + Internal (LAN) + Host-Only (mgmt)**

---

## Troubleshooting Tips

**VM has no internet on Internal Network?**
- Expected! Add a router VM or change to NAT Network

**Can't ping between VMs on NAT?**
- Expected! NAT isolates VMs. Use NAT Network or Internal

**Can't access VM from host?**
- Add Host-Only adapter or use Bridged

**pfSense not logging traffic?**
- Check if LAN is on NAT Network (bypasses pfSense)
- Should be on Internal Network

**Traffic slow through pfSense?**
- Check DNS settings
- Disable DNSSEC if enabled
- Check firewall rules

---

## Summary for Your Current Setup

**What you had (broken):**
```
WAN: NAT ✓
LAN: NAT Network ✗ (bypassed pfSense)
```

**What you need (correct):**
```
WAN: NAT ✓
LAN: Internal Network ✓
Optional: Host-Only (for management) ✓
```

This forces all LAN traffic through pfSense, giving you:
- Complete traffic visibility
- Full firewall control
- Proper logging
- Realistic network behavior
