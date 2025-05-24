# Revenue Opportunity #5: Disaster Recovery (DR) Expansion Using OCI & Azure

## Storyboard

A multinational enterprise operates mission-critical workloads on Microsoft Azure. To ensure business continuity and meet compliance or regulatory requirements, the company implements a cross-cloud disaster recovery (DR) strategy: **Azure is the primary production environment, while Oracle Cloud Infrastructure (OCI) serves as the DR site. All mission-critical data, applications, and backups are replicated from Azure to OCI using Interconnect (ExpressRoute + FastConnect).** In case of a disaster, workloads fail over to OCI—where pre-provisioned compute, storage, and database resources are available for rapid recovery. This architecture leverages both clouds' strengths and unlocks new DR options beyond single-vendor approaches.

Alternatively, the customer may run production on OCI and use Azure as the DR site, or design an active-active multi-region DR across both clouds. *(This BOM is modeled on Azure as primary, OCI as DR site.)*

-**Typical Use Cases:**
- Mission-critical databases and business applications run in Azure, with a full disaster recovery (DR) site provisioned on OCI across multiple regions. *(This BOM assumes this direction.)*
- Automated failover and failback of applications and data between OCI and Azure for business continuity.
- Cross-region DR and backup/restore between two OCI regions with Azure providing additional DR compute, storage, or temporary workload hosting.
- Hybrid multi-cloud DR, where workloads, data, and storage are protected against regional and cloud-level outages.
- Regulatory or compliance-driven DR deployments requiring separation of DR infrastructure across clouds and geographies.

**Key business outcomes:**
- Enhanced business continuity and compliance with cross-cloud resilience
- Lower TCO by leveraging cloud-native, pay-as-you-go DR resources
- Partner opportunities for DR architecture, migration, orchestration, and managed service revenue

---

## Azure & OCI Components

- **Azure:**
  - Azure Site Recovery (ASR)
  - Azure Blob Storage (Backup, Replication)
  - ExpressRoute Circuit (Standard or Premium)
  - Virtual Network Gateway

- **OCI:**
  - Oracle Database (Autonomous or Exadata)
  - OCI Compute for DR workloads and App Tier
  - OCI Object Storage (for backup/restore/replication)
  - OCI Block Volume (for compute storage)
  - FastConnect Circuit
  - Virtual Cloud Network (VCN) & Dynamic Routing Gateway (DRG)

---

## SKU List, Usage Assumptions & Pricing (per month)

| Component                        | SKU/Service Name             | Usage Assumption                    | Monthly Price (Estimate) |
|---------------------------------|------------------------------|-------------------------------------|--------------------------|
| Azure Site Recovery               | Standard Protection          | 40 protected instances (DR workloads, no DB on Azure)  | $480                     |
| Azure Blob Storage                | 20TB (Hot), LRS             | 20TB stored (2 regions)              | $408                     |
| ExpressRoute Circuit              | Standard Circuit, 2Gbps      | 4 for HA (2 regions, 2 each)         | $4,000                   |
| Virtual Network Gateway           | ErGw3AZ                      | 2 per region (4 total)                | $552                     |
| OCI FastConnect                   | 10 Gbps, 4 ports            | 4 ports, HA (2 regions)               | $3,794.40                |
| OCI Compute (DR standby)          | VM.Standard.E4.Flex, 8 OCPU  | 2 instances, 730 hours (standby)     | $349.21                  |
| OCI Compute (App Tier)            | VM.Standard.E4.Flex, 8 OCPU  | 4 instances                         | $1,181.34                |
| Oracle Database (Autonomous)      | 2 peak (örnek)              | 2 instances, autoscaling, cross-region peer | $2,016                   |
| OCI Object Storage                | 50TB                        | 50TB stored, replication-enabled     | $523.99                  |
| OCI Block Volume                 | Standard Block Volume        | 2 volumes                           | $243.72                  |
| Data Transfer (Egress)            | Azure & OCI                  | 20TB/month bi-directional             | $300 (Azure side)         |
| Managed DR Orchestration Service  | Partner                      | DR automation/monitoring              | $400                     |

---

## BOM Table

| Service                        | Paid to    | SKU/Service Name           | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                                        |
|--------------------------------|------------|----------------------------|-------|---------------------|---------------------|----------------------------------------------|
| Azure Site Recovery            | Azure      | Standard Protection        | 40    | $480                | $5,760              | Multi-region, cross-cloud DR workloads (no DB on Azure) |
| Blob Storage                   | Azure      | 20TB                       | 2     | $408                | $4,896              | Multi-region, cross-cloud replication enabled |
| ExpressRoute Circuit           | Azure      | Standard Circuit, 2Gbps    | 4     | $4,000              | $48,000             | Multi-region, 4 connections total             |
| Virtual Network Gateway        | Azure      | ErGw3AZ                    | 2     | $552                | $6,624              | Multi-region, cross-cloud connectivity enabled |
| FastConnect Circuit            | OCI        | 10Gbps, 4 ports            | 4     | $3,794.40           | $45,532.80          | Multi-region, 4 connections total             |
| Compute (DR Standby)           | OCI        | VM.Standard.E4.Flex, 8 OCPU| 2     | $349.21             | $4,190.52           | Multi-region, cross-region replication enabled |
| Compute (App Tier)             | OCI        | VM.Standard.E4.Flex, 8 OCPU| 4     | $1,181.34           | $14,176.08          | Application tier compute                        |
| Oracle Database (Autonomous)   | OCI        | 2 peak (örnek)             | 2     | $2,016              | $24,192             | Primary DB in OCI with cross-region peer replication |
| Object Storage                 | OCI        | 50TB                       | 1     | $523.99             | $6,287.88           | Multi-region, cross-region replication enabled |
| Block Volume                  | OCI        | Standard Block Volume       | 2     | $243.72             | $2,924.64           | Storage attached to compute instances          |
| Data Transfer (Egress)         | Azure/OCI  | Outbound Data Transfer     | -     | $300                | $3,600              | Multi-region egress, example                  |
| Managed DR Service             | Partner    | DR Automation/Monitoring   | -     | $400                | $4,800              | Paid to Partner                               |
| **Total**                      |            |                            |       | **$14,839.66**      | **$178,075.40**     |                                              |

---

## Value Proposition

### For the Partner
- Recurring revenue from managed DR, orchestration, and monitoring services
- Upsell for DR migration, design, and cloud modernization projects
- Professional services for audit, testing, and compliance

### For the Customer
- Enterprise-grade, cross-cloud DR solution for business continuity and compliance
- Pay-as-you-go, scalable DR infrastructure (no over-provisioning)
- Enhanced resilience and vendor flexibility

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For         | Sample Total (Monthly USD) |
|---------------------|-----------------------------------|----------------------------|
| Azure               | Site Recovery, Blob Storage, ExpressRoute, Virtual Network Gateway, Data Transfer | $5,740           |
| OCI                 | FastConnect, Compute, Autonomous DB, Object Storage, Block Volume, Data Transfer  | $8,408.66        |
| Partner             | Managed DR Orchestration/Monitoring Service                    | $400             |

*Sample totals shown above are for illustration only and will vary based on configuration, usage, and data transfer volume.*
