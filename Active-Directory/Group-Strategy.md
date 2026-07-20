# Group Strategy

The lab uses department-based security groups instead of assigning permissions directly to individual users.

## Naming

The naming convention keeps the department and access level visible:

```text
Department-Users
Department-Admins
```

Examples:

- `Finance-Users`
- `Finance-Admins`
- `Engineering-Users`
- `IT-Admins`

## Group Types

| Group Type | Example | Main Use |
|---|---|---|
| Department users | `Finance-Users` | Department resources and drive targeting |
| Department admins | `Finance-Admins` | Elevated access to department resources |
| IT administrators | `IT-Admins` | Approved workstation administration |
| Domain administrators | `Domain Admins` | Domain-level administration |

## Where the Groups Are Used

- Department share permissions are documented in [NTFS Permissions](../File-Server/NTFS-Permissions.md).
- Drive-map targeting is documented in [Drive Mapping](../Group-Policy/Drive-Mapping.md).
- Standard-user restriction scope is documented in [Department Group Policies](../Group-Policy/department-policies.md).
- The overall access model is documented in [Role-Based Access Control](../Security/Role-Based-Access-Control.md).
- Local administrator control is documented in [Least Privilege](../Security/Least-Privilege.md).

This file is limited to the group structure so the same drive, GPO, and permission details are not maintained in several places.