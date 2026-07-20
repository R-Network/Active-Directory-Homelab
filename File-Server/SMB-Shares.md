# SMB Shares

SMB shares provide centralized network storage for departments, users, and shared public resources.

## Shares

| Share             | UNC Path                                            | Purpose                 |
|---|---|---|
| Department Shares | `\\VM-FILESERVER\SHARES\Departments\DepartmentName` | Department file storage |
| User Home Folders | `\\VM-FILESERVER\Users\%username%`                  | Personal user storage   |
| Public Share      | `\\VM-FILESERVER\Public`                            | Shared public files     |

## Department Share Examples

- \\VM-FILESERVER\SHARES\Departments\Engineering
- \\VM-FILESERVER\SHARES\Departments\Finance
- \\VM-FILESERVER\SHARES\Departments\HR
- \\VM-FILESERVER\SHARES\Departments\IT
- \\VM-FILESERVER\SHARES\Departments\Marketing
- \\VM-FILESERVER\SHARES\Departments\Operations
- \\VM-FILESERVER\SHARES\Departments\Sales

## Notes

Access to SMB shares is controlled through domain security groups and NTFS permissions.