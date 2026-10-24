# Kosuke Kikuchi

Platform / Backend Engineer | Architecture, Data Integrity, Software Factory

Nishinomiya, Hyogo, Japan · [GitHub](https://github.com/kousukekikuchi1984)

Last updated: October 24, 2026

## Summary

Software engineer working across backend systems, data platforms, and infrastructure since 2014.
I specialize in data integrity for systems where incorrect accounting outputs, point balances,
or revenue records are costly to correct. My work covers idempotency, state transitions,
safe retries, recovery, and auditability.

At NTT-ME, I work as an individual contributor on the AI Property Resilience Business
transferred from Tractable. I handle system discovery and platform improvement across
requirements, architecture, data, infrastructure, security, and operations. Recent work includes
a serverless DWH, reliable Terraform configuration management, role-based AI Agents,
integration tests, an isolated release-test lane, and automated dependency updates and repairs.
I am building a Software Factory incrementally so engineers can focus on system-wide
consistency and design decisions.
Recent work also includes an implemented approval CI awaiting full operation,
security-remediation quality gates, and initial design of a continuous remediation workflow.

I define specifications and acceptance criteria before delegating execution to AI Agents,
and retain responsibility for design decisions and evaluating the results. I observed
overengineering from Agents optimizing their own tasks and identified shared context,
dependencies, and coordination as design concerns. I pace platform changes around
team capacity and operational needs.

## Core Skills

- Data integrity: idempotency, state transitions, locking, retry and recovery design, auditability.
- Backend and platform architecture: availability, cost, operability, maintainability, technical requirements.
- Production troubleshooting: root-cause analysis across application code, databases, infrastructure, and workflows.
- Software Factory: specification-driven development, role-based Agents, code review,
  integration testing, isolated test lanes, dependency automation, evidence-based approval,
  blast-radius assessment, and human design judgment.
- Technologies: Python; TypeScript / Vue.js; MySQL, DynamoDB, OpenSearch, DuckDB, Athena;
  AWS ECS, EKS, Lambda, S3, CloudFront, CloudWatch, EventBridge, Step Functions; Terraform;
  Digdag, Embulk, Linux, HULFT, Cursor, Dependabot.
- Limited experience: Rust, Go, Java, Flutter.

## Experience

### NTT-ME Corporation / Software Engineer

June 2026–Present

Social Infrastructure Design Department, AI Property Resilience Business.
Individual contributor responsible for platform engineering and technical problem solving,
working with the PdM and TL/PM during the post-transfer operation and improvement of the service.

- Designed and implemented CI that routes changes to automatic approval or human review
  using finding severity, blast radius, and required integration-test / E2E evidence.
  Automatic approval, merge, and production deployment remain separate decisions.
  The CI is awaiting full operation; review lead-time savings have not been demonstrated.
- Defined security-fix completion as a module-scoped change passing integration tests
  with evidence attached to the PR. Began an execution-environment inventory and decision skills
  for a Security Remediation Factory spanning impact assessment, repair, verification,
  approval, and release. End-to-end operation and throughput gains remain unvalidated.
- Implemented integration tests so Coding Agents can verify their implementations.
  Built a release-test lane that separates verification from regular processing,
  and established access to logs and relevant data for Cursor-assisted investigation.
  Broader adoption and verification-time savings remain to be validated.
- Introduced a dependency-update workflow: Dependabot updates libraries, tests run,
  and Cursor repairs failing changes. Expanded delegation of repetitive work while
  retaining human responsibility for system-wide consistency and design decisions.
- Restored a serverless DWH using DynamoDB Export, S3, EventBridge, Step Functions, and Athena.
  Requirements and design took the end-to-end effort to approximately one month;
  implementation, infrastructure, and data validation took five working days.
  Validated counts, missing records, duplicates, and processing time.
  Construction and data validation are complete; effects on operating effort,
  SLA reporting, and decision-making remain to be assessed in actual use.
- Identified insufficient OpenSearch instance capacity and prepared cost, rollout,
  Terraform state reconciliation, and risk information for a remediation decision.
  Resolved recurring Terraform drift and plan differences across S3, Lambda, Cognito,
  and EC2; verified clean plans when no change exists and successful applies.
- Built a Cursor-based CI/CD review environment. In one measured case, PR review time
  fell from approximately 60 minutes to five minutes while I retained verification of
  purpose, execution paths, permissions, data impact, and failure modes.
- Piloted implementation, investigation, security, SRE, QA, and review Agents.
  For one DWH project, two to three independent generations from the same specification
  converged on behavior verified by tests and runtime checks; this reproducibility result
  is limited to that one project. Observed overengineering from local Agent optimization
  and identified shared context, dependencies, coordination, and human review as design concerns.
- Delivered a PoC UI change in approximately one week. Clarified underspecified AWS
  security tasks and client PoC requirements before implementation, and assessed
  routing, endpoints, DNS, IAM conditions, and service impact for AWS network changes.
- Adjust platform-improvement scope and timing around colleagues' workload and project readiness.
  Version-based conflict control for DynamoDB-to-OpenSearch DLQ replay remains a design proposal.

### YUZURIHA / Engineer, Backend and Platform

January 2021–May 2026

Worked on a point platform serving approximately seven million members.
Contributed technical direction and design/code reviews for a team of approximately ten
engineers, led subprojects of three to four people, and conducted first-round technical interviews.

- Designed safe ingestion of 300,000 external credit-card records under a one-hour SLA.
  Redefined exception-prone external rules, used user-level locking, separated validation
  from ingestion, and implemented idempotent retries and account-merge handling.
  Ingestion took approximately six minutes in practice. Blocked ten partner-originated
  failures, including three incorrect-data deliveries, with zero irreversible mispostings.
- Prevented accounting CSV misstatements before launch by identifying a mismatch between
  point-expiry accounting rules and the implementation, then correcting the design.
- Led a HULFT file-transfer cutover covering OS, application, and encryption changes.
  Reassessed cost, risk, and recoverability when external constraints changed, and completed
  a single cutover with backup, recovery, and monitoring plans, without critical incidents.
- Stopped an unsafe local optimization of point-balance processing. Identified MySQL
  commit-time fsync as the bottleneck and proposed fewer commits and clearer responsibilities
  while preserving data integrity.
- Resolved a production memory leak caused by persistent caching of DB Engine objects.
  Eliminated the identified deadlocks by standardizing lock acquisition order.
- Explained assumptions, risks, and alternatives in reviews; supported technical development,
  one-on-one feedback, and documentation skills. Other work included point-system renewal,
  native-app backend support, and recruitment-site development.

### Gunosy / Data Reliability Engineer

May 2019–December 2020

- Designed SSP revenue workflows with preliminary finalization at 60 hours and final
  freeze at 72 hours; prepared data for Athena and investigated Digdag behavior at code level.
- Created reusable workflow templates with explicit platform/user responsibilities.
  Reduced operational noise by separating errors that converge on the next run from
  conditions requiring intervention.
- Other projects: online ML infrastructure, patent-data preprocessing and search,
  and data-mart development and maintenance.

### PERSOL CAREER / Systems Engineer

October 2017–April 2019

- Maintained backend services and data platforms; built on-premises Hadoop infrastructure
  for ML systems, documented ML project practices, maintained ML engines, and taught
  introductory statistics to business teams.

### IP ONWEB JAPAN / Data Mining Engineer

February 2016–September 2017

- Analyzed advertising delivery and revenue data, investigated anomalies,
  and worked on multi-armed-bandit campaign-budget optimization, private auctions,
  in-feed delivery improvements, and performance consulting.

### Spotlight / Engineer

April 2014–January 2016

- Developed Rakuten Check, an O2O service, including internal reporting, test-user features,
  and functionality for a major convenience-store rollout. Improved reporting performance.

## Education and Training

- Waseda University, Graduate School of Creative Science and Engineering, Architecture:
  completed doctoral coursework; withdrew without receiving a PhD.
- IELTS Academic: 6.5, November 2012.
- Waseda EDGE Global Entrepreneurship Program, completed December 2016.
- Fab Academy Certificate, August 2013.
- Machine Learning, Coursera / Stanford University, February 2022;
  Deep Learning, Coursera / Deeplearning.ai, March 2022.
- Architectural Institute of Japan, Kanto Branch, Young Researcher Presentation Award,
  March 2013; Waseda Tsuruta Scholarship, February 2013.

## Selected Writing and Contributions

- [From a Bug Fix to a Software Factory](https://zenn.dev/kou2kkkt/articles/10b13eef3b0046)
  (Japanese): specialized Agents, independent review, E2E testing, and human attention in a three-day experiment.
- [Preserving How We Build, Beyond the Code](https://zenn.dev/kou2kkkt/articles/d52dca7e2a1872)
  (Japanese): execution, verification, and organizational learning as distinct processes.
- [Designing the Rules, Choosing the Results](https://zenn.dev/kou2kkkt/articles/fc92cd9d6599fb)
  (Japanese): generative design and evaluation through Xenakis's music, architecture, and mathematics.
- [HTTP/3 explained](https://http3-explained.haxx.se/ja): partial Japanese translation.
- [Cache locality](https://qiita.com/kikuchi-yzrh/items/56b2368e4473e19ec1d9),
  [SQLAlchemy IdentityMap](https://qiita.com/kikuchi-yzrh/items/9680fd85f0dcb474ef18),
  [MySQL full-text search](https://qiita.com/kikuchi-yzrh/items/baaab16cc1258e81e476),
  and [Digdag retry behavior](https://tech.gunosy.io/entry/escape-from-pitfall).
