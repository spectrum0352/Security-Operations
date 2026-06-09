**Vulnerability Metrics Framework**

**Document Type:** Metrics & Reporting Standard\
**Domain:** Vulnerability Management / Cyber Risk\
**Version:** 1.0\
**Owner:** CISO Office / Security Metrics & Analytics Team\
**Effective Date:** \[Insert Date\]

**1. Purpose**

This document defines the enterprise standard for measuring, tracking,
and reporting **vulnerability management performance and risk posture**
using quantifiable metrics aligned to business objectives.

**2. Scope**

This framework applies to:

- Infrastructure vulnerabilities (servers, endpoints, network)

- Cloud and container vulnerabilities

- Application vulnerabilities (where integrated with VM program)

- All business units and asset owners

**3. Objectives**

- Measure effectiveness of vulnerability remediation

- Track compliance with defined SLAs

- Provide visibility into enterprise risk exposure

- Enable data-driven decision-making for leadership

- Support regulatory and audit requirements

**4. Metric Categories**

| **Category**       | **Description**                                 |
|--------------------|-------------------------------------------------|
| Efficiency Metrics | Speed and responsiveness (MTTR, SLA compliance) |
| Risk Metrics       | Exposure and risk reduction                     |
| Hygiene Metrics    | Vulnerability aging and backlog                 |
| Coverage Metrics   | Visibility and asset inclusion                  |

**5. Core Metrics Definitions**

**5.1 MTTR (Mean Time to Remediate)**

**Definition**

Average time taken to remediate a vulnerability from **detection to
closure**.

**Formula**

MTTR = (Sum of remediation time for all vulnerabilities) / (Total number
of vulnerabilities remediated)

**Measurement Logic**

- Start Time: Detection timestamp (scan or alert)

- End Time: Verified remediation (re-scan closure)

- Unit: Days

**Targets (Enterprise Standard)**

| **Severity** | **Target MTTR** |
|--------------|-----------------|
| Critical     | ≤ 7 days        |
| High         | ≤ 15 days       |
| Medium       | ≤ 30 days       |
| Low          | ≤ 60–90 days    |

**5.2 SLA Compliance %**

**Definition**

Percentage of vulnerabilities remediated within defined SLA timelines.

**Formula**

SLA Compliance % = (Vulnerabilities resolved within SLA / Total
vulnerabilities) × 100

**Measurement Logic**

- Calculated per severity and business unit

- Measured weekly and monthly

**Target**

- ≥ 95% for Critical/High

- ≥ 90% overall compliance

**5.3 Vulnerability Aging**

**Definition**

Distribution of open vulnerabilities based on how long they have
remained unresolved.

**Aging Buckets**

| **Bucket** | **Duration**           |
|------------|------------------------|
| 0–7 days   | Newly identified       |
| 8–30 days  | Within SLA             |
| 31–60 days | Approaching SLA breach |
| 61–90 days | SLA breached           |
| \>90 days  | Critical backlog       |

**Usage**

- Identify backlog risks

- Highlight overdue vulnerabilities

- Support escalation to business owners

**5.4 Risk Reduction Over Time**

**Definition**

Measurement of how overall vulnerability risk exposure decreases over a
defined period.

**Measurement Model**

- Risk Score = f(CVSS + Asset Criticality + Threat Intelligence)

- Track aggregate risk score trend (weekly/monthly)

**Key Indicators**

- Reduction in total risk score

- Decrease in critical/high vulnerabilities

- Reduction in externally exposed vulnerabilities

**Visualization**

- Trend lines (month-over-month risk reduction)

- Heat maps by business unit

**5.5 Coverage %**

**Definition**

Percentage of total assets that are included in the vulnerability
scanning program.

**Formula**

Coverage % = (Number of assets scanned / Total assets in inventory) ×
100

**Coverage Types**

- Infrastructure coverage

- Cloud asset coverage

- Endpoint coverage

- Application coverage

**Target**

- ≥ 98% asset coverage across enterprise

**6. Data Sources**

| **Source** | **Purpose** |
|----|----|
| Vulnerability Scanners (Qualys, Tenable, Defender VM) | Vulnerability data |
| CMDB | Asset inventory |
| SIEM (e.g., Microsoft Sentinel) | Threat context |
| ITSM (ServiceNow, Jira) | Ticket lifecycle |
| Threat Intelligence Platforms | Exploitability context |

**7. Reporting Structure**

**7.1 Operational Reports (Weekly)**

- MTTR by severity

- SLA compliance %

- Aging distribution

- Top overdue vulnerabilities

**7.2 Management Reports (Monthly)**

- Risk reduction trends

- Business unit comparison

- Coverage %

- Top risk contributors

**7.3 Executive Dashboard (Quarterly)**

- Enterprise risk posture

- MTTR trends

- SLA adherence

- Critical exposure summary

**8. Visualization Standards**

- Use trend graphs for MTTR and risk reduction

- Use bar charts for SLA compliance

- Use heat maps for vulnerability distribution

- Use pie charts for coverage

**9. Thresholds & Alerts**

- SLA breach alerts for critical vulnerabilities

- MTTR deviation alerts

- Coverage drop below threshold

- Increase in risk score

**10. Governance & Review**

- Weekly review by VM and IT Ops teams

- Monthly review with CISO and leadership

- Quarterly board-level reporting

**11. Compliance Alignment**

This framework aligns with:

- NIST (DE.CM, RS.MI)

- ISO 27001 (A.12.6, A.16)

- Center for Internet Security Controls (VM & Metrics)

**12. Continuous Improvement**

- Refine risk scoring models using threat intelligence

- Automate metric collection and reporting

- Integrate with predictive analytics

- Benchmark against industry standards

**13. Appendices**

**Appendix A – Sample Dashboard Layout**

**Appendix B – Metric Calculation Examples**

**Appendix C – Data Dictionary**

**End of Document**
