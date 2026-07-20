# Active Directory Homelab

I started this project to get hands-on experience with Windows Server instead of only studying the concepts. The first version was a basic domain with a few users and a joined workstation. Over time I added Group Policy, a separate file server, department permissions, home drives, DHCP, LDAP integration, and an internal certificate authority.

The domain now supports several parts of my homelab:

- Windows users and workstations
- Department file shares and home folders
- Zammad user synchronization through LDAP
- DHCP, DNS, and NTP for my Cisco CML network
- Internal certificates for services such as LibreNMS

## Lab Summary

| Component | Details |
|---|---|
| Domain | `Homelab.local` |
| Domain Controller | Windows Server 2019 |
| File Server | `VM-FILESERVER` |
| Clients | Windows 10/11 domain-joined workstations |
| Zammad | Ubuntu server at `192.168.216.242` |
| LibreNMS | Ubuntu server at `192.168.216.139` |
| Windows infrastructure server | `192.168.216.240` |

The Windows Server currently provides AD DS, DNS, DHCP, NTP, and Active Directory Certificate Services.

## Active Directory

Users, groups, computers, and servers are separated into OUs so policies and permissions can be applied without placing everything in the default containers.

- [OU design](Active-Directory/Organizational-Unit-Design.md)
- [Users and groups](Active-Directory/Users-and-Groups.md)
- [Group strategy](Active-Directory/Group-Strategy.md)
- [Active Directory screenshots](Screenshots/Active-Directory)

## Group Policy

The lab uses shared user and workstation baselines, a drive-mapping GPO, standard-user restrictions, and an IT workstation administration policy.

- [Group Policy design](Group-Policy/Group-Policy-Design.md)
- [Baseline policies](Group-Policy/Baseline-Policies.md)
- [Department policy targeting](Group-Policy/department-policies.md)

## File Server

`VM-FILESERVER` hosts department shares, user home folders, and a public share. Access is assigned through Active Directory groups, with drive mappings deployed through Group Policy Preferences.

- [File server documentation](File-Server/README.md)
- [NTFS permissions](File-Server/NTFS-Permissions.md)
- [Drive-mapping configuration](Group-Policy/Drive-Mapping.md)

## DHCP, DNS, and the CML Lab

Windows DHCP serves the user, IT, and guest VLANs in my Cisco CML project. The Cisco core switch relays the requests to `192.168.216.240`, and Windows DNS is supplied to the clients through the scope options.

The DHCP issue I encountered was caused by a missing return route from Windows Server to the CML networks.

- [DHCP and routing notes](Infrastructure-Services/DHCP-for-CML.md)
- [DHCP scopes screenshot](Screenshots/Active-Directory/dhcp-scopes-overview.png)
- [DNS records screenshot](Screenshots/Active-Directory/dns-records.png)

## Zammad LDAP

Zammad imports and synchronizes users from Active Directory through LDAP. Active Directory provides the identities, while Zammad manages the application roles.

- [Zammad LDAP integration](Infrastructure-Services/Zammad-LDAP.md)

## Internal Certificate Authority

Active Directory Certificate Services issues certificates for internal services. The first web certificate was created for the Ubuntu-hosted LibreNMS site at `librenms.homelab.local`.

- [Certificate authority notes](Infrastructure-Services/Internal-Certificate-Authority.md)
- [Issued certificates screenshot](Screenshots/Active-Directory/issued-certificates.png)

## Security

The lab includes domain account policies, workstation hardening, Defender, firewall enforcement, auditing, USB restrictions, AppLocker, least-privilege administration, and group-based resource access.

- [Security documentation](Security/README.md)

## Screenshots

Screenshots are separated into Active Directory, File Server, Group Policy, Security, and Validation folders.

- [Screenshot index](Screenshots/README.md)

## Repository Folders

```text
Active-Directory/
Architecture/
File-Server/
Group-Policy/
Infrastructure-Services/
Screenshots/
Security/
```

## Next Steps

The next major additions would be a second domain controller, DNS redundancy, better Zammad group-to-role mapping, and certificate auto-enrollment for domain computers.
