# Kosuke Kikuchi

Backend / Full-stack Engineer | Software Design, Data Integrity, Architecture

Nishinomiya, Hyogo, Japan · [GitHub](https://github.com/kousukekikuchi1984)

Last updated: November 20, 2026

## Summary

Full-stack engineer specializing in backend development and data integrity since 2014.
I design idempotent transactions, locking, retries, and recovery for accounting, point balances,
and revenue data, balancing correctness, performance, availability, security, and operating costs.

At YUZURIHA, I designed ingestion of 300,000 external records in approximately six minutes
against a one-hour SLA, prevented accounting misstatements before release, and identified
the causes of MySQL fsync bottlenecks, deadlocks, and growing memory usage.
I contributed design/code reviews for a team of about ten and led subprojects of three to four.

At NTT-ME, I am an IC responsible for post-transfer system improvement. I restored a serverless
DWH, completing implementation, infrastructure, and data validation in five working days,
and reconciled Terraform configuration. I contribute to team security delivery and build
Agent-assisted implementation and verification, including reproduction-based remediation
criteria and evidence-based approval. I work across frontend, data, infrastructure,
and operations as needed.

## Core Skills

- Data integrity: idempotency, state transitions, locking, retry and recovery design, auditability.
- Backend and platform architecture: availability, cost, operability, maintainability, technical requirements.
- Production troubleshooting: root-cause analysis across application code, databases, infrastructure, and workflows.
- Software Factory: specification-driven development, role-based Agents, code review,
  integration testing, isolated test lanes, dependency automation, evidence-based approval,
  blast-radius assessment, reachability-informed assessment, and human design judgment.
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
The system uses microservices.

#### Serverless DWH restoration

- Owned requirements, design, implementation, and validation after the transfer made the
  previous analytics platform unavailable. Manual CSV aggregation had taken one to two hours weekly.
- Built a serverless DWH with DynamoDB Export, S3, EventBridge, Step Functions, and Athena.
  Requirements/design and delivery took about one month; implementation, infrastructure,
  and data validation took five working days. Validated counts, missing records, duplicates,
  and processing time. Effects on recurring work, SLA reporting, and decisions remain unmeasured.

#### Platform and architecture improvement

- Corrected Terraform state/configuration drift, recurring resource recreation, missing
  definitions, and unstable references; verified clean plans without changes and successful applies.
- Identified insufficient OpenSearch capacity and prepared cost, rollout, and Terraform
  reconciliation options. Assessed routing, endpoints, DNS, IAM, and service impact for network changes.
- Clarified scope, constraints, and completion criteria for underspecified security and client
  PoC work. Delivered an early PoC UI change in about one week, using Cursor for exploration
  and implementation support. Pace changes around colleagues' capacity and project readiness.

#### Security and operational risk

- Contributed architecture and security/release decisions to team production delivery.
  Implemented image-input restrictions and minimal audit logging. Separately tested
  sample-event-to-handler and handler-to-blocking paths; full real-event E2E through
  notification and unblocking remains incomplete.
- Assessed an alternative-runtime draft against vulnerability prerequisites, execution paths,
  and deployment/maintenance costs. Closed the unmerged draft and retained the managed
  runtime for the assessed path; other vulnerabilities and routine patching remain subject to review.
- Enabled Dependabot Reachability and verified read-only data retrieval; assess unknown
  reachability against production dependencies and execution paths.

#### Software Factory and verification

- Implemented integration tests, an isolated release-test lane, and a workflow that tests
  dependency updates and uses Cursor to repair failures. Built an assisted-review environment;
  one measured PR review fell from about 60 to five minutes, with final judgment retained by me.
- Delegated remediation verification to AI Agents and defined completion criteria covering
  review-comment validity, pre-fix reproduction, post-fix checks with the same tests,
  regression tests, evidence, and residual-risk-based merge eligibility. Evidence coverage
  and production rollout remain separate checks for each change.
- Designed and implemented approval CI and revised criteria combining severity, blast radius,
  and verification results. Require module-scoped fixes, integration tests, and PR evidence;
  distinguish approval, GitHub merge status, and production release. Sustained operation
  and review/verification-time gains remain unconfirmed.
- Piloted role-based Agents. For one DWH, two to three independent generations converged
  on behavior verified by tests and runtime checks. Identified local overengineering,
  shared-context, dependency, and coordination issues. Browser E2E, local verification,
  and release-strategy changes remain at design/proposal stage.

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
