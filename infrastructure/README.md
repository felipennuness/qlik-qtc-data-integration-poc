# Infrastructure & Connectivity

## Scope

This section documents the infrastructure and connectivity work completed during the current stage of the POC.

## Validated environment

- **Qlik Talend Cloud**
- **Virtual machine / integration environment**
- **MySQL on-premises** as the source
- **Azure SQL Database** as the destination

## Work completed

- Prepared the integration environment required for the POC.
- Worked with a virtual machine as part of the integration architecture.
- Configured the on-premises MySQL source connection.
- Configured the Azure SQL Database destination connection.
- Validated connectivity between the on-premises environment, Qlik Talend Cloud, and Azure.
- Diagnosed and corrected connectivity/configuration issues encountered during setup.
- Confirmed that the environment supported the required MySQL-to-Azure Data Movement flow.

## Connectivity validation approach

```text
On-Premises MySQL available
        ↓
Source connectivity validated
        ↓
Qlik Talend Cloud connection configured
        ↓
Azure SQL Database connection configured
        ↓
Source and target tested
        ↓
Data Movement configured
        ↓
Transfer to Azure validated
```

## AWS + Apache Iceberg

An alternative AWS architecture using Apache Iceberg was also configured/explored. It was not finalized because maintaining the required AWS resources would add cost to the proof of concept.

This AWS path is therefore not represented as part of the completed production-ready flow.

## Public portfolio note

Connection strings, credentials, IP addresses, tenant information, server names, client-specific ports, database names, and internal network details are intentionally excluded from this repository.
