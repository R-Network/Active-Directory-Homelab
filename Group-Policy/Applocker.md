# AppLocker

AppLocker is configured in the `Company Workstation Baseline` GPO to control approved executable use while still allowing required administrative tooling for IT and Engineering.

## Current Enforcement State

| Rule Collection         | Status           |
|---|---|
| Executable Rules        | Enforced         |
| Script Rules            | Not enforced     |
| Windows Installer Rules | No rules defined |
| DLL Rules               | No rules defined |
| Appx Rules              | No rules defined |

Script rules are intentionally not enforced because no script rules are currently defined. This prevents the VM from breaking while still allowing executable rule testing.

## Executable Rules

Configured allow rules include:

| Action | User/Group                  | Rule |
|---|---|---|
| Allow  | `HOMELAB\IT-Users`          | Allow PowerShell - IT Only                    |
| Allow  | `HOMELAB\Engineering-Users` | Allow PowerShell - Engineers Only             |
| Allow  | Everyone                    | All files located in the Windows folder       |
| Allow  | Everyone                    | All files located in the Program Files folder |
| Allow  | BUILTIN\Administrators      | All files                                     |

## Exceptions

PowerShell access is granted to:

- HOMELAB\IT-Users
- HOMELAB\Engineering-Users

## Notes

- Script rules should remain not enforced until proper script allow rules are created and tested.
- Default executable rules should remain in place to prevent Windows components from being blocked.