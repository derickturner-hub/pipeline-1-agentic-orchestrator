# Enterprise RevOps Agentic Execution Engine
![Schema Validation](https://github.com/derickturner-hub/enterprise-revops-agentic-pipeline/actions/workflows/validate-schemas.yml/badge.svg)

> Decoupled, schema-governed RevOps content production pipeline built on n8n, node-level JSON Schema validation, and multi-channel fulfillment staging.

---

## Executive Summary: Operational Paradigm Shift

| Operational Dimension | Manual Approval Workflows (Legacy) | Sovereign Agentic Pipeline (Engine) |
| :--- | :--- | :--- |
| **Execution Model** | Step-by-step human prompts & approval gating | Event-driven, fully autonomous execution |
| **Data Integrity** | Hallucination-prone, unvalidated text blobs | Hardened JSON Schema (Draft 2020-12) validation |
| **Domain Control** | Vertical lock-in across single-tenant setups | Universal vertical support via dynamic prompts |
| **Delivery Model** | Manual copy-pasting between platforms | Direct REST API integration to multi-channel staging |

Most operational RevOps teams rely on fragile "chat-based" setups—forcing team members to sit and manually "babysit" execution runs, re-prompting LLMs for missing fields, and manually formatting data across project management tools.

**`enterprise-revops-agentic-pipeline`** replaces manual oversight with an event-driven engine. Raw inbound triggers are processed, normalized, enforced against structural data contracts, and delivered directly as QA tasks with zero manual intervention required.

---

## Architecture & Data Flow

### Pipeline Execution Flow
```mermaid
graph TD
    %% Nodes
    A[Trigger: Webhook / Event] -->|Raw Keyword / Brief Input| B[Agent 1: 01_keyword_intent]
    B -->|Unstructured LLM Response| C[Parser 1: Parse Keyword JSON]
    C -->|Validated Keyword Schema| D[Agent 2: 02_content_intelligence]
    D -->|Unstructured LLM Content| E[Parser 2: Parse Content JSON]
    E -->|Validated Content Schema| F[Integration: Multi-Channel Router]
    F -->|REST / API Token Auth| G[Staging Adapters: ClickUp / Jira / Webflow]

    %% Data Governance & Guardrails
    subgraph Data Governance & Guardrails
        C
        E
    end

    subgraph LLM Intelligence Nodes
        B
        D
    end

    %% Styling
    style B fill:#3b82f6,stroke:#1d4ed8,color:#fff
    style D fill:#3b82f6,stroke:#1d4ed8,color:#fff
    style C fill:#10b981,stroke:#047857,color:#fff
    style E fill:#10b981,stroke:#047857,color:#fff
    style F fill:#8b5cf6,stroke:#6d28d9,color:#fff

