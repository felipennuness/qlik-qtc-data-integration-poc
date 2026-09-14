# Challenges & Technical Decisions

This document summarizes the technical decisions made during the current Qlik Talend Cloud proof of concept. It reflects only work that has actually been performed or explicitly planned in the project.

## 1. Connecting an on-premises source to Qlik Cloud

The project source is a **MySQL database running on-premises**. Before any cloud data movement could be validated, the integration environment had to provide reliable connectivity between the local database and Qlik Talend Cloud.

### Work performed

- Prepared the virtual machine / integration environment.
- Installed and configured the Qlik Data Gateway for Data Movement.
- Validated that the gateway service was running correctly.
- Configured and tested the MySQL source connection.
- Troubleshot connectivity and configuration issues before enabling replication.

## 2. First validated destination: Azure SQL Database

The first end-to-end data movement flow used **Azure SQL Database** as the cloud destination.

### Validated flow

```text
MySQL On-Premises
        ↓
Qlik Data Gateway / Integration Environment
        ↓
Qlik Talend Cloud
        ↓
Qlik Data Movement
        ↓
Azure SQL Database
```

The replication flow was created and executed successfully, and the transferred data was validated directly in Azure SQL Database.

## 3. AWS + Apache Iceberg exploration

A second architecture was explored using **AWS infrastructure with Qlik Open Lakehouse / Apache Iceberg**.

The exploration included work around:

- AWS VPC and subnet configuration
- Qlik network integration
- IAM roles
- S3 storage preparation
- KMS configuration
- Qlik Open Lakehouse cluster creation
- CDC-oriented lakehouse workload configuration

The AWS/Iceberg path was **not finalized** because continuing the required infrastructure for the POC would increase cost. It remains an explored architecture rather than a completed implementation.

## 4. Current direction: SQL Server for pipeline testing

To continue the POC while controlling infrastructure cost, the next test destination is **Microsoft SQL Server**.

The objective of this phase is to use SQL Server as a lower-cost test target while progressing into:

- pipeline configuration
- pipeline orchestration
- transformation scenarios
- downstream validation

This phase is currently the next technical milestone and must not be described as completed until it has been implemented and validated.

## 5. Documentation principle

This portfolio distinguishes three states clearly:

- **Validated:** implemented and technically verified in the project.
- **Explored:** configured or investigated but not completed end to end.
- **Planned / in progress:** intended next steps that are not yet validated.

This distinction is maintained throughout the repository so the public case study remains technically accurate.
