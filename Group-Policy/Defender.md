# Microsoft Defender

Microsoft Defender Antivirus is configured through the `Company Workstation Baseline` GPO.

## Implemented Settings

| Setting                                            | Status   |
|---|---|
| Allow antimalware service to remain running always | Enabled  |
| Turn off Microsoft Defender Antivirus              | Disabled |
| Monitor file and program activity                  | Enabled  |
| Scan all downloaded files and attachments          | Enabled  |
| Turn off real time protection                      | Disabled |

## Attack Surface Reduction

One ASR rule 

| Rule GUID                              | State | Meaning                                                 |
|---|---|---|
| `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` | `1`   | Block Office applications from creating child processes |