# 04 – Master Data Setup  
**SAP MM Procure-to-Pay (P2P) – Log360 Scenario**

---

## 1. Purpose of This Document

This document defines the **SAP MM master data design** required to support the Procure-to-Pay (P2P) process for the Log360 scenario.

It outlines:
- Required master data objects
- Key design decisions
- Governance considerations
- Dependencies between MM and FI

> This is a **design and setup reference**, not a transaction manual.

---

## 2. Master Data Principles

The following principles guided master data design:

- Standard SAP ECC 6.0 master data objects
- Single source of truth per master record
- Plant- and material-driven inventory control
- Tight integration between MM and FI
- Scalable design for future plants and materials

---

## 3. Material Master Design

### 3.1 Material Categories (Business View)

Materials procured by Log360 include:

- Animal feed (starter, grower, finisher)
- Seeds and fertilizers
- Veterinary medicines
- Packaging materials
- General consumables

---

### 3.2 Material Types

| Material Type | Usage |
|--------------|-------|
| ROH | Raw materials (feed, seed, fertilizer) |
| HIBE | Consumables (chemicals, packaging) |
| FERT | Finished goods (for stock produced internally) |

**Design Rationale**
- ROH enables stock valuation and inventory tracking
- HIBE supports consumption-based procurement
- Material types control valuation, account posting, and views

---

### 3.3 Required Material Views

| View | Purpose |
|-----|--------|
| Basic Data | Description, base unit of measure, material group |
| Purchasing | Procurement control, GR-based IV |
| MRP | Reorder and planning parameters |
| Accounting | Valuation class, price control |
| Storage | Warehouse and stock data |

---

### 3.4 Valuation & Price Control

- **Valuation Area:** Plant
- **Price Control:**
  `V` (Moving Average) for feed and consumables
  - `S` (Standard) optional for stable-price materials
 
  ---

## 4. Material Groups

Material groups are used for:
- Spend analysis
- Reporting
- Procurement categorisation

**Example Material Group Structure**

| Material Group | Description |
|---------------|------------|
| FEED | Animal feed |
| SEED | Seeds |
| FERT | Fertilizers |
| VET | Veterinary products |
| PACK | Packaging materials |
| CONS | General consumables |

---
## 5. Vendor Master Design

### 5.1 Vendor Categories

| Vendor Type | Description |
|------------|------------|
| Local Suppliers | Feed, seed, veterinary suppliers |
| Transport Vendors | Delivery and logistics providers |
| Service Providers | Maintenance and operational services |

---
### 5.3 Vendor Control Design

- One vendor per legal entity
- Naming conventions enforced to avoid duplicates
- Payment terms and reconciliation accounts managed via FI integration

---
## 6. Purchasing Info Records

Purchasing Info Records maintain **vendor–material relationships**.

### Key Uses:
- Vendor-specific pricing
- Planned delivery time
- Purchasing conditions

**Design Decision**
- Mandatory for high-volume materials (e.g. feed)
- Optional for low-value consumables

---
## 7. Source List (Optional Control)

Source Lists may be used to:
- Enforce approved vendors
- Restrict sourcing to preferred suppliers

**Design Choice**
- Enabled for critical materials (feed, medicines)
- Not enforced for low-risk consumables

---
## 8. Account Determination (Conceptual)

Material master data drives FI posting through:

| Field | Purpose |
|-----|--------|
| Valuation Class | Links material to G/L account |
| Material Type | Controls posting logic |
| Transaction Key | Determines debit/credit posting |

> Detailed FI configuration is out of scope, but MM–FI integration logic is documented.

---
## 9. Master Data Governance

### Controls Implemented
- Centralised material master creation
- Approval required for vendor creation
- Change logs enabled
- Naming standards enforced

### Risks Mitigated
- Duplicate master records
- Incorrect valuation classes
- Financial posting errors

---
## 10. Dependencies & Assumptions

- Organisational structure is configured
- Chart of accounts is available
- Plants and storage locations are active
- No custom master data fields are used

---
## 11. Business Value

Effective master data design enables:
- Accurate inventory valuation
- Controlled procurement processes
- Reliable reporting
- Audit-ready Procure-to-Pay execution

---

*This document reflects a realistic SAP MM master data setup aligned to real-world agro-logistics operations and is intended for professional portfolio demonstration purposes.*
