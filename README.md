<p align="center">
  <img src="https://img.shields.io/badge/Project-SAP%20MM%20P2P-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Focus-Procure%20to%20Pay%20(P2P)-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Role-SAP%20MM%20Functional%20Consultant-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Docs-Updated-critical?style=for-the-badge" />
</p>

# SAP MM Procure-to-Pay Project – Log360 Scenario

## 1. Overview

This project simulates a real-world **SAP MM Functional Consultant** assignment.

I designed and documented an end-to-end **Procure-to-Pay (P2P)** process for a fictional agro-logistics company that procures farming inputs (e.g., pig feed, fertilizers, packaging) and manages stock across multiple locations.

The focus is on:

- Translating **business requirements** into an SAP MM design  
- Showing clear **configuration logic and trade-offs**  
- Defining **test scenarios** that a consultant or tester could execute in SAP  
- Documenting the **P2P flow**, from PR → PO → Goods Receipt → Invoice  

> ⚠️ **Note:** This is a documentation and design project. No SAP access is required to review, but the steps are written so they could be executed in SAP S/4HANA or ECC.

---

## 🧠 Skills Demonstrated

### 🔧 SAP MM Configuration & Functional Skills
- Material Master configuration (MM01/MM02)
- Vendor Master setup (BP)
- PR → PO flow with release strategy
- Source determination & info records
- Pricing schema configuration
- Goods Receipt (MIGO)
- Invoice Verification (MIRO)

### 📊 Business Analysis & Requirements Mapping
- Translating pain points into SAP solutions
- BPMN-style process diagrams
- Stakeholder requirement mapping
- AS-IS vs TO-BE gap analysis

### 🧪 Testing & Validation
- Writing test scripts
- Acceptance criteria definition
- Scenario-based validation

### 🗂 Documentation & Project Delivery
- Clean repository structure
- Professional SAP documentation flow
- Configuration notes & design decisions

---

## 📘 Table of Contents

1. [Overview](#1-overview)  
2. [Business Context](#2-business-context)  
3. [Repository Structure](#3-repository-structure)  
4. [Documentation Links](#4-documentation-links)  
5. [How to Navigate This Project](#5-how-to-navigate-this-project)  
6. [Future Enhancements](#6-future-enhancements)

---

# 2. Business Context

### 2.1 Company  
**Log360 T/A Karukweza Ecofarm**

### 2.2 Industry  
**Agriculture, farming, and logistics**

### 2.3 Pain Points
- Unstructured purchasing (manual spreadsheets, calls, WhatsApp)
- No visibility of stock across locations
- Frequent stockouts (feed, medicines)
- No vendor performance tracking
- Losses from poor inventory reconciliation

### 2.4 Project Goal
Design a **scalable SAP MM P2P process** to improve procurement efficiency and eliminate operational bottlenecks.

---

# 3. 📁 Repository Structure

The repository is organised to clearly separate requirements, design decisions, test cases, and diagrams.

<details>
<summary><strong>📁 Click to expand repository structure</strong></summary>

```md
📦 sap-mm-log360/
 ┣ 📂 docs/
 ┃ ┣ 📂 tradeoffs/
 ┃ ┃ ┗ 📄 design_tradeoffs.md
 ┃ ┣ 📂 tests/
 ┃ ┃ ┗ 📄 p2p_test_cases.md
 ┃ ┣ 📂 diagrams/
 ┃ ┃ ┗ 📄 README.md        # Lists & describes all P2P diagrams
 ┃ ┗ 📄 README.md          # Index of project documentation
 ┃
 ┗ 📄 README.md            # Main project documentation
