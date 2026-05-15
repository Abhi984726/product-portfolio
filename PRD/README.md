# PRD Portfolio — Retail Lending Domain

**Domain:** Retail Lending — FIS Modern Banking Platform (MBP)
**Products Covered:** Term Loan · Line of Credit (LOC) · BNPL
**Clients:** Fifth Third Bank · BMO · American Express · SMBC

---

## Context

These PRDs are based on real lending workflows from the FIS Modern Banking Platform (MBP) — a core banking platform used by institutional banking clients globally. As a Product Owner at FIS Global, I owned the end-to-end digital learning journey for lending workflows — covering onboarding, origination, disbursement, delinquency, and closure. These PRDs capture the product requirements for eLearning simulation modules built to help bank employees understand how these workflows behave within the FIS MBP system.

---

## Lending Lifecycle Coverage

```
Onboarding → Origination → BRE Decision → Sanction → Disbursement
                                                            ↓
                                                    Repayment & EMI
                                                            ↓
                                              ┌─────────────────────┐
                                              │                     │
                                         Delinquency ✅         Closure ✅
                                         (30+ DPD)           (100% Repaid)
```

---

---

# PRD 1 — Term Loan Delinquency Awareness Module

---

## Section 1 — Product Overview

An eLearning simulation module designed to help bank employees across FIS MBP client organizations understand how term loan delinquency is represented, triggered, and reflected across borrower profiles, loan accounts, and system records within the FIS Modern Banking Platform.

---

## Section 2 — Problem Statement

As FIS MBP is a newly launched core banking platform, banking clients lack historical familiarity with how the system behaves when a loan account becomes delinquent. Without this awareness, the loan servicing team struggles to navigate the platform confidently during delinquency scenarios — leading to errors, delayed responses, dependencies on seniors, and an influx of support queries post go-live.

---

## Section 3 — Goals and Success Metrics

| Goal | Metric | Target |
|---|---|---|
| Bank employees understand delinquency workflow in FIS MBP | Module completion rate | 20% increase |
| Reduce support queries related to delinquency | L1 delinquency tickets | 20-30% reduction |
| Faster platform adoption for post-disbursement workflows | Go-live time for collections teams | Measurable reduction |

---

## Section 4 — User Personas

**Persona 1 — Collections Officer**
- Works at an FIS MBP client bank — eg: Fifth Third Bank, BMO, Amex, SMBC
- Responsible for monitoring and managing delinquent loan accounts
- New to FIS MBP — needs to understand how delinquency looks in the system

**Persona 2 — Loan Servicing Officer**
- Manages loan accounts post disbursement
- Needs to understand how account and borrower statuses change during delinquency
- Uses FIS MBP daily for loan servicing

---

## Section 5 — User Stories

**US001 — System Awareness**
As a Collections Officer, I want to understand how the system automatically flags a delinquent account so that I can quickly navigate to the right records when a borrower misses an EMI.

Acceptance Criteria:
- Module shows auto flag and alert generation triggered by missed EMI
- Module shows borrower profile status change to Delinquent
- Module shows loan account status change to Overdue
- Module shows affected records and screens at 30+ DPD

**US002 — Status Visibility**
As a Loan Servicing Officer, I want to see how borrower and account statuses change during delinquency so that I can accurately read and interpret system records.

Acceptance Criteria:
- Module covers all status changes triggered by delinquency
- Final scene shows summary view of all affected records

---

## Section 6 — Module Flow

```
Scene 1 — Pre-Delinquency State
Loan account viewed — Active status, EMI due date visible
        ↓
Scene 2 — Missed EMI Trigger
Borrower misses EMI — System auto flags account
Alert generated on dashboard
        ↓
Scene 3 — Status Changes
Borrower Profile Status → Delinquent
Loan Account Status → Overdue
Affected records updated — 30+ DPD bucket
        ↓
Scene 4 — Final Summary
Account status view
Borrower status view
All affected records shown
```

---

## Section 7 — Scope

