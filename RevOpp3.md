# Revenue Opportunity #3: Split Stack Architecture (Azure Applications Integrated with OCI Services)

## Storyboard

## Storyboard

A global enterprise has its customer-facing or business-critical applications running on Microsoft Azure (using services such as Azure App Service, AKS, or Virtual Machines). These applications require robust, high-performance, and highly available Oracle database services provisioned on Oracle Cloud Infrastructure (OCI). The application tier on Azure connects directly to the database tier on OCI over a secure, dedicated, low-latency Interconnect (Azure ExpressRoute + OCI FastConnect). This "split stack" architecture leverages best-in-class Azure application development and user experience, while benefiting from Oracle's database technologies on OCI.

## Typical Use Cases
- Modern web or mobile apps on Azure, with Oracle DB backend on OCI
- Large-scale business applications or custom middleware requiring Oracle DB features not available natively on Azure
- Seamless lift-and-shift or modernization projects where applications migrate to Azure, but databases remain (or are upgraded) on OCI

## Key Business Outcomes
- Best of both clouds: Azure for application innovation, OCI for database performance & compliance
- Consistent low-latency connectivity (ExpressRoute + FastConnect)
- Simplified migration path for enterprise apps
- Increased network, database, and managed service consumption

---

## Azure & OCI Components

- **Azure:**
  - Azure App Service or AKS (Kubernetes Service) or Virtual Machines
  - Azure Virtual Network
  - ExpressRoute Circuit (Standard or Premium)
  - Virtual Network Gateway

- **OCI:**
  - Autonomous Database or Exadata DB System
  - FastConnect Circuit
  - Virtual Cloud Network (VCN)
  - Dynamic Routing Gateway (DRG)

---

## SKU List, Usage Assumptions & Pricing (per month)

| Component                    | SKU/Service Name           | Usage Assumption          | Monthly Price (Estimate) |
|------------------------------|----------------------------|--------------------------|--------------------------|
| Azure App Service            | P3v3 (Premium V3, 8 cores) | 1 instance, 730 hours    | $618                     |
| ExpressRoute (Standard)      | Standard Circuit           | 1 Gbps, 2 circuits for HA| $1,000                   |
| Virtual Network Gateway      | ErGw3AZ                    | 1 per region             | $276                     |
| FastConnect                  | FastConnect Direct         | 1 Gbps, 2 connections    | $316.20                  |
| Autonomous Database          | 8 peak/3 base ECPU, 1TB + 3TB backup, autoscaling enabled | 730 hours                | $1,130.77                |
| Data Transfer (Egress)       | Azure & OCI                | 5TB/month bi-directional | $80 (Azure side)         |
| Managed Integration Service  | Partner                    | Monitoring/support       | $300                     |

---

## BOM Table

| Service                     | Paid to    | SKU/Service Name        | Qty   | Monthly Price (USD) | Annual Price (USD) | Notes                    |
|-----------------------------|------------|-------------------------|-------|---------------------|---------------------|--------------------------|
| Azure App Service           | Azure      | P3v3                    | 1     | $618                | $7,416              | Microsoft Azure          |
| ExpressRoute Circuit        | Azure      | Standard Circuit        | 2     | $2,000              | $24,000             | Microsoft Azure          |
| Virtual Network Gateway     | Azure      | ErGw3AZ                 | 1     | $276                | $3,312              | Microsoft Azure          |
| FastConnect Circuit         | OCI        | FastConnect Port        | 2     | $632.40             | $7,588.80           | Oracle Cloud Infrastructure |
| Autonomous Database         | OCI        | 8 peak/3 base ECPU, 1TB + 3TB backup, autoscaling enabled | 1     | $1,130.77           | $13,569.24           | Oracle Cloud Infrastructure |
| Data Transfer (Egress)      | Azure/OCI  | Outbound Data Transfer  | -     | $80                 | $960                | Example, see note        |
| Managed Integration Service | Partner    | Integration Service     | -     | $300                | $3,600              | Paid to Partner          |
| **Total**                   |            |                         |       | **$5,037.17**       | **$60,446.04**      |                          |

*Data Transfer/Egress: Outbound data transfer is billed by the originating cloud provider. Example shown; actual costs depend on usage and direction.*

---

## Value Proposition

### For the Partner
- Recurring revenue from managed integration/monitoring services
- Consulting/professional services for architecture, migration, and modernization
- Ongoing support for multi-cloud operations

### For the Customer
- Enterprise-class, low-latency, highly available integration between Azure applications and OCI databases
- No compromise on app development speed or DB feature set
- Future-proofed for further cloud adoption, migration, or hybrid extensions

---

## Who Gets Paid for What?

| Institution         | Example Services Paid For                    | Sample Total (Monthly USD) |
|---------------------|----------------------------------------------|----------------------------|
| Azure               | App Service, ExpressRoute, Gateway, Data Transfer | $2,974           |
| OCI                 | FastConnect, Autonomous DB, Data Transfer         | $1,763.17        |
| Partner             | Managed Integration/Support Service               | $300             |

*Sample totals above are for illustration and will vary based on configuration, usage, and data transfer volume.*