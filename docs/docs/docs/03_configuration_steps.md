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
`Enterprise Structure → Definition → Financ