**In Scope:**
- Term Loan delinquency scenario — 30+ DPD
- Auto flag and alert generation
- Borrower profile status change — Delinquent
- Loan account status change — Overdue
- Affected records and screen walkthrough
- Final summary scene

**Out of Scope:**
- Escalation flows — 60+ DPD, 90+ DPD
- Self-employed borrower delinquency
- NPA and recovery workflows
- Collections officer actions and workflows

---

## Section 8 — Delivery Format

eLearning simulation module — screen recording of live FIS MBP product with synchronized audio narration. Script developed collaboratively between Product Owner and Lending SME. Development executed by eLearning Dev team with script-audio synchronization. Delivered via FIS internal LMS in SCORM-compliant format.

---

## Section 9 — Dependencies

| Dependency | Owner |
|---|---|
| Script sign-off | Lending SME |
| Live product access for screen recording | FIS MBP Product Team |
| Audio recording and synchronization | eLearning Dev Team |
| LMS publishing | LMS Administrator |

---

## Section 10 — Timeline

| Activity | Stage |
|---|---|
| Script drafting and SME review | Sprint 1 — Week 1 |
| Screen recording on live product | Sprint 1 — Week 1 |
| Dev synchronization — script and audio | Sprint 1 — Week 2 |
| QA review and accuracy check | Sprint 1 — Week 2 |
| LMS publishing and release | Sprint 1 — Week 3 |

---

## Section 11 — Risks

| Risk | Mitigation |
|---|---|
| SME unavailability for script sign-off | Buffer time built into sprint planning |
| Product UI changes before recording | Align with product team on UI freeze |
| Audio-script sync errors | QA review before LMS publishing |

---
---

# PRD 2 — Term Loan Closure Awareness Module

---

## Section 1 — Product Overview

An eLearning simulation module designed to help bank employees across FIS MBP client organizations understand how a term loan closure is triggered, processed, and reflected across loan accounts, borrower profiles, and system records within the FIS Modern Banking Platform — upon 100% repayment of outstanding dues by the borrower.

---

## Section 2 — Problem Statement

As FIS MBP is a newly launched core banking platform, banking clients lack historical familiarity with how the system behaves when a term loan is fully repaid and closed. Without this awareness, loan servicing teams struggle to navigate post-closure system states — leading to confusion around account status, outstanding balances, and borrower profile updates — resulting in errors and increased support queries post go-live.

---

## Section 3 — Goals and Success Metrics

| Goal | Metric | Target |
|---|---|---|
| Bank employees understand closure workflow in FIS MBP | Module completion rate | 20% increase |
| Reduce support queries related to closure | L1 closure tickets | 20-30% reduction |
| Faster platform adoption for post-disbursement workflows | Go-live time for servicing teams | Measurable reduction |

---

## Section 4 — User Personas

**Persona 1 — Loan Servicing Officer**
- Works at an FIS MBP client bank — eg: Fifth Third Bank, BMO, Amex, SMBC
- Responsible for managing loan accounts post-disbursement through closure
- New to FIS MBP — needs to understand how closure looks and behaves in the system
- Needs to accurately interpret system states after full repayment

**Persona 2 — Branch Manager**
- Oversees loan servicing team at client bank
- Needs visibility into how closed accounts appear in the system
- Responsible for ensuring team handles post-closure queries accurately

---

## Section 5 — User Stories

**US001 — Closure Trigger Awareness**
As a Loan Servicing Officer, I want to understand how the system processes a full loan payoff so that I can accurately identify and navigate a closed loan account in FIS MBP.

Acceptance Criteria:
- Module shows loan account in Active status with outstanding amount before payoff
- Module demonstrates full payoff transaction being processed
- Module shows loan account status changing to Closed post payoff
- Module shows outstanding principal and interest updating to zero

**US002 — Record and Profile Update Awareness**
As a Loan Servicing Officer, I want to understand what changes across borrower profile and loan records after closure so that I can accurately read and interpret system records post closure.

