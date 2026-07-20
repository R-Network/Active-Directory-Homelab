# Department Group Policies

Department configuration currently uses shared GPOs and targeted settings instead of a separate full GPO for every department.

## Current Implementation

| Policy | Scope | Purpose |
|---|---|---|
| Company User Baseline | Employees OU | Shared user environment settings |
| Drive Maps | Employees OU | Department and home drives targeted by group |
| Standard User Restrictions | Selected department OUs | Restrictions for standard users |
| Company Workstation Baseline | Workstations OU | Shared workstation security |
| IT Workstation Admin Access | IT workstation OU | IT administration and remote access |

## Standard User Restrictions

The restrictions GPO is linked to:

- Contractors
- Customer Service
- Executive
- Finance
- HR
- Interns
- Legal
- Marketing
- Operations
- Sales
- Warehouse

It is not linked to:

- Engineering
- IT

Engineering and IT require Command Prompt, PowerShell, Registry Editor, and other technical tools that are restricted for standard departments.

## Drive Targeting

Department drives use security-group item-level targeting. The complete drive-letter and group table is maintained in [Drive Mapping](Drive-Mapping.md).

## Future Department Policies

Separate department GPOs may be added later for requirements such as printers, browser favorites, shortcuts, and department-specific restrictions.
