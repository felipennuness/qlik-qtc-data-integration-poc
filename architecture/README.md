# Architecture

## Purpose

This section documents the architecture of the Qlik Talend Cloud data integration POC across its validated and current test stages.

The public documentation intentionally abstracts client-specific details while preserving the real technical flow that was implemented and the next environment being prepared.

## Phase 1 — Validated architecture

```text
+-----------------------------+
| On-Premises Environment     |
|-----------------------------|
| MySQL Database              |
| Operational Source          |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Data Gateway / VM      |
| Connectivity Environment    |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Talend Cloud           |
| Connection Configuration    |
+-------------+---------------+
              |
              v
+-----------------------------+
| Initial Load + CDC          |
| Change Data Capture         |
+-------------+---------------+
              |
              v
+-----------------------------+
| Qlik Data Movement          |
| Incremental Replication     |
+-------------+---------------+
              |
              v
+-----------------------------+
| Azure SQL Database          |
| Validated Destination       |
+-------------+---------------+
              |
              v
+-----------------------------+
| Validation                  |
+-----------------------------+
```

This **MySQL on-premises → Azure SQL Database** flow is the architecture validated as working in Phase 1.

### CDC role in the architecture

The replication design uses **CDC (Change Data Capture)** after the initial load so changes in the operational MySQL source can be captured and propagated incrementally to the destination.

This avoids treating each source change as a reason to reload the complete dataset. The POC validates the functional replication behavior; it does not claim a production latency SLA or strict real-time guarantee.

## Phase 2 — Current test direction

To continue the POC with lower infrastructure cost, the next test architecture will use **SQL Server as the destination** while keeping MySQL on-premises as the source.

The main purpose of this phase is to configure and validate **Qlik Talend Cloud pipelines, orchestration, transformations, and continued CDC/incremental replication tests**.

```text
MySQL On-Premises
      |
      v
Qlik Data Gateway / VM
      |
      v
Qlik Talend Cloud
      |
      v
Data Movement / CDC / Pipeline Tests
      |
      v
SQL Server
```

This phase must not be described as fully implemented until the SQL Server destination and pipeline behavior have been technically validated.

## Alternative architecture explored

A separate path using **AWS + Qlik Open Lakehouse + Apache Iceberg** was configured/explored during the POC. The Open Lakehouse configuration included a **CDC workload**.

It was not finalized because of the additional infrastructure cost required to continue that environment.

```text
MySQL On-Premises
      |
      v
Qlik Talend Cloud
      |
      v
Qlik Open Lakehouse / CDC
      |
      v
AWS + Apache Iceberg
      |
      v
Not finalized due to POC cost constraints
```

## Current boundary

- **Validated:** MySQL on-premises → Azure SQL Database through Qlik Data Movement with CDC/incremental replication
- **Current next test phase:** MySQL on-premises → SQL Server, focused on pipeline and continued CDC testing
- **Explored but not finalized:** AWS + Qlik Open Lakehouse + Apache Iceberg
- **Future stages:** Data Products, analytics consumption, Qlik Automate, Reporting, and Qlik Answers
