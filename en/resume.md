# Résumé — Kosuke Kikuchi (菊地 弘祐)

## Basic Information

| Item | Details |
| --- | --- |
| Name | Kosuke Kikuchi |
| Date of Birth | March 1984 |
| Location | Nishinomiya, Hyogo, Japan |
| Education | Waseda University, Graduate School of Creative Science & Engineering (Architecture) — PhD Program (Completed coursework, withdrew before dissertation) |

---

## Professional Summary

I am a backend engineer specializing in mission-critical domains, designing systems where **incorrect data must never be finalized as truth**. My primary focus has been accounting data and point/balance systems—domains where once data is confirmed, rollback or correction becomes extremely costly. I take responsibility not only for implementation but also for **design-stage judgment**, prioritizing long-term data integrity, reproducibility, and explainability over short-term performance gains.

---

## Strengths & Technical Focus

### Data Integrity Design for Mission-Critical Systems
- Designed and implemented systems for accounting data and point balances, where errors are difficult to correct once finalized
- Built “non-breakable” designs incorporating idempotency, state transitions, boundary conditions, and safe re-execution strategies
- Designed data models and processing structures that enable correctness to be **reproduced, audited, and explained after the fact**

### Backend Architecture for Long-Term Operation
- Maintainable and reusable architecture (domain modeling, clean architecture concepts)
- Engineering judgment on when **not** to optimize for performance in favor of safety (including stopping unsafe initiatives)
- Incremental migration from legacy systems to modern architectures

### Data Platforms & Batch Processing Operations
- Designed and operated batch processing, aggregation, and validation workflows (including monitoring and recovery)
- Optimized operational load by designing workflows with retries, notifications, and finalization rules

### Cross-Functional Implementation Experience
- Backend-focused development with hands-on experience in TypeScript + Vue.js
- Coordinated frontend and backend changes for UX and performance improvements

---

## Experience

### Engineer — YUZURIHA
**Jan 2021 – Present**

#### Role Overview
Responsible for designing and judging system structures in which incorrect data must not be confirmed as valid, particularly in mission-critical domains. Also contributed to technical decision-making and review standards.

#### Selected Contributions

##### Accounting CSV defects discovered during product launch phase
**Challenge**  
Identified a latent defect in CSV exports used for monthly accounting, external accounting system integration, and multi-department reporting. If released, the issue would have required costly re-posting and correction of finalized accounting data.

**Actions**  
- Cross-validated specifications and implementation, identifying incorrect accounting behavior when points expired
- Determined the root cause was a design mismatch with correct accounting rules
- Corrected the design to align with accounting principles rather than applying a temporary fix

**Outcome**  
- Prevented incorrect accounting data from being finalized across multiple consumers
- Eliminated a state where “the system is technically correct but accounting is broken” before release

##### Large-scale data integration with a credit card company (1M records / hour constraint)
**Challenge**  
Required to safely ingest 1,000,000 records within one hour. Incorrect or duplicate ingestion would finalize incorrect user data and point balances, making recovery difficult. External specifications contained many exceptions and lacked a consistent application unit.

**Actions**  
- Reconstructed ingestion rules from inconsistent external specifications and redefined them from first principles
- Identified the safe parallelization unit by mapping card-level records to user-level identifiers (member/user ID), then designed ingestion units, lock granularity, and correction logic
- Classified and aligned exception cases with the external partner to establish an operable rule set
- Separated validation from insertion to balance throughput and safety
- Ensured idempotency so retries would not corrupt data
- Designed safe handling for account merges occurring mid-ingestion

**Outcome**  
- Achieved safe ingestion in approximately **6 minutes (measured)**
- Established an architecture that remains explainable during retries, failures, and operational incidents

##### Architectural judgment against unsafe performance optimization
**Challenge**  
A performance improvement initiative proceeded without sufficient investigation. Continuing optimization within the existing structure risked permanently corrupting point balances and duplicating recovery logic, making root cause analysis difficult.

**Actions**  
- Identified that the bottleneck was not application logic but MySQL commit fsync latency
- Determined proposed primitive-level optimizations would be ineffective in Python and increase long-term risk
- Proposed safer alternatives (commit reduction, responsibility separation) and returned the task to PM with findings

**Outcome**  
- Avoided a high-risk architectural fork
- Achieved organizational alignment on prioritizing data integrity over superficial speed gains

#### Review & Mentoring
- Increased team communication by intentionally creating additional dialogue opportunities
- In code reviews, documented the reasoning behind decisions, not just fixes
- Focused review attention on failure boundaries such as deployments and asynchronous processing
- Maintained psychological safety by avoiding emotional blame or reprimands
- In 1-on-1 sessions, provided targeted guidance focused on the single highest-impact improvement
- Supported foundational skills such as writing clarity and documentation quality

#### Other Projects
- Point system modernization and operation for a major sporting goods retailer
- Recruitment website development for a major sporting goods retailer
- Backend support for native mobile app integration of the point system

---

### Data Reliability Engineer — Gunosy
**May 2019 – Dec 2020**

