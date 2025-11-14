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

## 🧠 Skills Demonstrated

This project showcases a full SAP MM Functional Consultant skillset, including:

### 🔧 SAP MM Configuration & Functional Skills
- Material Master configuration (MM01/MM02)
- Vendor Master setup (BP transaction)
- Purchase Requisition → Purchase Order flow
- Release strategy configuration
- Source determination & info records
- Pricing conditions & schema logic
- Goods Receipt (MIGO) & Inventory management
- Invoice Verification (MIRO)

### 📊 Business Analysis & Requirements Mapping
- Translating business pain points into SAP MM solutions
- Process mapping using BPMN-style flow diagrams
- Stakeholder requirement gathering
- Gap analysis between AS-IS and TO-BE processes

### 🧪 Testing & Validation
- Creating detailed test scripts and acceptance criteria
- Validating configuration outcomes through scenario testing
- Ensuring traceability from requirements → config → test case

### 🗂 Documentation & Project Delivery
- Clear repository structure for professional documentation
- Well-defined configuration notes and design decisions
- Realistic P2P end-to-end case study modelling a real client


## 📘 Table of Contents  

1. [Overview](#1-overview)  
2. [Business Context](#2-business-context)  
3. [Repository Structure](#3-repository-structure)  
4. [Documentation Links](#4-documentation-links)  
5. [How to Navigate This Project](#5-how-to-navigate-this-project)  
6. [Future Enhancements](#6-future-enhancements)

## 📁 Repository Structure

The project is structured to clearly separate configuration, design decisions, diagrams, test cases, and main documentation.



The repository is organised to clearly separate requirements, design, test cases, and diagrams for the SAP MM Procure-to-Pay (P2P) project.
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




## 2. Business Context

**Company:** Log360 T/A Karukweza EcoFarm  
**Industry:** Agriculture, farming, and logistics  

### Pain Points:

- Unstructured purchasing (manual spreadsheets, calls, WhatsApp)
- No visibility of stock levels across storage locations
- Repeated stockouts of critical inputs (feed, medicines)
- No vendor performance tracking
- High losses due to poor inventory reconciliation

### Project Goal

To design a **scalable SAP MM Procure-to-Pay process** that solves these operational problems and improves procurement efficiency for Log360.

---

