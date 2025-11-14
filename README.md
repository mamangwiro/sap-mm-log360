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

## 📘 Table of Contents  

1. [Overview](#1-overview)  
2. [Business Context](#2-business-context)  
3. [Repository Structure](#3-repository-structure)  
4. [Documentation Links](#4-documentation-links)  
5. [How to Navigate This Project](#5-how-to-navigate-this-project)  
6. [Future Enhancements](#6-future-enhancements)

---

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

## 3. Repository Structure

