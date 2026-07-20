# Home Drive Design

Each user receives a personal home drive that is separate from the department shares.

## Mapping

| Drive | Path | Label |
|---|---|---|
| `Z:` | `\\VM-FILESERVER\Users\%username%` | User Home Folder |

`Z:` was selected so it would not conflict with department drive letters. The HR department already uses `H:`.

## Access Design

Each home folder is intended for the assigned user and approved administrators only. The exact ACL entries are maintained in [NTFS Permissions](../File-Server/NTFS-Permissions.md).

The mapping itself is deployed through the [Drive Maps GPO](../Group-Policy/Drive-Mapping.md).