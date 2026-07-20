# Zammad LDAP Integration

Zammad runs on Ubuntu at `192.168.216.242`.

I connected it to `Homelab.local` so directory users could be imported and synchronized instead of being created again inside Zammad.

## Current Status

- The LDAP connection works.
- Domain users can be imported.
- Directory changes can be synchronized.
- Active Directory remains the source for the user account information.

The first imported users showed up as customers. Zammad treats the directory account and the application role as separate things, so importing an account does not automatically make it an agent or administrator.

The next step is to map selected Active Directory groups to the correct Zammad roles.

LDAP bind credentials and passwords are not stored in this repository.