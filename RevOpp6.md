# Revenue Opportunity #6: MySQL & HeatWave Synergy with Azure

## Storyboard

A modern enterprise runs its business applications and data pipelines on Azure, but leverages Oracle Cloud Infrastructure (OCI) MySQL HeatWave for high-performance, real-time analytics. Since HeatWave is not available on Azure, analytics workloads and advanced MySQL operations are performed entirely in OCI. Data flows securely and efficiently between Azure and OCI using the dedicated Interconnect (Azure ExpressRoute + OCI FastConnect).

## Typical Use Cases
- Modern web/mobile apps on Azure, requiring real-time analytics on MySQL data in OCI
- Hybrid analytics, where data is ingested from Azure and analyzed using HeatWave in OCI
- Disaster Recovery (DR) for MySQL databases, with cross-region replication in OCI and DR for Azure app tier

## Key Business Outcomes
- Real-time analytics and MySQL performance unavailable on Azure
- Flexible, multi-cloud DR and data protection
- Increased network and managed service consumption

---

## Azure & OCI Components

- **Azure:**
  - Azure App Service (Application hosting)
  - Azure Blob Storage (Data storage, geo-replication for DR)
  - Azure Data Factory (Data transfer; optional)
  - Azure Site Recovery (App tier DR)
  - ExpressRoute Circuit (1 Gbps, for Interconnect)

- **OCI:**
  - MySQL HeatWave Service (Analytics processing)
  - Object Storage (500 GB for backups and staging)
  - FastConnect Circuit (1 Gbps, for Interconnect)
  - MySQL HeatWave Cross-Region Replica (DR)
  - Object Storage Cross-Region Replication (Backup DR)

---

## SKU List, Usage Assumptions & Pricing (per month)

| Component                                | SKU/Service Name                        | Usage Assumption               | Monthly Price (Estimate) |
|-------------------------------------------|-----------------------------------------|-------------------------------|--------------------------|
| Azure App Service                        | Premium (P3v3, 8 cores)                 | 1 instance, 730 hours         | $900                     |
| Azure Blob Storage                       | 2TB, geo-replicated                     | Data + DR storage             | $250                     |
| Azure Data Factory                       | Standard                                | Optional, data transfer       | $100                     |
| Azure Site Recovery                      | Standard Protection                     | DR for App Tier               | $240                     |
| ExpressRoute Circuit                     | Standard Circuit (1 Gbps)               | 2 for HA                      | $948.90                  |
| MySQL HeatWave Service                   | MySQL HeatWave                          | 32 OCPU, 512GB RAM (sample)   | $2,634.61                |
| Object Storage                           | OCI Object Storage (500 GB)             | Backups/staging               | $12.50                   |
| FastConnect Circuit                      | FastConnect Direct (1 Gbps)             | 2 for HA                      | $632.40                  |
| MySQL HeatWave Cross-Region Replica      | HeatWave Cross-Region Replica           | DR in 2nd region              | $1,900                   |
| Object Storage Cross-Region Replication  | Object Storage Replication (500 GB)     | Backup DR                     | $75                      |

---

## BOM Table

| Service                              | Paid to    | SKU/Service Name              | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                             |
|---------------------------------------|------------|-------------------------------|-------|---------------------|---------------------|------------------------------------|
| Azure App Service                    | Azure      | Premium (P3v3, 8 cores)       | 1     | $900                | $10,800             | Microsoft Azure                    |
| Azure Blob Storage                   | Azure      | 2TB, geo-replicated           | 1     | $250                | $3,000              | Microsoft Azure, DR enabled        |
| Azure Data Factory                   | Azure      | Standard                      | 1     | $100                | $1,200              | Microsoft Azure, optional          |
| Azure Site Recovery                  | Azure      | Standard Protection           | 1     | $240                | $2,880              | Microsoft Azure, App Tier DR       |
| ExpressRoute Circuit                 | Azure      | Standard Circuit (1 Gbps)     | 2     | $948.90             | $11,386.80          | Microsoft Azure, Interconnect (HA) |
| MySQL HeatWave Service               | OCI        | MySQL HeatWave                | 1     | $2,634.61           | $31,975.32          | Oracle Cloud Infrastructure        |
| OCI Object Storage                   | OCI        | 500 GB                        | 1     | $12.50              | $150                 | Oracle Cloud Infrastructure        |
| FastConnect Circuit                  | OCI        | FastConnect Port (1 Gbps)     | 2     | $632.40             | $7,588.80            | Oracle Cloud Infrastructure (HA)   |
| MySQL HeatWave Cross-Region Replica  | OCI        | Cross-Region Replica          | 1     | $1,900              | $22,800              | DR in 2nd OCI region               |
| OCI Object Storage Cross-Region Replication | OCI   | Replication (500 GB)          | 1     | $75                 | $900                 | DR for backups                     |
| **Total**                            |            |                               |       | **$7,693.41**       | **$92,320.92**      |                                    |

*Data Transfer/Egress: Outbound data transfer is billed by the originating cloud provider. Example shown; actual costs depend on usage and direction.*

---

## Value Proposition

### For the Partner
- Recurring revenue from multi-cloud managed database/analytics services
- Integration, migration, and DR services for MySQL/HeatWave and Azure workloads
- Ongoing support, automation, and optimization

### For the Customer
- High-performance MySQL analytics not available on Azure
- Multi-cloud DR and business continuity for MySQL
- Maximum flexibility for future modernization and AI/analytics expansion

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For                    | Sample Total (Monthly USD) |
|---------------------|----------------------------------------------|----------------------------|
| Azure               | App Service, Blob Storage, Data Factory, Site Recovery, ExpressRoute | $2,438.90                  |
| OCI                 | MySQL HeatWave, Object Storage, FastConnect, Cross-Region Replica, Replication | $5,254.51                  |

*Sample totals above are for illustration and will vary based on configuration, usage, and data transfer volume.*