**Layer 1 -- MBP Platform Ecosystem**
graph TD
    %% Styling and Definitions
    classDef ecosystem fill:#f4f5f7,stroke:#333,stroke-width:2px;
    classDef layer fill:#ffffff,stroke:#0052cc,stroke-width:2px,stroke-dasharray: 5 5;
    classDef core fill:#e6f0ff,stroke:#0052cc,stroke-width:2px;
    classDef nodeStyle fill:#fff,stroke:#666,stroke-width:1px;

    %% Main Container Box (Represented logically via hierarchy)
    subgraph BE [BANK'S ECOSYSTEM — Bank's Choice]
        
        %% Top Layer: Origination
        subgraph LOC [Lead / Origination Channel]
            channels[FIS Digital One • Salesforce FSC • nCino • Blend • Any Platform]
        end

        %% Middle Layer: API and Core
        subgraph API [FIS Code Connect — Open API Layer 1000+ APIs]
            
            %% Core Engine
            subgraph MBP [FIS Modern Banking Platform — Core Engine]
                direction TB
                foundational[Foundational • Customer • Account Engine<br>Compliance • Real-time Data • Operations]
                products[Term Loan • LOC • BNPL<br>Deposits • Collections]
            end
            
            %% External Dependencies connected to Core
            subgraph Left_Integrations [Risk & Credit Verification]
                direction TB
                cb[Credit Bureau:<br>FICO • Experian • Equifax]
                fr[Fraud & Risk:<br>LexisNexis]
            end

            subgraph Right_Integrations [Communications & Compliance]
                direction TB
                cc[Customer Comms:<br>TouchCX • Alerts • Notices]
                comp[Compliance:<br>FATCA • AML • KYC]
            end

        end

        %% Bottom Layer: Payments
        subgraph PR [Payment Rails]
            payments[ACH • FedNow • FedWire • RTP • Any Payment Hub]
        end

    end

    %% Flow Connections
    channels --> API
    
    %% Internal API Core Connections
    MBP <--> Left_Integrations
    MBP --> Right_Integrations
    
    %% Core to Payments
    API --> payments

    %% Apply Styles
    class BE ecosystem;
    class API layer;
    class MBP core;
    class channels,payments,cb,fr,cc,comp,foundational,products nodeStyle;


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
