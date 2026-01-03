# 05 – Test Scenarios  
**SAP MM Procure-to-Pay (P2P) – Log360 Scenario**

---

## 1. Purpose of This Document

This document defines the **end-to-end business test scenarios** used to validate the SAP MM Procure-to-Pay (P2P) solution for the Log360 scenario.

The test scenarios ensure that:
- Business requirements are met
- Configuration supports real operational workflows
- MM–FI integration behaves as expected
- Controls and approvals function correctly

> These are **business-aligned test scenarios**, not technical unit tests.

---

## 2. Testing Scope

### 2.1 In Scope
- Procure-to-Pay lifecycle (PR → PO → GR → IR)
- Stock and consumable procurement
- Inventory movements
- Invoice verification (3-way matching)
- Master data usage
- Integration touchpoints with FI

### 2.2 Out of Scope
- Custom ABAP testing
- SAP SD and PP execution
- Advanced MRP optimisation
- Warehouse Management (WM/EWM)

---

## 3. Test Strategy

Testing is performed using:
- Representative master data
- Realistic quantities and prices
- Business-driven scenarios
- Exception-based validation

Each test case includes:
- Business context
- Key steps
- Expected results

---

## 4. End-to-End Test Scenarios

---

### TS-01: Standard Stock Procurement (Animal Feed)

**Business Scenario**  
Log360 procures pig feed to replenish stock at the main farm.

**Steps**
1. Create Purchase Requisition for feed material
2. Convert PR to Purchase Order
3. Post Goods Receipt into storage location
4. Post Vendor Invoice
5. Complete payment (FI reference)

**Expected Results**
- Stock quantity updated
- GR/IR account posted correctly
- Invoice matched successfully
- No manual adjustments required

---

### TS-02: Consumption-Based Procurement (Consumables)

**Business Scenario**  
Procurement of low-value consumables (chemicals, packaging).

**Steps**
1. Create PO with account assignment
2. Post Goods Receipt (optional)
3. Post Invoice directly

**Expected Results**
- No stock created
- Expense posted directly to cost centre
- FI posting correct

---

### TS-03: Invoice Quantity Mismatch (3-Way Match Failure)

**Business Scenario**  
Vendor invoice quantity exceeds goods received.

**Steps**
1. Create PO
2. Post partial Goods Receipt
3. Post Invoice with higher quantity

**Expected Results**
- Invoice blocked
- Discrepancy visible in Invoice Verification
- Manual resolution required

---
### TS-04: Price Variance Handling

**Business Scenario**  
Invoice price differs from PO price.

**Steps**
1. Create PO with agreed price
2. Post GR
3. Post Invoice with higher price

**Expected Results**
- Invoice posted with variance
- Price difference handled per tolerance settings
- Correct FI posting

---
### TS-05: Internal Stock Transfer

**Business Scenario**  
Feed stock is moved between storage locations.

**Steps**
1. Create Stock Transfer Posting
2. Post Goods Issue from source location
3. Post Goods Receipt into destination location

**Expected Results**
- Stock reduced at source
- Stock increased at destination
- No financial posting (same plant)

---
### TS-06: Vendor Master Dependency Validation

**Business Scenario**  
Attempt to create PO using incomplete vendor master.

**Steps**
1. Create PO for vendor missing purchasing data

**Expected Results**
- System prevents PO creation
- Data dependency clearly identified

---
### TS-07: Material Master Dependency Validation

**Business Scenario**  
Attempt procurement using incomplete material master.

**Steps**
1. Create PR for material without accounting view

**Expected Results**
- Error message displayed
- Configuration dependency enforced

---
## 5. Negative & Exception Scenarios

- Missing valuation class
- Incorrect storage location
- Duplicate invoice posting attempt
- Invalid account assignment

All exceptions are expected to:
- Be system-controlled
- Provide clear error messaging
- Prevent incorrect postings

---
## 6. Test Data Assumptions

- Master data pre-created
- Standard SAP tolerance limits applied
- Single company code
- Single chart of accounts

---
## 7. Test Acceptance Criteria

The P2P solution is accepted when:
- All core scenarios execute successfully
- Exceptions behave as designed
- Inventory and FI postings reconcile
- No manual workarounds required

---
## 8. Business Value of Testing

- Reduces go-live risk
- Validates business readiness
- Confirms process controls
- Builds confidence for finance and operations

---

*This test scenario document reflects realistic SAP MM testing aligned with real-world agro-logistics operations and is intended for professional portfolio demonstration purposes.*
