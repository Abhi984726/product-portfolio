**Layer 1 -- MBP Platform Ecosystem**
<img width="930" height="647" alt="image" src="https://github.com/user-attachments/assets/c6bff5a7-92e5-42f1-b98e-3769c65af570" />


Note: All surrounding platforms are the bank's choice. MBP is the core engine — banks connect their preferred systems via FIS Code Connect open APIs or any third-party API integration.

**Term Loan -- Salaried Borrower Journey Inside MBP**
Lead / application received
(Passed into MBP from channel of bank's choice)
        ↓
Borrower onboarding
KYC · FATCA check · borrower profile creation
        ↓
Loan application
Loan amount · tenure · purpose submitted
        ↓
BRE credit decision
FICO score · FOIR check · employment vintage
Bureau data pulled via external API integration
        ↓
┌───────────────────────────────────────┐
│  Auto approve  │  Manual review  │  Reject  │
└───────────────────────────────────────┘
        ↓ (approve / review)
Sanction
Sanction letter generated · terms confirmed
        ↓
Disbursement
ACH · FedNow · FedWire — via payment rail integration
        ↓
Post disbursement
EMI collection via ACH (recurring)
        ↓
┌─────────────────────────────────┐
│  Delinquency      │  Closure    │
│  30+ DPD ✅ PRD  │  100% paid  │
│                   │  ✅ PRD     │
└─────────────────────────────────┘
Note: Similar we can have similar flow for Line of Credit and BNPPL.

**Key domain terms:**
BRE — Business Rule Engine — automated credit decisioning
FICO — US credit score (equivalent of CIBIL in India) — pulled from Experian, Equifax, or TransUnion
FOIR — Fixed Obligation to Income Ratio — EMI vs income check
FATCA — Foreign Account Tax Compliance Act — US regulatory compliance
ACH — Automated Clearing House — standard payment rail for EMI collection and disbursement
FedNow — Federal Reserve instant payment rail — real-time disbursement
FedWire — Federal Reserve large-value payment rail — high-value transfers
DPD — Days Past Due — delinquency classification
