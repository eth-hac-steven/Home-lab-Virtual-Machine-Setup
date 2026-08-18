## Name-Resolution Failure in Kali Linux

This issue usually happens when the system keeps old DNS settings from a previous ISP, or when the new ISP provides a different DNS server or DHCP configuration.

Follow these steps carefully to fix it.

### 1. Check whether the problem is DNS-related

Open a terminal and test:

```bash
ping -c 3 8.8.8.8
ping -c 3 google.com
```

- If `8.8.8.8` responds but `google.com` fails, the issue is almost certainly DNS resolution.
- If both fail, check the network connection itself first.

### 2. Check the current DNS configuration

```bash
cat /etc/resolv.conf
```

Look for stale nameservers such as:

- old ISP DNS addresses
- incorrect private DNS values
- empty or wrong entries

Also check the active interface:

```bash
nmcli dev show | grep IP4.DNS
```

If you use systemd-resolved:

```bash
systemd-resolve --status
```

### 3. Replace stale DNS servers with reliable ones

For Kali, a common fix is to use public DNS such as Cloudflare or Google.

```bash
sudo nano /etc/resolv.conf
```

Then write:

```bash
nameserver 1.1.1.1
nameserver 1.0.0.1
```

Or:

```bash
nameserver 8.8.8.8
nameserver 8.8.4.4
```

Save and exit.

> Note: Some Kali systems regenerate `/etc/resolv.conf` automatically after reconnecting to the network, so this may need to be fixed in the network manager settings too.

### 4. Fix NetworkManager settings (recommended)

Check your connection profile:

```bash
nmcli connection show
```

Then set custom DNS for the active connection:

```bash
sudo nmcli connection modify "<connection-name>" ipv4.dns "1.1.1.1 1.0.0.1"
sudo nmcli connection modify "<connection-name>" ipv4.ignore-auto-dns yes
sudo nmcli connection up "<connection-name>"
```

Replace `<connection-name>` with the actual network profile name, such as `Wired connection 1` or `eth0`.

If you want to see the profile list clearly:

```bash
nmcli connection show --active
```

### 5. If `/etc/resolv.conf` keeps resetting

This often happens when NetworkManager or systemd-resolved is managing DNS.

Check whether `/etc/resolv.conf` is a symlink:

```bash
ls -l /etc/resolv.conf
```

If it points to a generated file, disable the service or override it.

For systemd-resolved:

```bash
sudo systemctl stop systemd-resolved
sudo systemctl disable systemd-resolved
```

Then recreate the resolv file:

```bash
sudo rm /etc/resolv.conf
sudo nano /etc/resolv.conf
```

Add:

```bash
nameserver 1.1.1.1
nameserver 1.0.0.1
```

Then save.

### 6. Restart networking

```bash
sudo systemctl restart NetworkManager
```

Or, if you use a static interface:

```bash
sudo systemctl restart networking
```

Then test again:

```bash
ping -c 3 google.com
```

### 7. Flush DNS cache

If the old DNS value was cached, clear it:

```bash
sudo resolvectl flush-caches
```

Or:

```bash
sudo systemctl restart systemd-resolved
```

If you are using a local cache service:

```bash
sudo nscd -i hosts
```

### 8. Test DNS directly with known servers

Check if the server responds correctly:

```bash
dig @1.1.1.1 google.com
```

or:

```bash
nslookup google.com
```

If these work, the problem is almost certainly your system DNS configuration, not the internet connection itself.

### 9. Check for ISP DHCP changes

When the ISP changes often, the router or DHCP server may hand out different DNS values. Kali may keep using the old values until the interface is refreshed.

Run:

```bash
sudo dhclient -r
sudo dhclient
```

or renew the connection:

```bash
nmcli connection down "<connection-name>"
nmcli connection up "<connection-name>"
```

### 10. If IPv6 is causing trouble

Sometimes IPv6 misconfiguration breaks name resolution even when IPv4 works.

Check:

```bash
ip addr
```

If needed, disable IPv6 temporarily:

```bash
sudo nano /etc/sysctl.conf
```

Add:

```bash
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
```

Then apply:

```bash
sudo sysctl -p
```

### 11. Final verification

Run all of these:

```bash
cat /etc/resolv.conf
ping -c 3 8.8.8.8
ping -c 3 google.com
getent hosts google.com
```

If `google.com` resolves successfully, the issue is fixed.

---

### Recommended permanent solution

When changing ISPs frequently, do this:

1. Set static DNS values in NetworkManager.
2. Disable automatic DNS override when needed.
3. Check `/etc/resolv.conf` after each ISP change.
4. Restart NetworkManager if the DNS values do not update.
5. Use reliable public DNS like `1.1.1.1` or `8.8.8.8`.

This is the most reliable fix for domain resolution failures after switching internet providers.

### Quick command summary

```bash
cat /etc/resolv.conf
nmcli dev show | grep IP4.DNS
sudo nmcli connection modify "Wired connection 1" ipv4.dns "1.1.1.1 1.0.0.1"
sudo nmcli connection modify "Wired connection 1" ipv4.ignore-auto-dns yes
sudo nmcli connection up "Wired connection 1"
sudo systemctl restart NetworkManager
ping -c 3 google.com
```

If the problem still remains, the next step is to check the DHCP lease and router settings because some ISPs send broken or conflicting DNS values.

