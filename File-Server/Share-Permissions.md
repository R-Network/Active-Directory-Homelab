# Share Permissions

Share permissions provide the first layer of access control for SMB shares. NTFS permissions provide the detailed security model.

## Recommended Share Permission Design

| Share             | Principal | Permission |
|---|---|---|
| Department Shares | Authenticated Users or Domain Users | Change/Read                              |
| Department Shares | Domain Admins                       | Full Control                             |
| Department Shares | IT-Admins                           | Full Control                             |
| User Home Folders | Authenticated Users or Domain Users | Change/Read                              |
| Public Share      | Authenticated Users                 | Change/Read or Read, depending on design |

## Notes

- Use NTFS permissions for precise department access.
- Avoid granting broad Full Control to regular users.
- Department access should be controlled through groups such as `Finance-Users` and `Finance-Admins`.