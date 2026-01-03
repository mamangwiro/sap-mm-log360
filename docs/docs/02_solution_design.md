# 02 – Solution Design  
**SAP MM Procure-to-Pay (P2P) – Log360 Scenario**

---

## 1. Solution Overview

This document describes the **SAP MM solution design** for the Log360 Procure-to-Pay (P2P) process.  
The design translates the approved **Business Requirements** into a structured SAP MM configuration aligned with standard best practices.

The solution focuses on:
- Controlled procurement
- Accurate inventory management
- Seamless integration with Finance
- Scalability across multiple operational locations

---

## 2. Design Principles

The following principles guided the solution design:

- **Standard SAP First** – Use standard SAP MM functionality wherever possible.
- **Simplicity over Complexity** – Prioritise operational stability and usability.
- **Business Accountability** – Clear ownership through organisational structure.
- **Auditability** – End-to-end traceability from requisition to invoice.
- **Scalability** – Support future growth in plants, materials, and vendors.

---

## 3. Organisational Structure Design

### Company Code
- Single Company Code representing Log360.
- Shared Chart of Accounts to support financial consistency.

### Plants
Plants represent **physical operational locations**, such as:
- Piggery operations
- Horticulture production sites

Each plant is responsible for:
- Stock ownership
- Goods movements
- Local consumption tracking

### Storage Locations
Storage locations are defined within plants to reflect **physical stock separation**, for example:
- Feed stores
- Veterinary medicine stores
- Seed and fertiliser stores

This enables accurate stock visibility and targeted inventory control.

### Purchasing Organisation
- Single Purchasing Organisation aligned to the Company Code.
- Centralised procurement control with visibility across plants.

### Purchasing Groups
Purchasing Groups are used to enforce **responsibility and accountability**, e.g.:
- Feed procurement
- Agricultural inputs
- General consumables

---

## 4. Procurement Process Design

### Procurement Type
The solution supports:
- **Stock procurement** for regularly consumed materials.
- **Consumption-based procurement** for indirect or non-stock items.

### Purchase Requisition (PR)
- PRs are raised by operational users at plant level.
- Material category and plant determine approval and processing logic.
- PRs serve as the formal demand signal.

### Purchase Order (PO)
- PRs are converted into POs by the Purchasing Team.
- POs reference approved vendors and pricing.
- Purchasing Info Records support consistent pricing and conditions.

### Approval Controls
- Approval logic is driven by:
  - M
