# Azure Workflow Modernization — Swiss Re

![Azure](https://img.shields.io/badge/Microsoft_Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Azure Data Factory](https://img.shields.io/badge/Azure_Data_Factory-0062AD?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![Azure Functions](https://img.shields.io/badge/Azure_Functions-0062AD?style=for-the-badge&logo=azure-functions&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Azure DevOps](https://img.shields.io/badge/Azure_DevOps-0078D7?style=for-the-badge&logo=azure-devops&logoColor=white)

> Large-scale enterprise workflow migration from **Informatica → Microsoft Azure** for a global reinsurance client.  
> Achieved **~50% reduction in data processing time** and significantly improved system scalability and operational efficiency.

---

## 📌 Project Overview

This project involved modernizing hundreds of legacy Informatica-based data integration workflows by migrating them to Microsoft Azure cloud infrastructure. The goal was to improve performance, reduce operational costs, enable centralized monitoring, and bring CI/CD practices to enterprise data pipelines.

The solution was designed to be **fully cloud-native**, scalable, and maintainable — with logging, alerting, and multi-environment deployment built in from day one.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        DATA SOURCES                         │
│         (On-prem DBs / APIs / SFTP / Flat Files)            │
└────────────────────────────┬────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                   INGESTION LAYER                           │
│         Azure Data Factory  ·  Azure Logic Apps             │
└────────────────────────────┬────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                 PROCESSING / TRANSFORMATION                  │
│       Azure Function Apps (Python)  ·  Liquid Templates     │
└────────────────────────────┬────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                     STORAGE LAYER                           │
│         ADLS Gen2  ·  Azure Blob Storage                    │
└────────────────────────────┬────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│               MONITORING & OBSERVABILITY                    │
│    Azure Log Analytics  ·  Application Insights  ·  Kibana  │
└─────────────────────────────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                   CI/CD — AZURE DEVOPS                      │
│           DEV  →  NON-PROD  →  PROD  (multi-env)            │
└─────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Ingestion | Azure Data Factory, Azure Logic Apps |
| Processing | Azure Function Apps (Python), Liquid Templates |
| Storage | ADLS Gen2, Azure Blob Storage |
| Monitoring | Azure Log Analytics, Application Insights, Kibana |
| CI/CD | Azure DevOps (multi-environment pipelines) |
| Networking | Private Endpoints, VNet Integration |
| Security | OAuth2, SSL, Firewall configurations |

---

## ✅ Key Achievements

- ✅ Migrated **hundreds of Informatica workflows** to Azure cloud
- ✅ **~50% reduction** in data processing time post-migration
- ✅ Centralized **logging, monitoring and alerting** across all workflows
- ✅ Automated deployments across **DEV → NON-PROD → PROD** environments
- ✅ Resolved critical production issues: private endpoints, IR connectivity, SSL, firewall
- ✅ Improved **system scalability and operational efficiency** significantly

---

## 📁 Project Structure

```
azure-workflow-modernization/
│
├── functions/                  # Azure Function Apps (Python)
│   ├── data_ingestion/         # Ingestion trigger functions
│   ├── data_transformation/    # Processing & transformation logic
│   └── error_handler/          # Centralised error handling
│
├── pipelines/                  # Azure Data Factory pipeline definitions
│   ├── ingestion_pipelines/
│   └── transformation_pipelines/
│
├── logic_apps/                 # Logic App workflow definitions
│
├── monitoring/                 # Log Analytics queries (KQL), alert rules
│
├── devops/                     # Azure DevOps YAML pipeline definitions
│   ├── dev.yml
│   ├── non-prod.yml
│   └── prod.yml
│
├── docs/                       # Architecture diagrams, design docs
│
└── README.md
```

---

## 🔄 Migration Approach

The migration followed a phased approach:

1. **Discovery & Assessment** — Inventory all existing Informatica workflows, classify by complexity and priority
2. **Architecture Design** — Map each Informatica component to its Azure equivalent
3. **Development** — Build Azure-native equivalents using ADF, Logic Apps, and Python Functions
4. **Testing** — Validate data parity between legacy and new pipelines in NON-PROD
5. **Cutover** — Staged production deployment via Azure DevOps CI/CD
6. **Monitoring** — Post-go-live observability via Log Analytics + Application Insights + Kibana

---

## 📊 Performance Comparison

| Metric | Before (Informatica) | After (Azure) |
|---|---|---|
| Average processing time | Baseline | ~50% faster |
| Deployment process | Manual | Fully automated (CI/CD) |
| Monitoring | Fragmented | Centralized |
| Scalability | Limited | Cloud-native auto-scale |
| Environment management | Single | DEV / NON-PROD / PROD |

---

## ⚠️ Note

This repository contains **architecture documentation, design patterns, and sanitized sample code** only.  
No proprietary client data or production credentials are included.

---

## 👤 Author

**Prakash Thakur** — Data Engineer, InfoOrigin Pvt. Ltd.  
📧 prakash7thakur@gmail.com  
🌐 [Portfolio](https://personal-portfolio-d-z8t2.bolt.host/)
