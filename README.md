# Senior Mortgage Underwriting System

**Multi-agent mortgage underwriting that reduces processing time from days to hours while maintaining regulatory compliance**

Traditional mortgage underwriting takes 3–5 days per application and costs lenders $70–100K annually per underwriter. Different underwriters reach inconsistent conclusions on identical applications, creating compliance risk. This system replaces that manual, error-prone process with a coordinated team of specialised AI agents operating under strict governance controls.

---

## Business Outcome

- Reduces underwriting time from 3–5 days to hours
- Eliminates subjective inconsistency through deterministic calculation tools
- Maintains full regulatory compliance — Fair Lending Act, PII protection, audit trails
- Flags high-risk cases for mandatory human review rather than autonomous approval

---

## How It Works

Four specialist agents evaluate different dimensions of an application simultaneously, coordinated by a Supervisor. A Critic Agent reviews for inconsistencies before a Decision Agent produces the final recommendation.

### Agent Roles

| Agent | Responsibility |
|---|---|
| Credit Analyst | Reviews credit history, scores, derogatory marks |
| Income Analyst | Verifies employment, calculates debt-to-income ratio |
| Asset Analyst | Confirms funds adequacy for down payment and reserves |
| Collateral Analyst | Assesses property value and loan-to-value ratio |
| Supervisor Agent | Routes workflow, coordinates specialist agents |
| Critic Agent | Reviews all analyses for inconsistencies |
| Decision Agent | Synthesises findings, calculates risk score (0–100), produces recommendation |

### Workflow

```
Application Input
    │
    ▼
Supervisor Agent
    ├──► Credit Analyst
    ├──► Income Analyst
    ├──► Asset Analyst
    └──► Collateral Analyst
    │
    ▼
Critic Agent (consistency review)
    │
    ▼
Decision Agent (risk score + recommendation)
    │
    ├── Risk score ≤ 30, DTI ≤ 43%, LTV ≤ 90% ──► Automated recommendation
    └── Any threshold exceeded ──► Human-in-the-loop escalation
```

---

## Governance & Compliance Features

- **PII sanitisation** — sensitive data redacted before LLM processing
- **Bias detection** — automated flagging of Fair Lending Act violations
- **Deterministic calculations** — Python tool decorators prevent LLM arithmetic errors
- **Human-in-the-loop** — mandatory escalation when risk score > 30, DTI > 43%, or LTV > 90%
- **Full audit trail** — every agent decision logged with reasoning

---

## Technologies

| Component | Technology |
|---|---|
| Agent Orchestration | LangGraph (state machine) |
| LLM Framework | LangChain |
| Policy Retrieval | RAG, ChromaDB |
| Calculation Layer | Python tool decorators (deterministic) |
| LLM | OpenAI GPT-4o |

---

## Part of

[Agentic AI Architecture — Johns Hopkins University](https://github.com/kayvonsalari)
