# 03 – Configuration Steps  
**SAP MM Procure-to-Pay (P2P) – Log360 Scenario**

---

## 1. Purpose of This Document

This document outlines the **key SAP MM configuration steps** required to implement the Procure-to-Pay (P2P) solution designed for Log360.

It focuses on:
- Logical configuration sequencing
- Alignment to business requirements
- Standard SAP ECC 6.0 configuration paths (SPRO)

This is **not a click-by-click guide**, but a **consultant-level configuration blueprint**.

---

## 2. Configuration Scope & Assumptions

### In Scope
- SAP MM organisational structure
- Procurement configuration
- Inventory Management setup
- Invoice Verification configuration
- Master data dependencies

### Out of Scope
- Custom ABAP development
- Advanced workflow configuration
- SAP FI detailed configuration (integration touchpoints only)

---

## 3. Organisational Structure Configuration

### 3.1 Define Company Code
**SPRO Path:**  
`Enterprise Structure → Definition → Financial Accounting→ Define, Copy, Delete, Check Company Code`

- Single Company Code created for Log360
- Assigned Chart of Accounts
- Currency and fiscal year variant defined

---

### 3.2 Define Plants
**SPRO Path:**  
`Enterprise Structure → Definition → Logistics – General → Define, Copy, Delete, Check Plant`

- Plants represent physical operational locations
- Each plant assigned to the Company Code

---
### 3.3 Define Storage Locations
**SPRO Path:**  
`Enterprise Structure → Definition → Materials Management → Define Storage Location`

- Storage locations created per plant to reflect physical stock separation
- Examples:
  - Feed store
  - Veterinary store
  - Seed and fertiliser store

---

### 3.4 Define Purchasing Organisation
**SPRO Path:**  
`Enterprise Structure → Definition → Materials Management → Define Purchasing Organisation`

- Single Purchasing Organisation created
- Assigned to Company Code

---

### 3.5 Define Purchasing Groups
**SPRO Path:**  
`Enterprise Structure → Definition → Materials Management → Define Purchasing Groups`

- Purchasing Groups represent buyer responsibility areas
- Examples:
  - Feed procurement
  - Agricultural inputs
  - General consumables
 
  ---

### 3.6 Assign Organisational Units
**SPRO Path:**  
`Enterprise Structure → Assignment`

Assignments include:
- Plant → Company Code
- Purchasing Organisation → Company Code
- Purchasing Organisation → Plant

  ---

## 4. Master Data Configuration Foundations

### 4.1 Define Material Types
**SPRO Path:**  
`Logistics – General → Material Master → Basic Settings → Material Types → Define Attributes of Material Types`

- Material types defined to reflect business usage
- Field control and quantity/value updates reviewed


---

### 4.2 Define Material Groups
**SPRO Path:**  
`Logistics – General → Material Master → Settings for Key Fields → Define Material Groups`

- Used for reporting and spend analysis
- Supports procurement categorisation

---

### 4.3 Configure Number Ranges
**SPRO Path:**  
`Logistics – General → Material Master → Basic Settings → Define Number Ranges`

- Separate number ranges for materials and vendors
- Supports clarity and auditability

---
## 5. Procurement Configuration

### 5.1 Define Purchase Requisition Settings
**SPRO Path:**  
`Materials Management → Purchasing → Purchase Requisition`

Key settings include:
- PR document types
- Field selection
- Release strategy placeholders (conceptual)

---
### 5.2 Define Purchase Order Types
**SPRO Path:**  
`Materials Management → Purchasing → Purchase Order → Define Document Types`

- Standard PO types configured
- Controls number ranges and allowed item categories

---
### 5.3 Assign Purchasing Info Records
**SPRO Path:**  
`Materials Management → Purchasing → Info Record`

- Enables vendor-specific pricing
- Reduces manual price entry errors
- Supports consistent procurement execution

---
## 6. Inventory Management Configuration

### 6.1 Define Movement Types
**SPRO Path:**  
`Materials Management → Inventory Management → Movement Types`

- Standard SAP movement types used (e.g. GR, GI, transfer postings)
- No custom movement types required

---
### 6.2 Configure Valuation Areas
**SPRO Path:**  
`Materials Management → Valuation and Account Assignment → Define Valuation Control`

- Valuation set at Plant level
- Supports accurate inventory valuation

---
### 6.3 Assign Valuation Classes
**SPRO Path:**  
`Materials Management → Valuation and Account Assignment → Account Determination`

- Material types linked to valuation classes
- Enables correct financial postings

---
## 7. Invoice Verification Configuration

### 7.1 Configure Invoice Verification Settings
**SPRO Path:**  
`Materials Management → Logistics Invoice Verification`

- Three-way matching enabled (PO–GR–Invoice)
- Tolerance limits reviewed

---
### 7.2 GR/IR Clearing Logic
**SPRO Path:**  
`Materials Management → Valuation and Account Assignment → Account Determination`

- GR/IR clearing accounts assigned
- Automatic clearing upon invoice posting

---
## 8. Integration Touchpoints (MM–FI)

While FI configuration is not detailed, the following integrations are ensured:
- Goods Receipt → Inventory & GR/IR posting
- Invoice Posting → Vendor and GR/IR clearing
- Valuation classes drive account determination

---
## 9. Testing Readiness

Configuration supports:
- End-to-end P2P testing (PR → PO → GR → IR)
- Stock and valuation validation
- Invoice discrepancy scenarios

Detailed test cases are documented in `05_test_scenarios.md`.

---
## 10. Configuration Summary
This configuration approach:
- Aligns directly to approved business requirements
- Uses standard SAP MM best practices
- Supports auditability and scalability
- Provides a strong foundation for future extensions

---
*This document reflects a real-world SAP MM configuration approach and is intended for professional portfolio demonstration purposes.*


