# Infrastructure & Connectivity

## Scope

This section documents the infrastructure and connectivity work completed during the current stage of the POC.

## Technologies involved

- Qlik Talend Cloud
- Virtual machine / integration environment
- AWS
- Azure SQL Database
- Microsoft SQL Server
- MySQL

## Work completed

- Prepared the integration environment required for connectivity testing.
- Worked with a virtual machine as part of the integration architecture.
- Configured source and target database connections in Qlik Talend Cloud.
- Validated network/database connectivity across the technologies used in the POC.
- Diagnosed and corrected connectivity issues encountered during setup.
- Confirmed that the required environments could participate in Qlik Data Movement scenarios.

## Connectivity validation approach

The implementation followed a staged validation process:

```text
Environment available
        ↓
Database/service reachable
        ↓
Credentials and permissions validated
        ↓
Qlik connection configured
        ↓
Connection tested
        ↓
Data Movement configured
        ↓
Transfer validated
```

## Public portfolio note

Connection strings, credentials, IP addresses, tenant information, server names, ports specific to the client, and internal network details are intentionally excluded from this repository.
