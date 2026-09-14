# Qlik Talend Cloud Data Integration POC

![Status](https://img.shields.io/badge/status-in%20progress-orange)
![Qlik](https://img.shields.io/badge/Qlik-Talend%20Cloud-009845)
![Data Movement](https://img.shields.io/badge/Data%20Movement-working-success)
![MySQL](https://img.shields.io/badge/Source-MySQL%20On--Premises-4479A1)
![Azure SQL](https://img.shields.io/badge/Target-Azure%20SQL%20Database-0078D4)
![AWS](https://img.shields.io/badge/AWS%20%2B%20Iceberg-not%20finalized-lightgrey)

> **Portfolio case study based on a real ongoing BI/data integration POC.** Client-specific names, credentials, addresses, infrastructure identifiers, and business data are intentionally omitted or anonymized.

## Overview

This project documents an ongoing **Qlik Talend Cloud (QTC)** proof of concept focused on moving data from an on-premises environment to the cloud.

The validated implementation at the current stage is a data movement flow from an **on-premises MySQL database** to **Azure SQL Database** using Qlik Talend Cloud.

The project is currently **in progress**.

## Current validated milestone

**Data Movement from MySQL on-premises to Azure SQL Database is configured and working.**

The work completed so far includes environment preparation, connectivity configuration, source and target setup, data movement execution, validation, and troubleshooting.

## Validated architecture

```text
On-Premises Environment
        |
        v
MySQL Database
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

## Technologies used in the validated flow

- **Qlik Talend Cloud (QTC)**
- **Qlik Data Movement**
- **MySQL** — on-premises source
- **Azure SQL Database** — cloud destination
- **Virtual machine / integration environment**
- Source-to-target connectivity and validation

## AWS + Apache Iceberg exploration

An alternative architecture using **AWS with Apache Iceberg** was also configured/explored during the POC.

This path was **not finalized** because continuing the AWS environment would introduce additional infrastructure cost for the proof of concept. It is therefore documented as an explored alternative, not as a completed production-ready data movement flow.

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

## What I implemented

### Infrastructure & connectivity

- Prepared the integration environment required for the POC.
- Worked with a **virtual machine** as part of the integration architecture.
- Configured connectivity between the on-premises MySQL source and Qlik Talend Cloud.
- Configured the Azure SQL Database destination connection.
- Validated source and target connectivity.
- Diagnosed and corrected connectivity/configuration issues during setup.

### Qlik Talend Cloud

- Configured the Qlik Talend Cloud environment for the POC.
- Configured **MySQL on-premises as the source**.
- Configured **Azure SQL Database as the destination**.
- Implemented and executed **Qlik Data Movement**.
- Validated that data successfully reached the Azure destination.
- Performed troubleshooting during configuration and movement validation.

### Alternative architecture explored

- Configured/explored an **AWS + Apache Iceberg** destination scenario.
- Did not finalize this path because of infrastructure cost considerations for the POC.

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

As the POC progresses, this repository will be updated only with milestones that have actually been implemented and technically validated.
