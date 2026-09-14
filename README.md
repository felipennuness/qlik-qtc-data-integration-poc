# Qlik Talend Cloud Data Integration POC

![Status](https://img.shields.io/badge/status-in%20progress-orange)
![Qlik](https://img.shields.io/badge/Qlik-Talend%20Cloud-009845)
![Data Movement](https://img.shields.io/badge/Data%20Movement-working-success)
![Azure SQL](https://img.shields.io/badge/Azure-SQL%20Database-0078D4)
![SQL Server](https://img.shields.io/badge/Microsoft-SQL%20Server-CC2927)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1)
![AWS](https://img.shields.io/badge/AWS-Cloud-232F3E)

> **Portfolio case study based on a real ongoing BI/data integration POC.** Client-specific names, credentials, addresses, infrastructure identifiers, and business data are intentionally omitted or anonymized.

## Overview

This project documents the implementation of a data integration proof of concept using **Qlik Talend Cloud (QTC)**. The goal is to progressively build an end-to-end modern data architecture, starting with infrastructure and connectivity and advancing toward governed data delivery and analytics.

The project is currently **in progress**.

### Current milestone

**Data Movement is configured, validated, and working.**

The work completed so far includes environment preparation, connectivity, source/target configuration, data movement validation, and troubleshooting across heterogeneous database and cloud technologies.

## Technologies used so far

- **Qlik Talend Cloud (QTC)**
- **Qlik Data Movement**
- **AWS**
- **Azure SQL Database**
- **Microsoft SQL Server**
- **MySQL**
- **Virtual machine / integration environment**
- Relational database connectivity
- Source-to-target data validation

## Current architecture stage

```text
Database / Cloud Sources
        |
        |  SQL Server
        |  MySQL
        |  Azure SQL Database
        |  AWS environment
        v
Integration / VM Environment
        |
        v
Qlik Talend Cloud
        |
        v
Data Movement
        |
        v
Target Data Environment
        |
        v
Validation
```

> The diagram represents the technologies and integration layers involved in the POC without exposing the client's internal topology or connection details.

## What I implemented

### Infrastructure & connectivity

- Prepared the integration environment required for the POC.
- Worked with a **virtual machine** as part of the integration architecture.
- Configured and validated connectivity between Qlik Talend Cloud and database/cloud environments.
- Worked with **AWS, Azure SQL Database, SQL Server, and MySQL** in connectivity and data movement scenarios.

### Qlik Talend Cloud

- Configured the Qlik Talend Cloud environment for the POC.
- Configured source and target connections.
- Implemented **Data Movement** scenarios.
- Validated successful data transfer between configured environments.
- Performed troubleshooting during connectivity and movement configuration.
- Validated the current milestone before advancing to subsequent architecture layers.

## Project status

| Stage | Status |
|---|---|
| Infrastructure / VM preparation | ✅ Implemented |
| Source and target connectivity | ✅ Implemented |
| Qlik Talend Cloud configuration | ✅ Implemented |
| Data Movement | ✅ Working |
| Data transfer validation | ✅ Implemented |
| Advanced pipelines / orchestration | 🔄 Next stage |
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

- [Architecture](architecture/README.md)
- [Infrastructure & Connectivity](infrastructure/README.md)
- [Data Movement](data-movement/README.md)
- [Project Roadmap](roadmap/README.md)
- [Screenshot Guidelines](screenshots/README.md)

## Confidentiality

This repository is a **portfolio representation** of practical work performed in a real project. It does not contain production credentials, IP addresses, server names, customer data, proprietary scripts, confidential screenshots, or internal company documentation.

As the POC progresses, this repository will be updated with sanitized architecture diagrams, technical notes, synthetic examples, and validated project milestones.
