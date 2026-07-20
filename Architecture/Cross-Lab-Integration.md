# Cross-Lab Integration

The Active Directory project started as a Windows-only lab, but it now provides services to the Zammad and Cisco CML projects.

```text
Windows clients
├── Active Directory authentication
├── Group Policy
├── DNS
├── NTP
└── SMB file shares

Cisco CML clients
├── DHCP from Windows Server
├── DNS from Windows Server
└── NTP from Windows Server

Zammad on Ubuntu
└── LDAP user import and synchronization

LibreNMS on Ubuntu
├── DNS record in Homelab.local
└── HTTPS certificate from Homelab-Root-CA
```

## Main Addresses

| Service | Address or Name |
|---|---|
| Windows Server | `192.168.216.240` |
| FILE01 | `192.168.216.133` |
| Zammad | `192.168.216.242` |
| LibreNMS | `192.168.216.139` |
| LibreNMS hostname | `librenms.homelab.local` |
| CML edge router on VMware network | `192.168.216.140` during testing |

Connecting the labs gave me more useful troubleshooting practice than keeping them separate. DHCP required routing in both directions, Zammad required LDAP and application-role mapping, and LibreNMS required DNS, certificate issuance, Linux file permissions, and Nginx configuration.

## Related Screenshots

- [DHCP scopes](../Screenshots/Active-Directory/dhcp-scopes-overview.png)
- [DNS records](../Screenshots/Active-Directory/dns-records.png)
- [Issued certificates](../Screenshots/Active-Directory/issued-certificates.png)