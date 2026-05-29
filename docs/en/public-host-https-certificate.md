# Public Host, HTTPS and Certificates

PassMan starts on a local HTTP port by default. A controlled DNS name and HTTPS are recommended for production use.

## Host and Port

Set the public host and port in the Server System screen.

Examples:

```text
passman.company.local
vault.example.com
```

Default port:

```text
1903
```

## Certificate

When HTTPS is enabled, PassMan must be given a certificate package it can read. The operator provides the certificate file directly; PassMan does not require a separate certificate-source selection flow.

Supported package type:

```text
PFX / P12
```

Security notes:

- Do not upload certificate private keys to this public repository or logs.
- Store the certificate file on the server with restricted ACLs.
- The certificate subject/SAN should match the host users open in the browser.

## Verify

1. The host name resolves to the PassMan server.
2. The port is allowed by firewall policy.
3. The certificate matches the host name.
4. The browser opens `https://<HOST>:<PORT>` without warnings.