Acceptance Criteria:
- Module shows borrower active loan count reducing post closure
- Module shows borrower relationship status updating
- Module shows repayment schedule marked as complete
- Module shows future EMIs cancelled
- Final scene shows closure date, zero outstanding, closed status

**US003 — Closure vs Settlement Awareness**
As a Loan Servicing Officer, I want to understand the difference between loan closure and loan settlement so that I can correctly identify and distinguish between the two system states.

Acceptance Criteria:
- Module clearly distinguishes closure — 100% dues paid — from settlement — partial amount accepted
- Module shows closure status indicators in the system

---

## Section 6 — Module Flow

```
Scene 1 — Pre-Closure State
Loan Status — Active
Outstanding Principal — X amount
Outstanding Interest — Y amount
Next EMI Due — Z date
        ↓
Scene 2 — Full Payoff Transaction
Full outstanding amount paid by borrower
System processes payoff transaction
        ↓
Scene 3 — System Status Changes
Loan Account Status → Closed
Outstanding Principal → 0
Outstanding Interest → 0
Repayment Schedule → Completed
Future EMIs → Cancelled
        ↓
Scene 4 — Final State Summary
Closure Date recorded
Zero outstanding confirmed
Closed status reflected across all records
Distinction shown — Closure vs Settlement
```

---

## Section 7 — Scope

**In Scope:**
- Term Loan closure scenario — 100% dues paid by borrower
- Pre-closure and post-closure status changes
- Full payoff transaction processing
- Loan account status change — Active to Closed
- Outstanding principal and interest update to zero
- Repayment schedule completion and future EMI cancellation
- Final state summary
- Distinction between closure and settlement

**Out of Scope:**
- Loan settlement — OTS/partial payment acceptance
- NOC generation — recommended for future sprint
- Collateral release for secured loans — recommended for future sprint
- Foreclosure/prepayment closure
- Collections-initiated closure
- Self-employed borrower specific closure flows

---

## Section 8 — Product Applicability

| Product | Type | Applicable |
|---|---|---|
| Personal Loan | Term Loan — Unsecured | ✅ Yes |
| Salaried Loan | Term Loan — Unsecured | ✅ Yes |
| Home Loan | Term Loan — Secured | ✅ Yes — collateral release out of scope |
| Loan Against Property | Term Loan — Secured | ✅ Yes — collateral release out of scope |
| Personal LOC | Line of Credit — Unsecured | ✅ Yes |

**Key Difference — Term Loan vs LOC Closure:**
- Term Loan — fixed outstanding amount fully repaid, account closed permanently
- LOC — credit limit utilization reduced to zero, revolving facility closed or suspended based on bank policy

---

## Section 9 — Delivery Format

eLearning simulation module — screen recording of live FIS MBP product using SME-provided dummy account with Active loan status, with synchronized audio narration. Script developed collaboratively between Product Owner and Lending SME. Full payoff transaction performed on live platform during recording. Development executed by eLearning Dev team with script-audio synchronization. Delivered via FIS internal LMS in SCORM-compliant format.

---

## Section 10 — Dependencies

| Dependency | Owner |
|---|---|
| Script sign-off and dummy account setup | Lending SME |
| SCORM module development and audio synchronization | eLearning Dev Team |
| Testing | QA |
| LMS publishing | LMS Administrator |

---

## Section 11 — Timeline

| Activity | Stage |
|---|---|
| Script drafting and SME review | Sprint 1 — Week 1 |
| Screen recording on live product | Sprint 1 — Week 1 |
| Dev synchronization — script and audio | Sprint 1 — Week 2 |
| QA review and accuracy check | Sprint 1 — Week 2 |
| LMS publishing and release | Sprint 1 — Week 3 |

---

## Section 12 — Risks

| Risk | Mitigation |
|---|---|
| SME unavailability for script sign-off | Buffer time built into sprint planning |
| Product UI changes before recording | Align with product team on UI freeze |
| Audio-script sync errors | QA review before LMS publishing |
| Confusion between closure and settlement | SME to validate distinction in script |

---

> *Client-specific and proprietary platform details have been generalized where necessary.*
