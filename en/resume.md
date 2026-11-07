# Kosuke Kikuchi

Full-stack / Platform Engineer | Backend, Infrastructure, Data Integrity

Nishinomiya, Hyogo, Japan · [GitHub](https://github.com/kousukekikuchi1984)

Last updated: November 7, 2026

## Summary

Full-stack / platform engineer focused on backend and infrastructure, working across
applications, data platforms, and operations since 2014.
I specialize in data integrity: idempotency, state transitions, retries, recovery, and
auditability for accounting outputs, point balances, and revenue records.

At NTT-ME, I work as an IC on the AI Property Resilience Business transferred from Tractable,
spanning requirements, architecture, data, infrastructure, security, and operations.
Recent work includes a serverless DWH, Terraform reconciliation, verification foundations,
Dependabot Reachability, and team delivery of production security monitoring.

I am building an evidence-based Software Factory. Approval CI awaits full operation;
runtime fallback is a draft with runtime validation pending; browser E2E is at design stage.
The full remediation workflow and Blue/Green remain proposals; operational gains are unvalidated.
I define specifications and acceptance criteria before delegating execution to Agents,
retain design responsibility, and address shared context, dependencies, and overengineering.

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

- Contributed to team vulnerability remediation and production rollout of security monitoring
  and posture visibility. Owned architecture, platform, security/release strategy, and technical
  decisions while sharing code fixes with other engineers. Detection and response effectiveness
  remain to be measured.
- Draft-implemented an alternative runtime and CI switch for delayed managed-runtime patches,
  retaining the managed default and limiting manual switching to dev. Limited tests were reported
  as passing; SAM execution, dev runtime checks, and function/layer size validation remain pending.
  Completion criteria are unmet; production migration has not been decided.
- Designed and implemented approval CI using finding severity, blast radius, and required
  integration/E2E evidence. Approval, merge, and production deployment are separate decisions.
  Full operation and review lead-time savings remain unvalidated.
- Defined security-fix completion as module-scoped changes passing integration tests with
  PR evidence. Began an environment inventory and decision skills for continuous remediation;
  end-to-end operation and throughput gains remain unvalidated.
- Enabled Dependabot Reachability and verified read-only data retrieval. Separated assessment
  from repair/testing; unknown reachability requires production dependency and path evidence.
  Sustained assessment quality remains unvalidated.
- Defined security-requirement criteria covering protection goals, threats, assurance,
  certificate renewal, automation, availability, and audits. Validation, adoption/policy
  agreement, and ADR documentation remain pending; technical and policy authority are distinct.
- Presented a release strategy separating technical verification from business acceptance.
  Presentation does not imply adoption approval. Blue/Green remains a proposal with shared-data,
  duplicate-event, compatibility, and rollback questions; release-frequency gains are unproven.
- Implemented integration tests, an isolated release-test lane, and Cursor access to logs/data.
  Defined browser/API/persistence E2E requirements; the README awaits approval and browser
  validation is pending. Existing unit/integration gates remain; time savings are unmeasured.
- Introduced dependency updates followed by tests and Cursor repair of failures, retaining
  human responsibility for system-wide consistency and design decisions.
- Restored a serverless DWH using DynamoDB Export, S3, EventBridge, Step Functions, and Athena.
  End-to-end requirements/design took about one month; implementation, infrastructure, and
  data validation took five working days. Validated counts, missing records, duplicates,
  and processing time; operating-effort, SLA-reporting, and decision-making effects remain open.
- Identified insufficient OpenSearch capacity; prepared cost, rollout, Terraform reconciliation,
  and risk information. Resolved recurring drift across S3, Lambda, Cognito, and EC2;
  verified clean plans without changes and successful applies.
- Built Cursor-assisted CI/CD review. One measured PR review fell from about 60 to five minutes;
  I retained checks of purpose, execution paths, permissions, data impact, and failure modes.
- Piloted implementation, investigation, security, SRE, QA, and review Agents. For one DWH,
  two to three independent generations converged on behavior verified by tests and runtime
  checks. Observed local overengineering and identified shared context and coordination needs.
- Delivered a PoC UI change in about one week; clarified underspecified AWS security and client
  PoC tasks; assessed routing, endpoints, DNS, IAM, and service impact for network changes.
  Pace changes around colleagues' capacity/readiness; version-based DynamoDB-to-OpenSearch
  DLQ conflict control remains a design proposal.

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
