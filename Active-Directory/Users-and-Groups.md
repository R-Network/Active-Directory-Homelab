# Users and Groups

Users are stored in department OUs and assigned to department security groups.

## Department Groups

| Department | User Group | Admin Group |
|---|---|---|
| Contractors | `Contractors-Users` | `Contractors-Admins` |
| Customer Service | `Customer-Service-Users` | `Customer-Service-Admins` |
| Engineering | `Engineering-Users` | `Engineering-Admins` |
| Executive | `Executive-Users` | `Executive-Admins` |
| Finance | `Finance-Users` | `Finance-Admins` |
| HR | `HR-Users` | `HR-Admins` |
| Interns | `Interns-Users` | `Interns-Admins` |
| IT | `IT-Users` | `IT-Admins` |
| Legal | `Legal-Users` | `Legal-Admins` |
| Marketing | `Marketing-Users` | `Marketing-Admins` |
| Operations | `Operations-Users` | `Operations-Admins` |
| Sales | `Sales-Users` | `Sales-Admins` |
| Warehouse | `Warehouse-Users` | `Warehouse-Admins` |

## Administrative Groups

| Group | Purpose |
|---|---|
| `Domain Admins` | Domain-level administration |
| `Enterprise Admins` | Forest-level administration |
| `IT-Admins` | Approved workstation administration |
| `IT-Users` | Standard IT department membership |
| `Engineering-Users` | Engineering membership and approved technical-tool access |

Detailed permission assignments are documented separately:

- [Group Strategy](Group-Strategy.md)
- [Role-Based Access Control](../Security/Role-Based-Access-Control.md)
- [Least Privilege](../Security/Least-Privilege.md)

## Zammad Integration

Active Directory is the identity source for users imported into Zammad.

See [Zammad LDAP Integration](../Infrastructure-Services/Zammad-LDAP.md) for synchronization and role details.
