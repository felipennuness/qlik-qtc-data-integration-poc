# Qlik Data Movement

## Current milestone: working

The principal technical milestone reached so far in this POC is successful **Qlik Data Movement from an on-premises MySQL database to Azure SQL Database**.

## Work completed

- Configured the MySQL on-premises source connection in Qlik Talend Cloud.
- Configured the Azure SQL Database destination connection.
- Defined the source-to-target Data Movement flow.
- Executed data movement from MySQL to Azure.
- Confirmed successful transfer at the current POC stage.
- Validated the moved data in the Azure destination.
- Troubleshot connectivity and configuration issues during implementation.

## Validated flow

```text
MySQL On-Premises
      ↓
Source Connectivity
      ↓
Qlik Talend Cloud
      ↓
Qlik Data Movement
      ↓
Azure SQL Database
      ↓
Target Validation
```

## AWS + Apache Iceberg exploration

A separate AWS + Apache Iceberg destination scenario was configured/explored during the project. This alternative was **not finalized because of the additional infrastructure cost for the POC**.

It should therefore be understood as an architectural exploration rather than a completed data movement path.

## Why this stage matters

Before building downstream transformations, pipelines, analytics, reporting, or AI-assisted use cases, the architecture first needed to reliably move data from the on-premises operational source into a cloud destination.

The successful MySQL-to-Azure flow establishes that foundation.

## Next technical step

The next phase is to expand beyond the validated movement into **pipeline/orchestration and transformation scenarios**. These remain roadmap items until they are implemented and technically validated.
