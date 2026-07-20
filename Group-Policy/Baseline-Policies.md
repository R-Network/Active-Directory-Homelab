# Baseline Group Policies

Baseline policies define common security and configuration settings for the domain, users, and workstations.

## Domain-Level Baseline

Configured in `Default Domain Policy`.

### Password Policy

| Setting                  | Value                  |
|---|---|
| Enforce password history | 3 passwords remembered |
| Maximum password age     | 90 days                |
| Minimum password age     | 1 day                  |
| Minimum password length  | 12 characters          |
| Password complexity      | Enabled                |
| Reversible encryption    | Disabled               |

### Account Lockout Policy

| Setting                   | Value              |
|---|---|
| Account lockout threshold | 3 invalid attempts |
| Account lockout duration  | 30 minutes         |
| Reset lockout counter     | 30 minutes         |

### Kerberos Policy

| Setting                         | Value       |
|---|---|
| Enforce user logon restrictions | Enabled     |
| Maximum service ticket lifetime | 600 minutes |
| Maximum user ticket lifetime    | 10 hours    |
| Maximum user ticket renewal     | 7 days      |
| Clock synchronization tolerance | 5 minutes   |

## Company User Baseline

Applied to:

- Homelab.local/Employees

Configuration side:

- User Configuration enabled
- Computer Configuration disabled

Includes:

- Enable screen saver.
- Password protect screen saver.
- Prevent changing desktop background.
- Company wallpaper.
- Microsoft Edge first run page disabled.
- File Explorer recent search entries disabled.
- Registry preferences for user environment settings.

### Screen Lock Note

- Screen saver timeout policy = 900 seconds
- Registry ScreenSaveTimeOut = 900 seconds

## Company Workstation Baseline

Applied to:

- Homelab.local/Workstations

Configuration side:

- Computer Configuration enabled
- User Configuration disabled

Includes:

- Guest account disabled.
- Built in Administrator renamed to `IT-Administrator`.
- UAC settings enabled.
- SMB signing enabled.
- Machine inactivity lock set to 900 seconds.
- Firewall profiles enabled.
- Firewall dropped packet logging enabled.
- Advanced audit policy enabled.
- AppLocker executable rules enforced.
- AppLocker script rules not enforced.
- USB removable storage blocked.
- Defender AV enabled.
- Local Administrators cleanup enabled.