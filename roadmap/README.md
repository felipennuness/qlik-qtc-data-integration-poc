# Project Roadmap

This POC is actively evolving. The roadmap below separates **validated implementation**, **current test work**, **explored alternatives**, and **future stages**.

## Validated implementation

- Integration / VM environment preparation
- Qlik Talend Cloud environment setup
- MySQL on-premises source connectivity
- Azure SQL Database destination connectivity
- Qlik Data Movement configuration
- Successful MySQL-to-Azure data transfer
- Target-side validation in Azure
- Connectivity and movement troubleshooting

## Current test phase

- Configure **SQL Server as the lower-cost test destination**
- Keep **MySQL on-premises as the source**
- Configure and validate pipeline behavior using the SQL Server test target
- Test pipeline orchestration and transformation scenarios
- Validate downstream data flow

## Explored alternative

- AWS environment configuration/exploration
- Apache Iceberg destination scenario
- **Status:** not finalized because of additional infrastructure cost for the POC

## Planned Qlik Cloud expansion

- Data Products
- Qlik Cloud analytical consumption
- Qlik Automate
- Reporting workflows
- Qlik Answers

## Documentation principle

Only stages that have been implemented and technically validated are marked as completed in this repository. Current test work, explored alternatives, and planned capabilities are explicitly separated from the validated implementation.
