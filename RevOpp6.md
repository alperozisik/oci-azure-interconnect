# RevOpp6

## Storyboard

All analytics operations are performed on MySQL HeatWave in OCI. Since HeatWave is not available on Azure, data is transferred via Interconnect from Azure to OCI. The Azure application tier accesses OCI MySQL HeatWave for data and analytics needs; all analytics and reporting are completed on OCI.

Analytics workload is performed entirely on OCI MySQL HeatWave; data exchange with Azure applications is via Interconnect. (Interconnect is established using Azure ExpressRoute and OCI FastConnect.)

## Azure & OCI Components

### Azure Components

- App Tier
- Storage
- Data Factory (optional, for data transfer)
- Azure Site Recovery (for App Tier Disaster Recovery)
- Azure Blob Storage Geo-Replication (for Disaster Recovery)
- Azure ExpressRoute (for Network Interconnect)

### OCI Components

- MySQL HeatWave
- Object Storage (500 GB capacity for backups and data staging)
- OCI FastConnect (1 Gbps for Network Interconnect)
- OCI MySQL HeatWave Cross-Region Replica (for MySQL Disaster Recovery)
- OCI Object Storage Cross-Region Replication (for backup Disaster Recovery)

## SKU List

| Component                         | SKU/Service Name                          | Quantity | Notes                         |
|----------------------------------|------------------------------------------|----------|-------------------------------|
| Azure App Tier                   | Azure App Service                        | 1        | Application hosting            |
| Azure Storage                   | Azure Blob Storage                       | 1        | Data storage                  |
| Azure Data Factory              | Azure Data Factory                       | 1        | Optional, for data transfer   |
| Azure ExpressRoute              | Azure ExpressRoute                       | 1        | 1 Gbps                       |
| OCI MySQL HeatWave              | MySQL HeatWave Service                   | 1        | Analytics processing          |
| OCI Object Storage              | OCI Object Storage                       | 1        | 500 GB Backup and staging     |
| OCI FastConnect                | OCI FastConnect                          | 1        | 1 Gbps                       |
| Azure Site Recovery             | Azure Site Recovery                      | 1        | Disaster Recovery for App Tier|
| OCI MySQL HeatWave Cross-Region Replica | OCI MySQL HeatWave Cross-Region Replica | 1        | MySQL Disaster Recovery       |
| OCI Object Storage Cross-Region Replication | OCI Object Storage Cross-Region Replication | 1        | Backup Disaster Recovery      |
| Azure Blob Storage Geo-Replication | Azure Blob Storage Geo-Replication      | 1        | Geo-Replication for DR        |

## Usage Assumptions & Pricing

- Azure App Service: Based on application usage.
- Azure Blob Storage: Based on data stored.
- Azure Data Factory: Usage depends on data transfer needs.
- OCI MySQL HeatWave: Based on analytics workload.
- OCI Object Storage: Based on backup and staging storage (500 GB).
- Azure ExpressRoute: Based on data transfer volume and selected bandwidth (1 Gbps in this scenario).
- OCI FastConnect: Based on data transfer volume and selected bandwidth (1 Gbps in this scenario).
- Azure Site Recovery: Based on protected instances for disaster recovery.
- OCI MySQL HeatWave Cross-Region Replica: Based on replica usage for MySQL disaster recovery.
- OCI Object Storage Cross-Region Replication: Based on replicated storage for backup disaster recovery.
- Azure Blob Storage Geo-Replication: Based on geo-replicated data storage for disaster recovery.

## BOM Table

| Component                               | Quantity | Unit Price | Total Price  |
|---------------------------------------|----------|------------|--------------|
| Azure App Service                     | 1        | $900       | $900         |
| Azure Blob Storage                    | 1        | $250       | $250         |
| Azure Data Factory                   | 1        | $100       | $100         |
| OCI MySQL HeatWave                   | 1        | $2,634.61  | $2,634.61    |
| OCI Object Storage                   | 1        | $12.50     | $12.50       |
| Azure ExpressRoute                   | 1        | $948.90    | $948.90      |
| OCI FastConnect                     | 1        | $632.40    | $632.40      |
| Azure Site Recovery                  | 1        | $240       | $240         |
| OCI MySQL HeatWave Cross-Region Replica | 1     | $1,900     | $1,900       |
| OCI Object Storage Cross-Region Replication | 1    | $75        | $75          |
| Azure Blob Storage Geo-Replication   | 1        | $60        | $60          |
| **Total**                           |          |            | **$7,753.41**|

## Who Gets Paid for What?

| Institution | Example Services Paid For                                              | Sample Total (Monthly USD) |
|-------------|----------------------------------------------------------------------|----------------------------|
| Microsoft   | Azure App Service, Azure Blob Storage, Azure Data Factory, Azure Site Recovery, Azure Blob Storage Geo-Replication | $1,550                     |
| Microsoft   | Azure ExpressRoute                    | $948.90                    |
| Oracle      | OCI MySQL HeatWave, OCI Object Storage, OCI MySQL HeatWave Cross-Region Replica, OCI Object Storage Cross-Region Replication | $4,622.51                  |
| Oracle      | OCI FastConnect                    | $632.40                    |
