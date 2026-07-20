# Role-Based Access Control

Access is assigned through Active Directory security groups based on department membership and administrative role.

## Department Access

| Role or Department | Group | Main Access |
|---|---|---|
| Engineering | `Engineering-Users` | Engineering share and approved technical tools |
| Finance | `Finance-Users` | Finance share |
| HR | `HR-Users` | HR share |
| IT | `IT-Users` | IT share and technical tools |
| Marketing | `Marketing-Users` | Marketing share |
| Operations | `Operations-Users` | Operations share |
| Sales | `Sales-Users` | Sales share |

## Administrative Roles

| Group | Main Access |
|---|---|
| `Domain Admins` | Domain administration |
| `IT-Admins` | Approved workstation administration |

## Related Implementation

- Group naming and purpose: [Group Strategy](../Active-Directory/Group-Strategy.md)
- File permissions: [NTFS Permissions](../File-Server/NTFS-Permissions.md)
- Drive targeting: [Drive Mapping](../Group-Policy/Drive-Mapping.md)
- GPO scope: [Department Group Policies](../Group-Policy/department-policies.md)
- Local administrator enforcement: [Least Privilege](Least-Privilege.md)

Users should receive only the groups needed for their job or administrative function.