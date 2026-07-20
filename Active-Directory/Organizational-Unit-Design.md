# Organizational Unit Design

The OU structure separates employees, groups, servers, and workstations so Group Policy can be linked to the correct type of object.

## OU Hierarchy

```text
Homelab.local
- Default Domain Controllers
- Employees
    - Contractors
    - Customer Service
    - Disabled Accounts
    - Engineering
    - Executive
    - Finance
    - HR
    - Interns
    - IT
    - Legal
    - Marketing
    - Operations
    - Sales
    - Warehouse
- Groups
- Servers
    - File Servers
- Workstations
    - Desktops
    - Laptops
```

## OU Purpose

| OU | Purpose |
|---|---|
| `Employees` | Parent OU for employee user accounts |
| Department OUs | Separate users for policy targeting and administration |
| `Disabled Accounts` | Holds disabled or separated user accounts |
| `Groups` | Stores domain security groups |
| `Servers` | Parent OU for server computer objects |
| `Servers/File Servers` | Stores file-server computer objects |
| `Workstations` | Parent OU for workstation computer objects |
| `Workstations/Desktops` | Desktop computer objects |
| `Workstations/Laptops` | Laptop computer objects |

## Policy Placement

- Domain account policies remain linked at the domain level.
- User policies are linked to `Employees` or a department OU.
- Computer policies are linked to `Workstations` or a workstation sub-OU.
- The exact scope of department restrictions is documented in [Department Group Policies](../Group-Policy/department-policies.md).