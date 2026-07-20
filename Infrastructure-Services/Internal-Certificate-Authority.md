# Internal Certificate Authority

I added Active Directory Certificate Services so internal websites could use certificates from a CA trusted inside the homelab. Even though the services connected to my CML environment were only accessible on the private network, I did not want to rely on unencrypted HTTP or browser warnings from self-signed certificates. I felt that leaving internal management websites unsecured was still an unnecessary risk, especially because they could contain device information, login credentials, and administrative data. Using an internal CA allowed me to encrypt the traffic and verify that I was connecting to the correct server.

## CA and Template

```text
CA: Homelab-Root-CA
Template display name: LibreNMS Web Server
Template name: LibreNMSWebServer
```

## LibreNMS Certificate

LibreNMS runs on Ubuntu at `192.168.216.139` and uses Nginx.

```text
Website: https://librenms.homelab.local
Certificate: /etc/nginx/ssl/librenms.crt
Private key: /etc/nginx/ssl/librenms.key
Nginx configuration: /etc/nginx/conf.d/librenms.conf
```

The DNS record, certificate subject, Nginx server name, certificate path, and private key path all had to match before HTTPS worked correctly.

- [Internal DNS records](../Screenshots/Active-Directory/dns-records.png)
- [Issued certificates](../Screenshots/Active-Directory/issued-certificates.png)

The Certification Authority console shows a certificate issued from the LibreNMS web server template and a separate Domain Controller certificate.

The private key is not included in the repository.

## Later Improvements

I would like to add certificate auto-enrollment for domain computers and use the CA for more internal services.