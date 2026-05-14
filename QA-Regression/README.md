# Automated Regression Analysis & Reporting Pipeline

**Domain:** QA & Release Management
**Tools:** Power Automate · SharePoint Lists · HTML Reporting · Outlook
**Type:** End-to-End Process Automation

---

## Overview

This project automates the end-to-end processing of QA regression test results shared via unstructured emails. The solution converts raw regression emails into structured, comparable, and decision-ready insights for Business Analysts and Product Managers — eliminating manual analysis entirely.

---

## Problem Statement

QA teams shared regression results via large text-based emails containing module-wise metrics — Expected, Passed, Failed, Executed, Unexecuted — across ~90 modules per cycle.

**Challenges:**
- Manual comparison with previous cycles
- High risk of missed regressions
- Time-consuming analysis across ~90 modules
- No centralized historical record
- Subjective interpretation of results

---

## Solution

Designed and implemented an automated workflow that:
- Listens for incoming QA regression emails
- Extracts cycle and module-level metrics
- Compares current results with the previous cycle
- Calculates deltas and identifies regressions
- Classifies each module with a clear status
- Stores historical data centrally in SharePoint
- Sends a clean, consolidated HTML summary email to stakeholders

The entire process runs without any manual intervention.

---

## End-to-End Workflow

```
QA Regression Email Received
        ↓
Email Parsing & Normalization
        ↓
Cycle Detection & Date Extraction
        ↓
Module-wise Metric Extraction
        ↓
Historical Comparison — Previous Cycle
        ↓
Delta Calculation
        ↓
Status Classification
        ↓
Central Storage → SharePoint
        ↓
Automated HTML Summary Email → BAs & PMs
```

---

## Key Design Decisions

### 1. Cycle Management
- Extracts regression date from email subject automatically
- Determines next cycle number without manual input
- Handles first-run and missing historical data safely

### 2. Metric Extraction
For each module — Expected, Passed, Failed, Executed, Unexecuted — all normalized into integers for accurate comparison

### 3. Delta Analysis
Each module compared with previous cycle:
- Δ Failed
- Δ Executed
- Δ Unexecuted

### 4. Status Classification

| Condition | Status |
|---|---|
| No change in deltas | NO CHANGE |
| Failed tests decreased | IMPROVED |
| Failed tests increased | REGRESSION FAILS |

Removes the need for stakeholders to interpret raw numbers.

---

## Input & Output

**Input — Raw QA Regression Email**
```
Subject: vlmazOmniApp001 moddev CART result 20260314

*** EXPECTED NUMBER OF TEST CASES:   237,122
*** Number of Passed Tests:           237,097
*** Number of Failed Tests:           25
*** Total Number of Tests Executed:   237,122
*** Number of Unexecuted Tests:       0
```

**Output — Automated HTML Summary Email**

| Module | Δ Executed | Δ Failed | Δ Unexecuted | Status |
|---|---|---|---|---|
| OCSO | 0 | 1 | 0 | REGRESSION FAILS |
| SP | 0 | 1 | 0 | REGRESSION FAILS |
| ST | 0 | 0 | 0 | NO CHANGE |
| TA | 0 | -1 | 0 | IMPROVED |
| TX | 0 | 0 | 0 | NO CHANGE |

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Power Automate | Workflow orchestration — trigger, parse, compare, send |
| SharePoint Lists | Central system of record and historical data |
| HTML Generation | Formatted summary email output |
| Outlook | Automated email delivery to stakeholders |

---

## Impact

- ✅ Reduced manual analysis effort to zero
- ✅ Faster and more reliable release decisions
- ✅ Eliminated subjective interpretation of regression results
- ✅ Scales across ~90 modules per cycle
- ✅ Fully auditable historical record in SharePoint

---

## What This Project Demonstrates

- End-to-end automation thinking — from trigger to output
- Data normalization and comparison logic
- Stakeholder-focused output design
- Scalable and auditable workflow architecture
- Business process automation using Microsoft Power Platform

---

> *Source code, flow definitions, and tenant-specific configurations are intentionally excluded to comply with enterprise confidentiality policies.*
