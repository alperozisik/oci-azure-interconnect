# Revenue Opportunity #4: Unified Data Management (EBS + OCI–Azure Distributed Data)

## Storyboard

A large enterprise runs its core Oracle E-Business Suite (EBS) environment on OCI, taking advantage of high performance, security, and Oracle-native support. At the same time, the organization needs to unify, replicate, and synchronize EBS and other business data across Azure for use with Microsoft analytics, AI, and reporting platforms (such as Power BI or Azure Synapse). Distributed workloads require robust, high-speed, and secure inter-cloud data movement. Azure-OCI Interconnect (ExpressRoute + FastConnect) enables seamless, secure sharing of data between OCI (hosting EBS and Oracle DBs) and Azure (hosting analytics, reporting, or SaaS extensions), supporting multi-cloud data lakes, unified governance, and integrated analytics. The architecture can also extend to multi-region high availability and federated identity management across Azure and OCI, ensuring business continuity and unified access control in distributed environments.

## Typical Use Cases
- Synchronizing EBS master data and transactional data with Azure analytics or reporting services
- Building multi-cloud data lakes and unified BI dashboards
- Integrating custom or SaaS applications in Azure with EBS/Oracle databases in OCI
- Supporting global business continuity, regulatory compliance, or geographic expansion

## Key Business Outcomes
- End-to-end unified data landscape across both clouds
- Real-time or near-real-time analytics, reporting, and AI/ML on business-critical data
- Best-in-class compliance, resilience, and vendor flexibility
- Partner opportunities for integration, migration, and managed services

---

## Azure & OCI Components

- **Azure:**
  - Azure Data Factory or Azure Synapse Analytics
  - Power BI, Azure Data Lake Storage, or SQL Database
  - ExpressRoute Circuit (Standard or Premium)
  - Virtual Network Gateway

- **OCI:**
  - E-Business Suite (EBS) on Compute/DB System
  - Oracle Database (Autonomous or Exadata)
  - FastConnect Circuit
  - OCI Object Storage
  - VCN & DRG
  - OCI Load Balancer (Flexible Load Balancer)

---

## SKU List, Usage Assumptions & Pricing (per month)

| Component                       | SKU/Service Name                | Usage Assumption                    | Monthly Price (Estimate) |
|----------------------------------|---------------------------------|-------------------------------------|--------------------------|
| Azure Data Factory               | Standard Pipeline               | 50,000 activities                   | $1,000                   |
| Azure ExpressRoute (Standard)    | Standard Circuit                | 2 Gbps, 2 circuits for HA           | $2,000                   |
| Virtual Network Gateway          | ErGw3AZ                         | 1 per region                        | $276                     |
| Azure Data Lake Storage          | 10TB (Hot), LRS                 | 10TB stored                         | $204                     |
| FastConnect                      | FastConnect Direct              | 10 Gbps, 2 ports, HA                | $1,897.80                |
| EBS Compute (OCI)                | VM.Standard.E4.Flex, 16 OCPU    | 1 instance, 730 hours               | $700                     |
| Oracle Database (OCI)            | 8 OCPU, 2TB storage             | 1 instance, 730 hours               | $1,400                   |
| OCI Object Storage               | 50TB                            | 50TB stored                         | $1,250                   |
| OCI Load Balancer               | Flexible Load Balancer           | Flexible LB, 2 Gbps                  | $166.03                  |
| Data Transfer (Egress)           | Azure & OCI                     | 10TB/month bi-directional           | $150 (Azure side)        |
| Managed Data Integration Service | Partner                         | Integration/monitoring/support      | $500                     |

---

## BOM Table

| Service                     | Paid to    | SKU/Service Name        | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                       |
|-----------------------------|------------|-------------------------|-------|---------------------|---------------------|-----------------------------|
| Azure Data Factory          | Azure      | Standard Pipeline       | 1     | $1,000              | $12,000             | Microsoft Azure             |
| ExpressRoute Circuit        | Azure      | Standard Circuit        | 2     | $2,000              | $48,000             | Microsoft Azure             |
| Virtual Network Gateway     | Azure      | ErGw3AZ                 | 1     | $276                | $3,312              | Microsoft Azure             |
| Data Lake Storage           | Azure      | 10TB                    | 1     | $204                | $2,448              | Microsoft Azure             |
| FastConnect Circuit         | OCI        | 10 Gbps, 2 ports, HA    | 2     | $1,897.80           | $45,547.20          | Oracle Cloud Infrastructure |
| EBS Compute                 | OCI        | VM.Standard.E4.Flex     | 1     | $700                | $8,400              | Oracle Cloud Infrastructure |
| Oracle Database             | OCI        | 8 OCPU, 2TB storage     | 1     | $1,400              | $16,800             | Oracle Cloud Infrastructure |
| OCI Object Storage          | OCI        | 50TB                    | 1     | $1,250              | $15,000             | Oracle Cloud Infrastructure |
| OCI Load Balancer           | OCI        | Flexible Load Balancer  | 1     | $166.03             | $1,992.36           | Flexible LB, 2 Gbps         |
| Data Transfer (Egress)      | Azure/OCI  | Outbound Data Transfer  | -     | $150                | $1,800              | Example, see note           |
| Managed Data Integration    | Partner    | Integration Service     | -     | $500                | $6,000              | Paid to Partner             |
| **Total**                   |            |                         |       | **$13,441.63**       | **$161,299.56**     |                             |

*Data Transfer/Egress: Outbound data transfer is billed by the originating cloud provider. Example shown; actual costs depend on usage and direction.*

---

## Value Proposition

### For the Partner
- Recurring revenue from managed data integration and migration services
- Upsell for BI modernization, multi-cloud governance, and analytics enablement
- Professional services for compliance, DR, and business continuity

### For the Customer
- End-to-end, secure data landscape across Oracle and Azure clouds
- Real-time, scalable analytics and AI on trusted business data
- No forced migration; maximum flexibility and cloud leverage

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For                    | Sample Total (Monthly USD) |
|---------------------|----------------------------------------------|----------------------------|
| Azure               | Data Factory, ExpressRoute, Virtual Network Gateway, Data Lake Storage, Data Transfer | $5,580           |
| OCI                 | FastConnect, EBS Compute, Oracle Database, Object Storage, Load Balancer | $7,361.63        |
| Partner             | Managed Data Integration/Support Service     | $500                       |

**Total: $13,441.63**

*Sample totals above are for illustration and will vary based on configuration, usage, and data transfer volume.*