# Technical Evidence Screenshots

A curated screenshot set has been prepared from the real project. Only sanitized versions should be published in this public repository.

## Selected public evidence

### 1. Qlik Data Gateway running

**Planned file:** `01-qlik-data-gateway-running.jpg`

Shows the Linux service status for **Qlik Data Gateway – Data Movement** with the service active and running. This supports the infrastructure and gateway configuration stage of the POC.

### 2. MySQL → Azure replication pipeline

**Planned file:** `02-mysql-to-azure-pipeline.jpg`

Shows the Qlik replication flow with:

```text
MySQL On-Premises → Replication → Azure SQL Database
```

Internal connection and project names are replaced with generic portfolio labels.

### 3. Azure SQL target validation

**Planned file:** `03-azure-sql-data-validation.jpg`

Shows the destination database after replication with a successful query and transferred records. Personal/test identifiers are removed from the public version.

### 4. Qlik Open Lakehouse / Apache Iceberg exploration

**Planned file:** `04-qlik-open-lakehouse-iceberg.jpg`

Shows the Qlik Open Lakehouse cluster creation workflow and the CDC workload used during the AWS + Apache Iceberg architecture exploration.

### 5. AWS network integration in Qlik

**Planned file:** `05-aws-network-integration.jpg`

Shows that the AWS network integration was accepted in Qlik. AWS account numbers, VPC IDs, internal space names, and project-specific identifiers are removed or generalized.

## Screenshots intentionally excluded

Some real project screenshots are not suitable for a public portfolio because they expose excessive infrastructure detail with limited additional portfolio value. Examples include:

- raw AWS VPC and subnet detail pages
- KMS key identifiers and ARNs
- IAM account and role detail screens
- raw Azure resource configuration containing IP addresses or administrative identifiers
- screenshots containing internal hostnames, emails, customer/project names, or unredacted test data

These images remain useful as private implementation evidence but should not be published publicly.

## Current SQL Server phase

The next architecture phase will use **Microsoft SQL Server as the test destination for pipeline development**. A public screenshot should only be added after that destination and its pipeline flow are actually configured and validated.

## Sanitization rules

Public screenshots must not expose:

- passwords, API keys, tokens, or certificates
- IP addresses tied to project infrastructure
- AWS account numbers, VPC/subnet IDs, ARNs, or KMS identifiers
- internal server or database names
- email addresses or tenant identifiers
- personal data such as CPF
- customer-specific or confidential business information