#### Role Overview
Ensured correctness, reproducibility, and explainability of data across applications, migrations, aggregations, and business operations within a large-scale data platform.

#### Selected Contributions

##### SSP revenue data ingestion and finalization workflow
**Work**  
- Built pipelines to ingest SSP revenue data and make it analyzable via AWS Athena
- Implemented strict finalization rules (preliminary fixed after 60 hours, final fixed after 72 hours, immutable thereafter)
- Diagnosed unexpected Digdag workflow behavior by inspecting source code rather than treating it as a black box

**Impact**  
- Balanced business requirements with strict data integrity
- Established reproducible handling of unexpected workflow behavior
- Identified errors in business-side revenue allocation ratios before finalization  
  - Reference: https://tech.gunosy.io/entry/escape-from-pitfall

##### Workflow templates for data platform democratization
**Work**  
- Designed bash-based templates enabling safe workflow usage across teams
- Defined clear responsibility boundaries between platform and user teams

**Impact**  
- Reduced workflow creation and operational costs
- Lowered support burden for both platform and consuming teams

##### Operational load reduction via workflow redesign
**Work**  
- Classified workflows that naturally converge to correctness over time
- Redesigned workflows so correctness is guaranteed in the next execution cycle

**Impact**  
- Reduced operational noise while preserving data integrity
- Shifted incident handling from human judgment to structural guarantees

#### Other Projects
- Online machine learning platform foundation
- Patent data preprocessing and search infrastructure
- Data mart creation and maintenance

---

### Systems Engineer — PERSOL CAREER
**Oct 2017 – Apr 2019**

#### Overview
- Worked on large-scale recruiting web services and data platform-related projects
- Focused on stable backend development and system maintenance
- Experienced how insufficient validation in batch/data pipelines leads to high downstream correction costs
- Developed strong emphasis on design-stage judgment and explainability

#### Projects
- On-premises Hadoop platform for machine learning systems
- Documentation for machine learning project execution
- Maintenance and review of existing ML engines
- Introductory statistics study sessions for business stakeholders

---

### Data Mining Engineer — IPONWEB Japan
**Feb 2016 – Sep 2017**

#### Overview
- Analyzed advertising delivery and revenue data
- Identified inconsistencies and anomalies from logs and aggregates
- Handled cases where systems appeared normal but data was incorrect
- Developed instincts for detecting distribution-level anomalies early

#### Projects
- Campaign budget optimization using multi-armed bandit methods
- Introduction of Private Auctions for overseas SSPs
- Incident improvement for in-feed advertising delivery
- Performance consulting for specific agencies

---

### Engineer — Spotlight
**Apr 2014 – Jan 2016**

#### Overview
- Worked primarily on “Rakuten Check,” an O2O customer acquisition service
- Improved report generation and display performance, enhancing UX and operational efficiency
- Built a problem-driven, technology-agnostic engineering mindset

#### Projects
- Internal reporting system development
- Test user feature implementation
- New feature development for large convenience store chain deployment
- Service performance improvements

---

## Certifications
- IELTS Academic 6.5 (Oct 2010)

---

## Awards & Programs
- Waseda University EDGE Global Entrepreneurship Program (Dec 2016)
- The Fab Academy Certificate (Aug 2013)
- Waseda University Tsuruta Scholarship (Feb 2012)
- Architectural Institute of Japan (Kanto Branch) Young Researcher Award (Mar 2012)
- Waseda University Doctoral Practical Studies Program (Sep 2011)

---

## Publications
- Urban analysis using location-based social networks (2010–2013)
- *Collective Background Extraction for Station Market Area by using Location Based Social Network*, Journal of Civil Engineering and Architecture, 2013
- *Smart Life*, Parade Publishing, 2011
- Additional publications available upon request

---

## Technical Writing
- Cache locality and performance trade-offs  
  https://qiita.com/kikuchi-yzrh/items/56b2368e4473e19ec1d9
- SQLAlchemy IdentityMap boundary conditions  
  https://qiita.com/kikuchi-yzrh/items/9680fd85f0dcb474ef18
- MySQL full-text search (n-gram) commit pitfalls  
  https://qiita.com/kikuchi-yzrh/items/baaab16cc1258e81e476
- Digdag retry pitfalls and idempotent recovery design  
  https://tech.gunosy.io/entry/escape-from-pitfall

---

## Selected Works

### Plant Pod (Mar 2013)
Explores indirect communication between humans and plants via environmental sensing and expressive visualization.  
https://www.youtube.com/watch?v=IEh0-y3y_0s

### Live Camera (Aug 2010)
A privacy-preserving system that visualizes lab occupancy states through clustered color data, increasing collaboration.  
https://www.youtube.com/watch?v=WbKnb9Cbi8s

### Environmental Sensing (Mar 2010)
Low-cost sensor modules synchronized with servers and reflected in 3D CAD models to visualize residential conditions.  
https://www.youtube.com/watch?v=4_mtrW7d3nc
---

[![Generated with ChatGPT](https://img.shields.io/badge/Generated%20with-ChatGPT-14A06F?style=flat-square&logo=openai&logoColor=white)](https://openai.com)
---

Last updated: 2026-01-05
