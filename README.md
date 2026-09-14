# Qlik Talend Cloud Data Integration POC

![Status](https://img.shields.io/badge/status-in%20progress-orange)
![Qlik](https://img.shields.io/badge/Qlik-Talend%20Cloud-009845)
![Data Movement](https://img.shields.io/badge/Data%20Movement-working-success)
![MySQL](https://img.shields.io/badge/Source-MySQL%20On--Premises-4479A1)
![Azure SQL](https://img.shields.io/badge/Validated%20Target-Azure%20SQL%20Database-0078D4)
![SQL Server](https://img.shields.io/badge/Next%20Test%20Target-SQL%20Server-CC2927)
![AWS](https://img.shields.io/badge/AWS%20%2B%20Iceberg-not%20finalized-lightgrey)

> **Portfolio case study based on a real ongoing BI/data integration POC.** Client-specific names, credentials, addresses, infrastructure identifiers, and business data are intentionally omitted or anonymized.

## Overview

This project documents an ongoing **Qlik Talend Cloud (QTC)** proof of concept focused on moving data from an on-premises environment to target data platforms and progressively validating additional Qlik data integration capabilities.

The first validated flow moved data from an **on-premises MySQL database** to **Azure SQL Database** using Qlik Talend Cloud Data Movement.

The project is currently moving into its next phase: using **SQL Server as a lower-cost test destination** so pipeline configuration and orchestration can be developed and validated without maintaining the higher-cost cloud alternatives used earlier in the POC.

## Phase 1 — Validated milestone

**Data Movement from MySQL on-premises to Azure SQL Database is configured and working.**

```text
MySQL On-Premises
        |
        v
Integration / VM Environment
        |
        v
Qlik Talend Cloud
        |
        v
Qlik Data Movement
        |
        v
Azure SQL Database
        |
        v
Data Validation
```

Work completed in this phase includes environment preparation, connectivity configuration, source and target setup, Data Movement execution, validation, and troubleshooting.

## Phase 2 — Current test direction

The next implementation phase will keep **MySQL on-premises as the source** and use **SQL Server as the test destination**.

The goal of this change is to continue the POC with a lower-cost destination while advancing into **pipeline configuration, orchestration, and transformation tests**.

```text
MySQL On-Premises
        |
        v
Integration / VM Environment
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

> SQL Server is the destination for the **current/next test phase**. Pipeline functionality will only be marked as implemented after it has been configured and technically validated.

## AWS + Apache Iceberg exploration

An alternative architecture using **AWS with Apache Iceberg** was also configured/explored during the POC.

This path was **not finalized** because continuing the AWS environment would introduce additional infrastructure cost for the proof of concept. It is documented as an explored alternative, not as a completed data movement flow.

## Technologies by project stage

### Validated
- **Qlik Talend Cloud (QTC)**
- **Qlik Data Movement**
- **MySQL** — on-premises source
- **Azure SQL Database** — validated destination
- **Virtual machine / integration environment**
- Source-to-target connectivity and validation

### Current / next test phase
- **SQL Server** — lower-cost test destination
- Pipeline configuration and orchestration testing

### Explored but not finalized
- **AWS**
- **Apache Iceberg**

## Project status

| Stage | Status |
|---|---|
| Integration / VM environment preparation | ✅ Implemented |
| MySQL on-premises source connectivity | ✅ Implemented |
| Azure SQL Database target connectivity | ✅ Implemented |
| Qlik Talend Cloud configuration | ✅ Implemented |
| MySQL → Azure Data Movement | ✅ Working |
| Data transfer validation in Azure | ✅ Implemented |
| AWS + Apache Iceberg alternative | 🟡 Explored / not finalized due to cost |
| SQL Server as test destination | 🔄 Current next phase |
| Pipeline configuration / orchestration | 🔄 Next implementation milestone |
| Transformations / preparation | ⏳ Planned |
| Data Products | ⏳ Planned |
| Qlik Cloud analytical consumption | ⏳ Planned |
| Qlik Automate | ⏳ Planned |
| Reporting workflows | ⏳ Planned |
| Qlik Answers | ⏳ Planned |

## Repository structure

```text
.
├── README.md
├── PROJECT_SCOPE.md
├── architecture/
│   └── README.md
├── infrastructure/
│   └── README.md
├── data-movement/
│   └── README.md
├── roadmap/
│   └── README.md
└── screenshots/
    └── README.md
```

## Documentation

- [Verified Project Scope](PROJECT_SCOPE.md)
- [Architecture](architecture/README.md)
- [Infrastructure & Connectivity](infrastructure/README.md)
- [Data Movement](data-movement/README.md)
- [Project Roadmap](roadmap/README.md)
- [Screenshot Guidelines](screenshots/README.md)

## Confidentiality

This repository is a **portfolio representation** of practical work performed in a real project. It does not contain production credentials, IP addresses, server names, customer data, proprietary scripts, confidential screenshots, or internal company documentation.

As the POC progresses, this repository will be updated only with milestones that have actually been implemented and technically validated.
