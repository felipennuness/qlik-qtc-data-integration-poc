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
+-------------+---------------+
              |
              v
+-----------------------------+
| Integration / VM Layer      |
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
| Qlik Data Movement          |
| Data Transfer               |
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

This MySQL on-premises → Azure SQL Database flow is the architecture currently validated as working.

## Phase 2 — Current test direction

To continue the POC with lower infrastructure cost, the next test architecture will use **SQL Server as the destination** while keeping MySQL on-premises as the source.

The main purpose of this phase is to configure and validate **Qlik Talend Cloud pipelines, orchestration, and transformation tests**.

```text
MySQL On-Premises
      |
      v
Integration / VM Layer
      |
      v
Qlik Talend Cloud
      |
      v
Data Movement / Pipeline Tests
      |
      v
SQL Server
```

This phase must not be described as fully implemented until the SQL Server destination and pipeline behavior have been technically validated.

## Alternative architecture explored

A separate path using **AWS + Apache Iceberg** was configured/explored during the POC, but it was not finalized because of the additional infrastructure cost required to continue that environment.

```text
MySQL On-Premises
      |
      v
Qlik Talend Cloud
      |
      v
AWS + Apache Iceberg
      |
      v
Not finalized due to POC cost constraints
```

## Current boundary

- **Validated:** MySQL on-premises → Azure SQL Database through Qlik Data Movement
- **Current next test phase:** MySQL on-premises → SQL Server, focused on pipeline testing
- **Explored but not finalized:** AWS + Apache Iceberg
- **Future stages:** Data Products, analytics consumption, Qlik Automate, Reporting, and Qlik Answers
