# DHCP for the Cisco CML Lab

The Windows DHCP server at `192.168.216.240` also provides addresses to routed client VLANs in Cisco CML.

## Scopes

| VLAN | Use | Network | Lease Range | Gateway |
|---:|---|---|---|---|
| 10 | Users | `10.10.10.0/24` | `10.10.10.50`–`10.10.10.200` | `10.10.10.1` |
| 30 | IT | `10.10.30.0/24` | `10.10.30.50`–`10.10.30.200` | `10.10.30.1` |
| 40 | Guest | `10.10.40.0/24` | `10.10.40.50`–`10.10.40.200` | `10.10.40.1` |

The clients receive `192.168.216.240` as their DNS server.

- [DHCP scopes in Windows Server](../Screenshots/Active-Directory/dhcp-scopes-overview.png)

## DHCP Relay

The VLANs are routed by the Cisco core switch, so the switch forwards the broadcasts to Windows Server:

```cisco
interface Vlan10
 ip helper-address 192.168.216.240

interface Vlan30
 ip helper-address 192.168.216.240

interface Vlan40
 ip helper-address 192.168.216.240
```

## Return-Path Issue

The DHCP requests reached Windows Server, but the server initially had no route back to the CML subnets.

I added this persistent route on Windows:

```powershell
route -p add 10.10.0.0 mask 255.255.0.0 192.168.216.140
```

`192.168.216.140` was the CML edge router's address on the VMware network. Once the return route was in place, the clients began receiving leases.