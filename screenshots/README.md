# Technical Evidence Screenshots

This page presents a curated set of **sanitized screenshots from the real project**. The purpose is to provide technical evidence of the implementation while protecting internal infrastructure, account information, personal data, and client-specific identifiers.

## 1. MySQL on-premises data source

![MySQL on-premises source](rc18_portfolio_screenshots_sanitized/38982d69-7d33-42ad-bb03-06d49bc3532d%20%281%29.jpeg)

This screenshot documents the **MySQL database used as the operational source** for the POC.

The source remains on-premises while Qlik Data Gateway and Qlik Talend Cloud provide the integration layer used to move and replicate data to the target environment.

## 2. Qlik Data Gateway running

![Qlik Data Gateway running](rc18_portfolio_screenshots_sanitized/01-qlik-data-gateway-running.jpg)

The Linux service for **Qlik Data Gateway – Data Movement** is active and running in the integration environment. This is evidence of the gateway/infrastructure layer used to enable the on-premises data movement scenario.

## 3. MySQL on-premises → Azure SQL replication flow

![MySQL to Azure replication](rc18_portfolio_screenshots_sanitized/02-mysql-to-azure-pipeline.jpg)

The Qlik replication flow represents the validated Phase 1 architecture:

```text
MySQL On-Premises → Qlik Data Gateway → Qlik Talend Cloud / Data Movement → Azure SQL Database
```

The replication design includes **CDC (Change Data Capture)** so subsequent changes in the source can be propagated incrementally after the initial load.

Internal connection and project names were replaced with generic portfolio labels.

## 4. Azure SQL target validation

![Azure SQL target validation](rc18_portfolio_screenshots_sanitized/03-azure-sql-data-validation.jpg)

This screenshot shows the destination database after replication, including a successful query against transferred records. Personal/test identifiers were removed from the prepared public version.

Together with the replication flow above, this provides evidence that data reached the Azure SQL destination and could be queried successfully.

## 5. Qlik Open Lakehouse / Apache Iceberg exploration

![Qlik Open Lakehouse Iceberg](rc18_portfolio_screenshots_sanitized/04-qlik-open-lakehouse-iceberg.jpg)

This screenshot documents the **AWS + Apache Iceberg** architecture exploration using Qlik Open Lakehouse and a **CDC workload**.

This path was explored and configured during the POC but was **not finalized**, primarily because continuing the AWS infrastructure would add unnecessary cost to the proof of concept.

## 6. AWS network integration accepted in Qlik

![AWS network integration](rc18_portfolio_screenshots_sanitized/05-aws-network-integration.jpg)

This screenshot shows that the AWS network integration configuration was accepted in Qlik during the Open Lakehouse exploration.

AWS account numbers, VPC identifiers, internal data space names, and project-specific identifiers were generalized in the prepared public version.

## CDC evidence and scope

CDC is part of the replication architecture used in the POC. Its purpose is to capture changes occurring after the initial data load and propagate those changes incrementally through the data movement flow.

The repository documents CDC as a **validated technical capability in the POC**, without claiming a production latency SLA or strict real-time performance.

## What these screenshots prove

The evidence set supports the following project milestones:

- MySQL on-premises was used as the operational data source.
- Qlik Data Gateway was configured and running in the integration environment.
- Qlik Talend Cloud / Data Movement was configured for replication.
- CDC / incremental change replication was part of the data movement architecture.
- Azure SQL Database was used as the validated Phase 1 destination.
- Replicated data was successfully validated in Azure SQL Database.
- AWS network integration and Qlik Open Lakehouse / Apache Iceberg were genuinely explored as an alternative architecture.

## Screenshots intentionally excluded

Some real implementation screenshots were intentionally not published because they expose excessive infrastructure detail with limited additional portfolio value. Examples include raw AWS VPC/subnet pages, KMS key identifiers and ARNs, IAM account/role details, Azure resource screens containing IP addresses or administrator information, and screenshots with internal hostnames or personal/test data.

## Current SQL Server phase

The next architecture phase will use **Microsoft SQL Server as the lower-cost test destination for pipeline development and continued CDC testing**. Evidence for that phase will only be added after the SQL Server destination and pipeline flow are actually configured and technically validated.

## Sanitization policy

Public screenshots must not expose passwords, API keys, tokens, certificates, project infrastructure IP addresses, AWS account numbers, VPC/subnet IDs, ARNs, KMS identifiers, internal server/database names, email addresses, tenant identifiers, CPF, or confidential customer/business information.
