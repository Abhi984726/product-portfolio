**Layer 1 -- MBP Platform Ecosystem**
┌─────────────────────────────────────────────────────────────────────┐
│                   BANK'S ECOSYSTEM — Bank's choice                  │
│                                                                     │
│  Lead / Origination Channel                                         │
│  FIS Digital One · Salesforce FSC · nCino · Blend · any platform   │
│                              ↓                                      │
│  ┌ ─ ─ ─ ─ ─ FIS Code Connect — Open API Layer (1000+ APIs) ─ ─ ─┐ │
│  │                                                                │ │
│  │          ┌─────────────────────────────────┐                  │ │
│  │          │   FIS Modern Banking Platform   │                  │ │
│  │          │         Core Engine             │                  │ │
│  │          │                                 │                  │ │
│  │  Credit  │  Foundational · Customer        │  Customer        │ │
│  │  Bureau ←│  Account Engine · Compliance    │→ Comms           │ │
│  │  FICO    │  Real-time Data · Operations    │  TouchCX         │ │
│  │  Experian│                                 │  Alerts          │ │
│  │  Equifax │  Term Loan · LOC · BNPL         │  Notices         │ │
│  │          │  Deposits · Collections         │                  │ │
│  │  Fraud & │                                 │  Compliance      │ │
│  │  Risk   ←│                                 │→ FATCA · AML     │ │
│  │  LexisN. │                                 │  KYC             │ │
│  │          └─────────────────────────────────┘                  │ │
│  └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─┘ │
│                              ↓                                      │
│  Payment Rails                                                      │
│  ACH · FedNow · FedWire · RTP · any payment hub                    │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘

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
