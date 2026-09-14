# Architecture

## Purpose

This section documents the architecture of the Qlik Talend Cloud data integration POC at its **current validated stage**.

The public documentation intentionally abstracts client-specific details while preserving the technical concepts involved in the implementation.

## Current architecture

```text
+-----------------------------+
| Database / Cloud Sources    |
|-----------------------------|
| SQL Server                  |
| MySQL                       |
| Azure SQL Database          |
| AWS Environment             |
+-------------+---------------+
              |
              v
+-----------------------------+
| Integration / VM Layer      |
| Connectivity & Environment  |
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
| Target Data Environment     |
+-------------+---------------+
              |
              v
+-----------------------------+
| Validation / Troubleshooting|
+-----------------------------+
```

## Design principles

- Keep source systems decoupled from analytical consumption layers.
- Validate connectivity before adding transformation complexity.
- Test data movement independently before advancing to downstream pipeline stages.
- Document technical milestones as they are implemented.
- Avoid exposing customer infrastructure or production credentials in public documentation.

## Current boundary

The architecture documented here ends at the successfully validated **Data Movement** stage.

Pipeline orchestration, transformation, Data Products, analytics, automation, reporting, and Qlik Answers are part of the future roadmap and are not represented as completed implementation.
