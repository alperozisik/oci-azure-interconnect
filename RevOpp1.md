# Revenue Opportunity #1: Increased Network Consumption (ExpressRoute Growth)

## Storyboard

A global enterprise runs its core business applications on Microsoft Azure while hosting critical Oracle databases and analytics workloads on Oracle Cloud Infrastructure (OCI). To ensure seamless and secure data exchange—such as live transaction processing, data warehousing, and real-time analytics—between Azure and OCI, the customer implements a dedicated, high-throughput Interconnect leveraging Azure ExpressRoute and OCI FastConnect. The architecture uses redundant ExpressRoute circuits for high availability, guaranteeing low-latency, high-bandwidth, and highly available connections between cloud environments. Continuous data transfer and integration between environments drive up network bandwidth consumption, resulting in greater recurring revenue from network services.

## Typical Use Cases
- Seamless data exchange and integration between Azure and OCI for core business applications and analytics
- High-throughput, low-latency connectivity for live transaction processing, data warehousing, and real-time analytics
- Multi-region or global high availability and disaster recovery leveraging both Azure and OCI
- Scenarios requiring secure, dedicated connectivity for compliance or regulatory reasons

## Key Business Outcomes
- Increased network bandwidth and interconnect usage (ExpressRoute/FastConnect)
- High-value managed network services for partners
- Improved reliability and performance for enterprise customers
- Foundation for enabling additional hybrid cloud use cases

---

## Azure & OCI Components

- **Azure:**
  - ExpressRoute Circuit (Standard or Premium)
  - Azure Virtual Network Gateway
  - Azure Virtual Network Peering (if cross-region)
  - Network Security Groups (for segmentation/controls)
  - Azure Application Services (if relevant workloads)
- **OCI:**
  - FastConnect Circuit (via provider or direct)
  - Virtual Cloud Network (VCN)
  - Dynamic Routing Gateway (DRG)
  - Service Gateway (if OCI native services)
  - Compute/Database Service (if part of the data flow)

---

## SKU List, Usage Assumptions & Pricing (per month)

| Component                     | SKU/Service Name        | Usage Assumption         | Monthly Price (Estimate) |
|-------------------------------|-------------------------|--------------------------|--------------------------|
| Azure ExpressRoute (Standard) | Standard Circuit        | 1 Gbps, 2 circuits for HA| $1,000                   |
| ExpressRoute Premium Add-on   | Premium                 | (Optional, for global reach) | $300                 |
| Azure Virtual Network Gateway | ErGw3AZ                 | 1 per region             | $276                     |
| OCI FastConnect               | FastConnect Direct      | 1 Gbps, 2 connections for HA | $316.20               |
| OCI Dynamic Routing Gateway   | DRG                     | 1 per VCN                | Included                 |
| OCI VCN                       | VCN                     | 1 per region             | Included                 |
| Data Transfer (Egress)        | Azure & OCI             | 10TB/month bi-directional| $150 (Azure side)        |
| Managed Network Service       | -                 | Support/monitoring       | $300                     |

> *Pricing is for reference only; check [Azure ExpressRoute Pricing](https://azure.microsoft.com/en-us/pricing/details/expressroute/) and [OCI FastConnect Pricing](https://www.oracle.com/cloud/networking/fastconnect/pricing/) for up-to-date rates. Data transfer costs may vary based on usage and inter-region routing.*

---

## BOM Table

| Service                     | Paid to    | SKU/Service Name          | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                         |
|-----------------------------|------------|---------------------------|-------|---------------------|---------------------|-------------------------------|
| ExpressRoute Circuit        | Azure      | Standard Circuit          | 2     | $1,000              | $12,000             | Microsoft Azure               |
| ExpressRoute Premium (Opt.) | Azure      | Premium Add-on            | 1     | $300                | $3,600              | Microsoft Azure               |
| Virtual Network Gateway     | Azure      | ErGw3AZ                   | 1     | $276                | $3,312              | Microsoft Azure               |
| FastConnect Circuit         | OCI        | FastConnect Port          | 2     | $316.20             | $3,794.40           | Oracle Cloud Infrastructure   |
| DRG / VCN                   | OCI        | DRG, VCN                  | -     | Included            | Included            | Oracle Cloud Infrastructure   |
| Data Transfer (Egress)      | Azure/OCI  | Outbound Data Transfer    | -     | $150                | $1,800              | Example, see note             |
| Managed Network Service     | Partner    | Managed Network Service   | -     | $300                | $3,600              | Paid to Partner               |
| **Total**                   |            |                           |       | **$2,342.20**       | **$28,106.40**      |                               |

*Data Transfer/Egress: Outbound data transfer is billed by the originating cloud provider. Example shown; actual costs depend on usage and direction.*

---

## Value Proposition

### For the Partner
- Recurring revenue from managed network service contracts
- Upsell of advanced support, network monitoring, optimization services
- Professional services for architecture, migration, and DR setup

### For the Customer
- Enterprise-grade, low-latency, highly available multi-cloud connectivity
- Foundation for advanced hybrid architectures (DR, analytics, real-time integration)
- Improved operational reliability and scalability

---

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For                    | Sample Total (Monthly USD) |
|---------------------|----------------------------------------------|----------------------------|
| Azure               | ExpressRoute, Premium, Gateway, Data Transfer| $1,876                     |
| OCI                 | FastConnect, Data Transfer, VCN/DRG         | $632.40                    |
| Partner             | Managed Network Service                      | $300                       |

*Sample totals above are for illustration and will vary based on configuration, usage, and data transfer volume.*