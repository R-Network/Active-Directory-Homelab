# USB Device Restrictions

USB removable storage restrictions are configured in the `Company Workstation Baseline` GPO to reduce data exfiltration and malware risk.

## Current Configuration

| Setting                                        | Status  |
|---|---|
| All Removable Storage classes: Deny all access | Enabled |

## Notes

The current configuration blocks access to all removable storage classes. It does not document separate write only restrictions or IT exceptions.

## Benefits

- Reduces unauthorized data transfer.
- Reduces malware introduction from removable media.
- Supports least privilege workstation security.