# SAP MM Procure-to-Pay Project – Log360 Scenario

## 1. Overview

This project simulates a real-world **SAP MM Functional Consultant** assignment.

I designed and documented an end-to-end **Procure-to-Pay (P2P)** process for a fictional agro-logistics company that procures farming inputs (e.g. pig feed, fertilizers, packaging) and manages stock in multiple locations.

The focus is on:

- Translating **business requirements** into SAP MM design
- Showing clear **configuration logic and trade-offs**
- Defining **test scenarios** that a consultant or tester could execute in an SAP system

> ⚠️ Note: This is a documentation and design project. No SAP access is required to review it, but the steps are written so they could be executed in an SAP S/4HANA or ECC sandbox.

## 📘 Table of Contents

1. Overview  
2. Business Context  
3. Repository Structure  
4. Documentation Links  
5. How to Navigate This Project  
6. Future Enhancements  


## 2. Business Context

**Company:** Log360 T/A Karukweza EcoFarm  
**Industry:** Agriculture, farming and logistics  
**Pain points:**

- Unstructured purchasing (manual spreadsheets, phone calls)
- No visibility on stock levels across storage locations
- Frequent stockouts of critical inputs (feed, medicines)
- Poor control on price variance and supplier performance

**Project Objectives:**

1. Design a standardized **Procure-to-Pay** process.
2. Define **organizational structure** and **master data** for MM.
3. Enable basic **inventory visibility** across plants and storage locations.
4. Lay the foundation for **financial integration** (GR/IR, stock valuation).

---

## 3. Scope

### In Scope

- MM Organization Structure
  - Company Code, Plant(s), Storage Locations, Purchasing Org, Purchasing Groups
- Master Data
  - Material Master (raw materials, operating supplies)
  - Vendor Master (domestic suppliers)
  - Info Records & Source List (for key materials)
- Procurement Process
  - Purchase Requisitions
  - Purchase Orders
  - Goods Receipt
  - Invoice Verification (MM–FI integration)
- Inventory Management
  - Stock type handling (unrestricted, blocked)
  - Simple stock transfers between storage locations

### Out of Scope (Future Enhancements)

- MRP / automatic PR generation  
- Batch management & quality management  
- Advanced pricing and condition techniques  
- Integration to SD and Production Planning  

---

## 4. High-Level Process Flow (P2P)

1. **Requirement Identification**
   - Farm Operations Manager identifies low stock (e.g., pig feed).
   - Create **Purchase Requisition (PR)** in SAP.

2. **Sourcing & Ordering**
   - Convert PR to **Purchase Order (PO)**.
   - Vendor pricing driven by Info Records OR manual entry.

3. **Goods Receipt**
   - Post **Goods Receipt** (GR).
   - Stock increases in the storage location.
   - FI entry posted (Dr Stock / Cr GR/IR).

4. **Invoice Posting**
   - Perform **Invoice Verification** (3-way match).
   - GR/IR cleared; vendor payable created.

---

## 5. Repository Structure
sap-mm-log360/
├── README.md
├── docs/
│   ├── 01_business_requirements.md
│   ├── 02_solution_design.md
│   ├── 03_configuration_steps.md
│   ├── 04_master_data_setup.md
│   └── 05_test_scenarios.md
├── tradeoffs/
│   └── design_tradeoffs.md
├── tests/
│   └── p2p_test_cases.md
└── diagrams/
    ├── p2p_process_flow.png
    └── org_structure.png


---

## 6. How to Use This Repository

This repository is intended to demonstrate:

- My ability to **analyze business requirements**
- Translate them into **SAP MM configuration**
- Create **test cases** that validate end-to-end P2P processes
- Document **trade-offs and design decisions**
- Communicate clearly in a consultant-ready format

---

## 7. Key Design Highlights

- Clean and realistic MM organization structure  
- Appropriately chosen valuation methods (MAP vs Standard)
- Clear PR → PO → GR → Invoice flow  
- Trade-off decisions documented  
- Test cases representing real SAP system behavior

---

## 8. Future Enhancements

- Add MRP scenario with automatic PR creation  
- Introduce batch management for feed and medicines  
- Add price variance analytics  
- Add Fiori app mapping for S/4HANA  

---

## 9. Contact

If you’d like to discuss this project or my SAP MM experience:

- **LinkedIn:** https://www.linkedin.com/in/munyaradzi-mangwiro  
- **Email:** mamangwiro@logstica360.com


