# Least Privilege

The environment follows least privilege by limiting administrative rights to approved administrative groups and using department groups for resource access.

## Local Administrator Control

The `Company Workstation Baseline` GPO manages the local Administrators group on workstations.

Current configuration:
- Action = Update
- Group name = Administrators (built in)
- Delete all member users = Enabled
- Delete all member groups = Enabled
  
Added members:
- HOMELAB\IT-Admins
- HOMELAB\Domain Admins

## Purpose

This removes unmanaged local admin users and groups and adds back only approved administrative groups.

## Standard Users

Department users should not be local administrators on workstations.

Examples of groups that should not be in local Administrators:

- Domain Users
- Authenticated Users
- Finance-Users
- HR-Users
- Engineering-Users
- Sales-Users

## Admin Separation

Administrative tasks should use admin groups/accounts such as:

- Domain Admins
- IT-Admins

Daily user accounts should remain standard users.