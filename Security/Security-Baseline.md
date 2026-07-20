# Security Baseline

The security baseline is split between domain-level account controls and workstation-level endpoint controls.

## Domain Controls

Password, account lockout, Kerberos, LDAP signing, and SMB signing settings are configured through the domain policies.

The exact values are documented in [Baseline Group Policies](../Group-Policy/Baseline-Policies.md).

## Workstation Controls

Workstation hardening is applied through `Company Workstation Baseline`.

Detailed status and links are maintained in [System Security](System-Security.md), with separate files for Defender, firewall, auditing, AppLocker, and USB restrictions.

## Administration and Access

- Local administrator management: [Least Privilege](Least-Privilege.md)
- Department and role access: [Role-Based Access Control](Role-Based-Access-Control.md)
- Internal certificate services: [Internal Certificate Authority](../Infrastructure-Services/Internal-Certificate-Authority.md)

This file is an overview of the baseline rather than a second copy of every configured setting.