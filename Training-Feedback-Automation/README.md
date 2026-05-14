# Training Effectiveness & Manager Feedback Automation

**Domain:** Learning & Development Operations
**Tools:** Power Automate · Microsoft Excel · Outlook · SharePoint / OneDrive
**Type:** Scheduled Outreach & Feedback Collection Automation

---

## Overview

This project automates a training effectiveness feedback process that was previously executed entirely manually by the Learning team. The solution uses a structured Excel dataset as the source of truth and an automated outreach workflow to systematically collect feedback from line managers on how effectively employees are applying skills learned from training programs.

---

## Problem Statement

After employees attended learning programs, the Learning team needed feedback from line managers to assess:
- Whether skills were applied in day-to-day work
- Whether skills were used in live projects
- Overall effectiveness and impact of training programs

**Challenges with the manual process:**
- SPOCs manually contacted each manager individually
- Low response and conversion rate
- No systematic follow-up mechanism
- High operational effort for the Learning team
- Difficult to track pending vs completed feedback

---

## Solution

Designed an automation-driven feedback outreach process that:
- Uses an Excel tracker as the single source of truth
- Identifies pending feedback records automatically
- Groups requests by unique manager
- Sends one consolidated email per manager
- Clearly highlights which employee records require feedback
- Eliminates duplicate and manual follow-ups

---

## Input Data — Excel Tracker

The Excel sheet contains structured records including:
- Employee details
- Training / program attended
- Training category and duration
- Line manager name and email
- Feedback questions — usage, application, impact
- Feedback status — Pending / Completed
- Row numbers for reference

---

## End-to-End Workflow

```
Scheduled Run — Periodic
        ↓
Read Excel Training Records
        ↓
Filter Records — Feedback Status = Pending
        ↓
Identify Unique Managers
        ↓
Group Employee Rows by Manager
        ↓
Send One Consolidated Email per Manager
        ↓
Highlight Row Numbers Requiring Feedback Input
```

---

## Key Design Decisions

### 1. Excel as System of Record
- Leveraged existing Excel tracker already used by the Learning team
- Avoided migration overhead and tool change friction
- Preserved familiarity for stakeholders

### 2. Pending-Only Outreach
- Only records marked Pending are included
- Prevents redundant or unnecessary communication
- Improves response quality and manager experience

### 3. Manager-Centric Communication
- One consolidated email per manager — not one per employee
- Includes all employees reporting to that manager
- Clearly references row numbers for easy feedback entry

### 4. Scheduled Automation
- Runs on a fixed periodic schedule
- Enables systematic nudges without manual chasing
- Scales effortlessly as training records grow

---

## Manager Experience

Managers receive:
- A single consolidated email — not multiple separate requests
- Full context about the training program and feedback purpose
- Direct link to the Excel tracker
- Exact row numbers where feedback is required
- Clear guidance on which columns to update

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Power Automate | Workflow orchestration — scheduled trigger, filtering, grouping, sending |
| Microsoft Excel | Structured data source and system of record |
| Outlook | Consolidated automated email delivery to managers |
| SharePoint / OneDrive | File hosting for Excel tracker |

---

## Impact

- ✅ Reduced manual effort for Learning SPOCs significantly
- ✅ Improved manager response and completion rate
- ✅ Standardized feedback collection across all programs
- ✅ Better visibility into training effectiveness
- ✅ Enabled data-driven learning decisions

---

## What This Project Demonstrates

- Automation of operational learning processes
- Data-driven feedback collection at scale
- Stakeholder-friendly communication design — manager consolidation
- Scale-ready workflow thinking
- Practical use of existing enterprise tools without migration friction

---

> *Source code, flow definitions, and tenant-specific configurations are intentionally excluded to comply with enterprise confidentiality policies.*
