# Windows Defender Firewall

Windows Defender Firewall is centrally managed through the `Company Workstation Baseline` GPO.

## Profile Configuration

| Profile | Firewall State | Inbound | Outbound | Notifications | Unicast Responses |
|---|---|---|---|---|---|
| Domain  | On             | Block   | Allow    | No            | No                |
| Private | On             | Block   | Allow    | Yes           | No                |
| Public  | On             | Block   | Allow    | No            | No                |

## Logging Configuration

Firewall logging is implemented for all workstation firewall profiles.

| Profile | Log Dropped Packets | Log Successful Connections | Log Path | Max Size |
|---|---|---|---|---|
| Domain  | Yes | No | `%systemroot%\system32\logfiles\firewall\pfirewall.log` | 16384 KB |
| Private | Yes | No | `%systemroot%\system32\logfiles\firewall\pfirewall.log` | 16384 KB |
| Public  | Yes | No | `%systemroot%\system32\logfiles\firewall\pfirewall.log` | 16384 KB |

## Benefits

- Reduces unauthorized inbound access.
- Provides centralized firewall enforcement.
- Logs dropped packets for troubleshooting and security review.