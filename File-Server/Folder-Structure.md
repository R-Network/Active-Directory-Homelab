# File Server Folder Structure

## Folder Layout

```text
VM-FILESERVER
- SHARES
    - Departments
        - Engineering
        - Finance
        - HR
        - IT
        - Marketing
        - Operations
        - Sales
- Users
    - %username%
- Public
```

## Notes

- Department folders are stored under `\\VM-FILESERVER\SHARES`.
- User home folders are stored under `\\VM-FILESERVER\Users`.
- The public share is stored at `\\VM-FILESERVER\Public`.
- Drive mappings use Group Policy Preferences.