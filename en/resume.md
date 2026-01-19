# Kosuke Kikuchi
Nishinomiya, Hyogo, Japan  
Backend / Data Reliability Engineer  
GitHub: https://github.com/kousukekikuchi1984

## Summary
Backend engineer specializing in **mission-critical data integrity**. I design systems where incorrect data must not become “confirmed truth,” such as **accounting outputs and point-balance ledgers**. I prioritize **correctness, reproducibility, and explainability** under operational constraints (retries, partial failure, asynchronous boundaries), and I am known for making pragmatic engineering decisions—including when to **stop unsafe optimizations**.

## Core Strengths
- **Data integrity design:** idempotency, state transitions, failure modes, re-execution strategy, auditability
- **Production troubleshooting:** root-cause analysis (DB deadlocks, memory leaks), prevention by structural fixes
- **Backend architecture:** long-term maintainability, clear boundaries of responsibility, operationally sound workflows
- **Cross-functional delivery:** align stakeholders by clarifying constraints, risks, and alternatives (servant-style leadership)

## Technical Skills
- **Backend:** Python (primary), Rust / Go / Java (limited)
- **Frontend:** TypeScript (production), Flutter (limited)
- **Databases/Data:** MySQL (primary), DuckDB, AWS Athena
- **Cloud/Infra:** AWS (ECS, EKS, Lambda, CloudFront, CloudWatch, EventBridge, Step Functions)
- **Data tools:** Digdag (code-level analysis), Embulk (code-level analysis)
- **Other:** HULFT (file transfer integration), Linux (conceptual familiarity)

## Experience

### YUZURIHA — Engineer (Backend / Platform)
Jan 2021 – Present

**Scope:** Technical direction for a ~10-engineer product team; design/code reviews as a quality gate; sub-project leadership (3–4 people); first-round engineering interviews.

**Selected accomplishments**
- **Prevented accounting CSV misstatement before launch** by identifying a latent edge case and correcting the design to match accounting rules (avoided costly post-release reconciliation).
- **Built safe large-scale ingestion for credit-card data (1M records, 1-hour SLA)** by redefining inconsistent external rules, deriving a safe parallelization unit (user-level key), separating validation from apply, and enforcing idempotent re-execution; achieved ~6 minutes ingestion in practice.
- **Led high-risk cutover of file-transfer integration (HULFT / OS / crypto changes)** across 4 stakeholders; re-evaluated trade-offs when new constraints emerged and executed a one-shot cutover with rollback/monitoring plans—completed without critical incidents.
- **Stopped unsafe “performance optimization”** by proving the bottleneck was MySQL commit fsync (not app CPU), proposing alternatives (commit reduction, responsibility split), and preventing a design fork that risked data integrity.
- **Resolved production incidents structurally:** fixed a post-release **memory leak** caused by persistent caching of DB Engine objects; eliminated recurring **DB deadlocks** by standardizing lock acquisition order and codifying the rule.

### Gunosy — Data Reliability Engineer
May 2019 – Dec 2020  
Ensured correctness and explainability across large-scale data workflows spanning ingestion, aggregation, and business operations.  
- Designed revenue data finalization workflows with strict “freeze” semantics and resolved non-obvious Digdag behavior via code-level analysis.  
- Built workflow templates to democratize the platform and reduced operational noise by designing convergence-by-structure.  
Reference: https://tech.gunosy.io/entry/escape-from-pitfall

### PERSOL CAREER — Systems Engineer
Oct 2017 – Apr 2019  
Selected: on-prem Hadoop for ML systems; docs for ML project execution; engine maintenance & review.

### IP ONWEB JAPAN — Data Mining Engineer
Feb 2016 – Sep 2017  
Analytics/ops for advertising delivery and revenue data; anomaly detection from distribution shifts; root-cause analysis of “looks normal but wrong” data states.

### Spotlight — Engineer
Apr 2014 – Jan 2016  
O2O product development; improved report generation performance and operational efficiency.

## Technical Writing & Contributions
- HTTP/3 (QUIC) partial Japanese translation: https://http3-explained.haxx.se/ja
- Cache locality and performance reasoning (Qiita): https://qiita.com/kikuchi-yzrh/items/56b2368e4473e19ec1d9
- SQLAlchemy IdentityMap deep-dive (Qiita): https://qiita.com/kikuchi-yzrh/items/9680fd85f0dcb474ef18
- MySQL full-text search edge case note (Qiita): https://qiita.com/kikuchi-yzrh/items/baaab16cc1258e81e476
- Digdag retry duplication pitfall (Gunosy Tech Blog): https://tech.gunosy.io/entry/escape-from-pitfall
