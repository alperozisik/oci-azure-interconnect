# Revenue Opportunity #1: Increased Network Consumption (ExpressRoute Growth)

## Storyboard

A global enterprise runs its core business applications on Microsoft Azure while hosting critical Oracle databases and analytics workloads on Oracle Cloud Infrastructure (OCI).  
To ensure seamless and secure data exchange—such as live transaction processing, data warehousing, and real-time analytics—between Azure and OCI, the customer implements a dedicated, high-throughput Interconnect leveraging Azure ExpressRoute and OCI FastConnect.

The architecture uses redundant ExpressRoute circuits for high availability. This design guarantees low-latency, high-bandwidth, and highly available connections between cloud environments, enabling mission-critical business flows to operate efficiently. The continuous data transfer and integration between environments drive up network bandwidth consumption, resulting in greater recurring revenue from network services.

**Multi-Region Note:**  
In scenarios where multiple Azure and/or OCI regions are utilized (e.g., for disaster recovery, regulatory compliance, or global high availability), additional services such as ExpressRoute Premium Add-on (for Azure) and OCI inter-region data transfer charges may apply. These should be reflected in both the architecture and BOM tables where relevant.

**Key business outcomes:**
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

| Service                        | Paid to    | SKU/Service Name          | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                         |
|--------------------------------|------------|---------------------------|-------|---------------------|---------------------|-------------------------------|
| ExpressRoute Circuit           | Azure      | Standard Circuit          | 2     | $1,000              | $12,000             | Microsoft Azure               |
| ExpressRoute Premium (Optional)| Azure      | Premium Add-on            | 1     | $300                | $3,600              | Microsoft Azure               |
| Virtual Network Gateway        | Azure      | ErGw3AZ                   | 1     | $276                | $3,312              | Microsoft Azure               |
| FastConnect Circuit            | OCI        | FastConnect Port          | 2     | $316.20             | $3,794.40           | Oracle Cloud Infrastructure   |
| DRG / VCN                      | OCI        | DRG, VCN                  | -     | Included            | Included            | Oracle Cloud Infrastructure   |
| Data Transfer (Egress)         | Azure/OCI  | Outbound Data Transfer    | -     | $150 (example)      | $1,800 (example)    | See notes below               |
| Managed Network Service        | Partner    | Managed Network Service   | -     | $300                | $3,600              | Paid to Partner               |
| **Total**                     |            |                           |       | **$2,342.20**       | **$28,106.40**      |                               |

**Data Transfer (Egress) Explanation:**  
- Outbound data transfer charges are billed by the cloud where the data originates.
    - OCI → Azure (via FastConnect): Paid to Oracle (OCI) at FastConnect rates.
    - Azure → OCI (via ExpressRoute): Paid to Microsoft (Azure) at ExpressRoute rates.
    - Inter-region traffic within OCI or Azure: Billed by the respective provider.

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

## Notes on Managed Network Service

"Managed Network Service" refers to the setup, ongoing monitoring, troubleshooting, optimization, and SLA management of ExpressRoute and FastConnect connections—delivered by the partner as a managed service. This is valuable for customers lacking deep multi-cloud network expertise or requiring higher SLAs and proactive support.

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For         | Sample Total (Monthly USD) |
|---------------------|-----------------------------------|----------------------------|
| Azure               | ExpressRoute, Premium, Gateway, Data Transfer | $1,876                  |
| OCI                 | FastConnect, Data Transfer, VCN/DRG           | $632.40                  |
| Partner             | Managed Network Service                         | $300                     |
| (Network Provider)  | Port/connection fees (only if a third-party network provider is used; usually not in direct Azure–OCI interconnect scenarios) | $0 (not included)        |

*Sample totals shown above are for illustration only and will vary based on configuration, usage, and data transfer volume.*