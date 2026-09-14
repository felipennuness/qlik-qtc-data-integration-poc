# Verified Project Scope

This file is the source of truth for the public portfolio documentation of this ongoing Qlik Talend Cloud POC.

## Validated implementation

- Source: **MySQL running on-premises**
- Integration platform: **Qlik Talend Cloud (QTC)**
- Data integration capability: **Qlik Data Movement**
- Validated destination: **Azure SQL Database**
- Supporting environment: **Virtual machine / integration environment**
- Validated result: **MySQL on-premises → Azure SQL Database Data Movement is working**
- Data transfer and target validation were performed successfully
- Connectivity/configuration troubleshooting was part of the implementation

## Current next phase

- Keep **MySQL on-premises** as the source
- Use **SQL Server as the test destination**
- Reason for the destination change: reduce infrastructure cost while continuing the POC
- Main technical goal: configure and validate **pipeline / orchestration tests** in Qlik Talend Cloud

SQL Server must be described as the destination for the current/next testing phase until the new flow and pipeline behavior are technically validated.

## Explored but not finalized

- **AWS** environment
- **Apache Iceberg** destination scenario
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
