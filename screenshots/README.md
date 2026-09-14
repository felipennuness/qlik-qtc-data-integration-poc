# Screenshot Guidelines

This folder will contain sanitized screenshots that demonstrate the technical implementation without exposing confidential client information.

## Good screenshots to add

- Qlik Talend Cloud Data Movement overview with sensitive identifiers hidden
- Connection configuration screens with credentials, hostnames, IPs, tenant IDs, and database names redacted
- Successful movement / task status screens
- High-level AWS or database architecture views using generic names
- Validation results using synthetic or anonymized data

## Never publish

- Passwords, API keys, tokens, certificates, or connection strings
- Public or private IP addresses tied to the client
- Real server or database names that expose internal infrastructure
- Customer or employee data
- Internal URLs or tenant identifiers
- Proprietary documents or screenshots with confidential business information

## Naming convention

Use descriptive file names such as:

```text
01-qtc-data-movement-overview.png
02-connection-validation-redacted.png
03-data-movement-success.png
04-architecture-sanitized.png
```

Every screenshot should be reviewed and sanitized before being committed to this public repository.
