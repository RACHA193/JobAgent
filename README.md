# JobAgent

### Local-First AI-Assisted Job Application Automation

JobAgent is a personal automation platform I built to reduce the repetitive work involved in searching for jobs, evaluating roles, tailoring resumes, preparing applications, and tracking application outcomes.

The project runs locally because it works with sensitive information such as resumes, application data, browser sessions, email confirmations, and candidate profile information.

> **Note:** This repository is intentionally documentation-only.  
> The production source code, credentials, personal data, application records, resumes, logs, and private configuration are not published.

---

## What JobAgent Does

JobAgent combines AI-assisted generation with deterministic validation and browser automation to support an end-to-end job application workflow.

The system can:

- evaluate and rank job opportunities
- analyze job descriptions and technical responsibilities
- generate role-specific resume content
- validate generated resume bullets before they are accepted
- map resume bullets back to specific job responsibilities
- prepare application packages
- automate browser-based application workflows
- answer known application questions from configured profile data
- detect uncertain application states before attempting duplicate submissions
- reconcile application confirmations and rejections through email
- maintain local application state, retries, cooldowns, and logs

---

## Architecture

```mermaid
flowchart LR
    A[Job Discovery] --> B[Evaluation & Ranking]
    B --> C[JD Analysis]
    C --> D[Resume Generation]
    D --> E[Deterministic Validation]
    E --> F[Source Grounding]
    F --> G[Application Preparation]
    G --> H[Browser Automation]
    H --> I[Confirmation Detection]
    I --> J[Email Reconciliation]
    J --> K[Local Application State]

    E -->|Validation Failed| D
    F -->|Grounding Failed| D
