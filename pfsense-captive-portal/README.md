# pfSense Captive Portal (Default) setup

This guide shows how to enable the pfSense built-in captive portal and create local users and groups.

Prerequisites

- pfSense installed and reachable
- A VLAN or internal network interface configured for the captive portal

Steps

1. In pfSense web UI go to Services → Captive Portal and click Add.
2. Create a Zone name (for example `Human_Res`) and enable the portal on the appropriate interface.
3. Configure idle timeout, concurrent connections, bandwidth restrictions, and the authentication method. For simple labs, use the Local Database for authentication.
4. Create Groups: System → User Manager → Groups. Add a group for each department and give it the `User-Service: Captive Portal` privilege if needed.
5. Create Users: System → User Manager → Users. Add users and assign them to the correct groups.
6. Test login by connecting a client on the captive portal network. Check Status → Captive Portal to view current sessions.

Images are available in the repository under the original images folder for the captive portal guide.

