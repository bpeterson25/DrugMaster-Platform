# DrugMaster Platform

## Overview

DrugMaster Platform is an enterprise drug intelligence framework designed to acquire, normalize, enrich, and maintain comprehensive drug reference data from publicly available healthcare data sources.

The platform serves as the foundation for downstream analytics, market intelligence, formulary strategy, value-based pharmacy, and drug repository management use cases.

---

## Project Objectives

DrugMaster Platform was built to:

- Create a persistent drug repository
- Normalize drug concepts across multiple sources
- Support monthly and quarterly refresh cycles
- Enable enterprise analytics and reporting
- Serve as the data foundation for future applications

The platform separates:

### Data Acquisition

Retrieving source data from authoritative public repositories.

### Data Normalization

Building standardized product, package, ingredient, and clinical concept models.

### Data Enrichment

Integrating regulatory, clinical, and pricing data sources.

### Data Consumption

Supporting query tools, analytics, dashboards, and reporting.

---

## Architecture

```text
               OpenFDA
                   |
                   |
               RxNorm
                   |
                   |
            DrugMaster Builder
                   |
                   |
            DrugMaster Integration
                   |
                   |
        drug_master.parquet
                   |
      --------------------------
      |                        |
      |                        |
DrugMaster Query      Analytics & BI
```

---

## Repository Structure

```text
DrugMaster-Platform

├── notebooks
│
│   ├── DrugMaster_Builder.ipynb
│   ├── DrugMaster_RxNorm_Builder.ipynb
│   └── DrugMaster_Integration.ipynb
│
├── repositories
│
│   ├── openfda
│   ├── rxnorm
│   └── master
│
├── docs
│
└── archive
```

---

## Core Components

### DrugMaster Builder

Purpose:

- Download OpenFDA drug data
- Build product repository
- Build package repository
- Build ingredient repository
- Generate repository assets

Primary Outputs:

```text
products.parquet
packages.parquet
ingredients.parquet
repository.parquet
```

---

### DrugMaster RxNorm Builder

Purpose:

- Map generic names to RxCUIs
- Retrieve RxNorm concept metadata
