# 01 – Business Requirements  
**SAP MM Procure-to-Pay (P2P) – Log360 Scenario**

---

## 1. Business Context

Log360 is an agro-logistics and farming operation managing piggery and horticulture activities across multiple locations. The organisation procures critical operational inputs including animal feed, seeds, fertilisers, veterinary medicines, packaging materials, and general consumables.

Procurement efficiency and inventory availability directly impact livestock health, crop cycles, and service continuity. As operations scale, Log360 requires a structured and controlled **Procure-to-Pay (P2P)** process to improve visibility, accountability, and financial integration.

This document summarises the **business requirements** driving the SAP MM solution design.

---

## 2. Current-State Challenges (AS-IS)

### Procurement
- Purchase requests are raised with limited standardisation.
- Approval controls vary by material type and urgency.
- Accountability for purchasing decisions is inconsistent.

### Inventory Management
- Stock is held across multiple physical locations (feed stores, seed rooms, veterinary stores).
- Limited visibility of stock consumption versus procurement.
- Risk of stockouts for critical materials such as feed and veterinary inputs.

### Invoice & Cost Control
- Invoices do not always align with delivered quantities or agreed prices.
- Manual reconciliation between procurement and finance.
- Limited audit trail linking PR → PO → GR → Invoice.

### Master Data
- Inconsistent material and vendor categorisation.
- Risk of duplicate or incomplete master records.
- Weak linkage between material type, valuation, and financial posting logic.

---

## 3. Business Objectives (TO-BE)

The SAP MM implementation aims to:

- Establish a **controlled end-to-end Procure-to-Pay process**.
- Improve **inventory visibility** at plant and storage location level.
- Enforce **procurement approval and accountability**.
- Enable **3-way matching** (PO–GR–Invoice).
- Ensure **accurate financial integration** with SAP FI.
- Standardise master data to support reporting and audit requirements.

---

## 4. Scope Definition

### In Scope
- SAP MM Procure-to-Pay (PR → PO → GR → IR).
- Stock and consumption-based procurement.
- Multi-plant and multi-storage location inventory management.
- Material and vendor master data design.
- Conceptual integration with SAP FI.
- End-to-end business scenario testing.

### Out of Scope
- Custom ABAP development.
- Advanced MRP optimisation beyond basic setup.
- Warehouse Management (WM/EWM).
- SAP SD execution (referenced only for future integration).

---

## 5. Key Business Requirements

### Procurement Requirements
- Ability to raise Purchase Requisitions by material category.
- Clear responsibility via Purchasing Organisations and Purchasing Groups.
- Conversion of PRs into POs with vendor-specific pricing.
- Support for both plant-specific and central procurement scenarios.

### Inventory Requirements
- Stock tracking by Plant and Storage Location.
- Support for different stock types.
- Accurate posting of Goods Receipts and Goods Issues.
- Internal stock transfers between locations.

### Invoice Verification Requirements
- Enforced 3-way matching for stock procurement.
- Automatic posting to GR/IR clearing accounts.
- Ability to block invoices when discrepancies exist.
- Clear audit trail for invoice resolution.

### Master Data Requirements
- Standardised material types and material groups.
- Vendor master records with purchasing and FI views.
- Purchasing Info Records for pricing and conditions.
- Field controls to enforce data quality.

---

## 6. Assumptions & Constraints

- SAP ECC 6.0 environment.
- Standard SAP MM functionality only.
- No client-specific or proprietary data used.
- Single chart of accounts.
- Focus on operational stability over complexity.

---

## 7. Success Criteria

The solution will be considered successful if:

- All procurement follows PR → PO → GR → IR flow.
- Stock balances are accurate and visible per location.
- Invoice discrepancies are detected automatically.
- Master data quality issues are reduced.
- Finance and operations share a single source of truth.

---

## 8. Business Value

- Reduced procurement risk and improved audit compliance.
- Better cost control and spend visibility.
- Improved operational continuity and reduced stockouts.
- Strong foundation for future SAP extensions (SD, PP, analytics).

---

*This document represents a business requirements summary derived from real-world agro-logistics operations and is intended for professional SAP MM portfolio demonstration purposes.*
