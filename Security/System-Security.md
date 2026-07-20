# System Security

Workstation security is mainly applied through the `Company Workstation Baseline` GPO.

## Detailed Controls

| Area | Documentation |
|---|---|
| Microsoft Defender | [Defender](../Group-Policy/Defender.md) |
| Windows Defender Firewall | [Firewall](../Group-Policy/Firewall.md) |
| Advanced auditing | [Audit Policy](../Group-Policy/audit-policy.md) |
| Application control | [AppLocker](../Group-Policy/Applocker.md) |
| Removable storage | [USB Restrictions](../Group-Policy/usb-restrictions.md) |
| Local administrator control | [Least Privilege](Least-Privilege.md) |
| Baseline GPO settings | [Baseline Policies](../Group-Policy/Baseline-Policies.md) |

## Deferred Controls

These controls are not presented as fully implemented:

- BitLocker
- Credential Guard / VBS
- AppLocker script-rule enforcement

Credential Guard/VBS caused problems when signing out of a domain account on Windows 10/11 Professional virtual machines. AppLocker script enforcement is also deferred until script allow rules are created and tested.