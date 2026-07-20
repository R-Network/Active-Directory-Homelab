# NTFS Permissions

NTFS permissions control actual file and folder access on the file server.

## Department Share Permissions

Example: Finance folder

- Folder: \\VM-FILESERVER\SHARES\Departments\Finance

| Principal        | Permission             |
|---|---|
| `Finance-Users`  | Modify                 |
| `Finance-Admins` | Full Control or Modify |
| `Domain Admins`  | Full Control           |
| `IT-Admins`      | Full Control           |
| `SYSTEM`         | Full Control           |

## User Home Folder Permissions

Example:

- Folder: \\VM-FILESERVER\Users\%username%

| Principal       | Permission   |
|---|---|
| User accounts   | Modify       |
| `Domain Admins` | Full Control |
| `IT-Admins`     | Full Control |
| `SYSTEM`        | Full Control |

## Public Folder Permissions

Example:

- Folder: \\VM-FILESERVER\Public

| Principal | Permission                                       |
|---|---|
| Authenticated Users    | Read or Modify, depending on policy |
| `Domain Admins`        | Full Control                        |
| `IT-Admins`            | Full Control                        |
| `SYSTEM`               | Full Control                        |

## Permission Notes

- Department users should only access their department folder.
- Home folders should not be browsable by other users.
- Administrative groups should retain recovery/management access.
- Avoid assigning permissions directly to individual users except for home folders.