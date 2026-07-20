# Group Policy Design

The Active Directory environment uses a layered Group Policy design to separate domain security, user configuration, workstation security, drive mapping, and department restrictions.

This structure reduces policy overlap and makes troubleshooting easier.

## Current Group Policy Hierarchy

```text
Homelab.local
- Default Domain Policy
- Default Domain Controllers Policy
- Employees
    - Company User Baseline
    - Drive Maps
    - Contractors
        - Standard User Restrictions
    - Customer Service
        - Standard User Restrictions
    - Disabled Accounts
    - Engineering
    - Executive
        - Standard User Restrictions
    - Finance
        - Standard User Restrictions
    - HR
        - Standard User Restrictions
    - Interns
        - Standard User Restrictions
    - IT
    - Legal
        - Standard User Restrictions
    - Marketing
        - Standard User Restrictions
    - Operations
        - Standard User Restrictions
    - Sales
        - Standard User Restrictions
    - Warehouse
        - Standard User Restrictions
- Workstations
    - Company Workstation Baseline
    - Desktops
        - IT
            - IT Workstation Admin Access
    - Laptops
```

## Current GPOs

| GPO | Scope | Configuration Side | Purpose |
|---|---|---|---|
| Default Domain Policy             | Domain root           | Computer      | Password, account lockout, Kerberos,LDAP signing, SMB signing                                                                                                      |
| Company User Baseline             | Employees OU          | User only     | User desktop/environment baseline           |
| Drive Maps                        | Employees OU          | User only     | Department and home drive mappings          |
| Standard User Restrictions        | Restricted user OUs   | User only     | Restrict standard users                     |
| Company Workstation Baseline      | Workstations OU       | Computer only | Workstation security and security baseline |
| IT Workstation Admin Access       | IT workstation OU     | Computer only | IT workstation admin/remote access          |
| Default Domain Controllers Policy | Domain Controllers OU | Computer      | Domain controller security rights           |

## Design Rules

- Domain password, lockout, and Kerberos settings are kept at the domain level.
- User settings are kept in user GPOs.
- Computer settings are kept in workstation GPOs.
- `Company Workstation Baseline` has user settings disabled.
- `Company User Baseline` has computer settings disabled.
- Department restriction scope is maintained in [Department Group Policies](department-policies.md).
- Drive maps are controlled using item level targeting by security group.

## GPO Processing

Group Policy follows LSDOU order:

- Local
- Site
- Domain
- Organizational Unit

More specific OU linked GPOs can override broader policies when settings overlap.

## Current State Notes

The current implementation uses shared baseline and restriction GPOs. Dedicated department specific GPOs are not fully implemented for every department yet; they are planned future improvements where needed.