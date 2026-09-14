# Verified Project Scope

This file is the source of truth for the public portfolio documentation of this ongoing Qlik Talend Cloud POC.

## Validated implementation

- Operational source: **MySQL running on-premises**
- Integration platform: **Qlik Talend Cloud (QTC)**
- On-premises integration layer: **Qlik Data Gateway / VM environment**
- Data integration capability: **Qlik Data Movement**
- Replication pattern: **Initial load + CDC (Change Data Capture)**
- Validated destination: **Azure SQL Database**
- Validated result: **MySQL on-premises → Azure SQL Database Data Movement is working**
- Incremental source changes were propagated using CDC during the POC validation
- Data transfer and target validation were performed successfully
- Connectivity/configuration troubleshooting was part of the implementation

No production latency SLA or strict real-time performance claim should be made from this POC.

## Current next phase

- Keep **MySQL on-premises** as the source
- Use **SQL Server as the test destination**
- Reason for the destination change: reduce infrastructure cost while continuing the POC
- Main technical goal: configure and validate **pipeline / orchestration tests** in Qlik Talend Cloud
- Continue validating incremental replication / CDC behavior as the test architecture evolves

SQL Server must be described as the destination for the current/next testing phase until the new flow and pipeline behavior are technically validated.

## Explored but not finalized

- **AWS** environment
- **Qlik Open Lakehouse**
- **Apache Iceberg** destination scenario
- CDC workload configuration/exploration in the Open Lakehouse architecture
- Reason not finalized: additional infrastructure cost for the proof of concept

This path must not be described as a completed data movement implementation.

## Future stages after pipeline validation

- Additional transformation / preparation scenarios
- Data Products
- Qlik Cloud analytical consumption for this POC
- Qlik Automate
- Reporting workflows
- Qlik Answers

## Documentation rule

Public documentation should only describe an item as implemented or working when it has been technically completed and validated in the real project. Current test directions, explored alternatives, and planned features must always be labeled separately.
