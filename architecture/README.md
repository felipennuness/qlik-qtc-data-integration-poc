# Architecture

## Purpose

This section documents the architecture of the Qlik Talend Cloud data integration POC at its **current validated stage**.

The public documentation intentionally abstracts client-specific details while preserving the real technical flow that was implemented.

## Validated architecture

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
| Cloud Destination           |
+-------------+---------------+
              |
              v
+-----------------------------+
| Validation                  |
+-----------------------------+
```

## Alternative architecture explored

A second path using **AWS + Apache Iceberg** was configured/explored during the POC, but it was not finalized because of the additional infrastructure cost required to continue that environment.

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

The architecture currently validated in the project ends with successful **Data Movement from MySQL on-premises to Azure SQL Database**.

The AWS + Iceberg path is documented only as an explored alternative. Pipeline orchestration, transformation, Data Products, analytics, automation, reporting, and Qlik Answers remain future stages until they are actually implemented and validated.
