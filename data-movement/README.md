# Qlik Data Movement

## Current milestone: working

The principal technical milestone reached so far in this POC is successful **Qlik Data Movement from an on-premises MySQL database to Azure SQL Database**, including incremental change replication with **CDC (Change Data Capture)**.

## Source

The operational source is a **MySQL database running on-premises**. Qlik Data Gateway provides the integration layer required for Qlik Talend Cloud to access and replicate data from this environment.

## Work completed

- Configured the MySQL on-premises source connection in Qlik Talend Cloud.
- Configured the Azure SQL Database destination connection.
- Defined the source-to-target Data Movement flow.
- Executed the initial data movement from MySQL to Azure.
- Configured and validated **CDC / incremental change replication** for subsequent source changes.
- Confirmed successful transfer at the current POC stage.
- Validated the moved data in the Azure destination.
- Troubleshot connectivity and configuration issues during implementation.

## Validated flow

```text
MySQL On-Premises
      ↓
Qlik Data Gateway
      ↓
Qlik Talend Cloud
      ↓
Initial Load + CDC
      ↓
Qlik Data Movement
      ↓
Azure SQL Database
      ↓
Target Validation
```

## CDC — Change Data Capture

CDC allows the integration flow to capture changes occurring in the source after the initial load and propagate them incrementally to the target.

In this POC, CDC is important because it demonstrates a replication pattern that avoids performing a complete reload every time operational data changes.

The portfolio does **not** claim a production latency SLA or strict real-time behavior. The documented result is the functional implementation and validation of incremental change replication in the proof of concept.

## AWS + Apache Iceberg exploration

A separate AWS + Apache Iceberg destination scenario was configured/explored during the project using Qlik Open Lakehouse. The exploration also included a **CDC workload**.

This alternative was **not finalized because of the additional infrastructure cost for the POC** and is therefore documented as architectural exploration rather than a completed data movement path.

## Why this stage matters

Before building downstream transformations, pipelines, analytics, reporting, or AI-assisted use cases, the architecture first needed to reliably move data from the on-premises operational source into a target environment and propagate subsequent changes incrementally.

The successful MySQL-to-Azure flow with CDC establishes that foundation.

## Next technical step

The next phase keeps **MySQL on-premises as the source** and uses **SQL Server as a lower-cost test destination** while the project advances into pipeline, orchestration, transformation, and continued CDC testing.
