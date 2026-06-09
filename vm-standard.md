**Vulnerability Management Standard**

**(Detailed Control Requirements – Audit Ready Standard Document)**

**1. Purpose**

This Vulnerability Management Standard defines the **mandatory technical
and operational controls** required to implement the Vulnerability
Management Policy across the enterprise.

It ensures consistent execution, measurable security outcomes, and audit
readiness across all environments.

**2. Scope**

This standard applies to all systems within scope of the Vulnerability
Management Policy, including:

- On-premises infrastructure

- Cloud environments (IaaS, PaaS, SaaS)

- Endpoints and servers

- Applications and APIs

- Containers and DevOps pipelines

**3. Vulnerability Scanning Controls**

**3.1 Authenticated vs Unauthenticated Scanning**

**3.1.1 Authenticated Scanning (Mandatory)**

Authenticated scans must be configured wherever technically feasible to
ensure deep visibility.

**Control Requirements:**

- Use credentialed scans for servers, endpoints, and databases

- Integrate with directory services (e.g., Active Directory, Azure AD)

- Enable OS-level inspection (patches, registry, configurations)

- Use least-privileged accounts with necessary read access

- Validate scan coverage and success rates

**Minimum Coverage Target:**

- ≥ 95% of enterprise assets must be scanned using authenticated methods

**3.1.2 Unauthenticated Scanning**

Unauthenticated scans must be used to simulate external attacker
perspectives.

**Control Requirements:**

- Perform scans against internet-facing assets

- Validate exposed services, open ports, and misconfigurations

- Identify shadow IT and unknown assets

- Conduct scans from external network vantage points

**3.1.3 Control Validation**

- Compare authenticated vs unauthenticated scan results

- Identify blind spots and scanning gaps

- Maintain scan coverage dashboards

**4. Scan Frequency Requirements**

**4.1 Infrastructure Scanning**

| **Asset Type**          | **Frequency**                      |
|-------------------------|------------------------------------|
| Internet-facing systems | Weekly (minimum)                   |
| Internal servers        | Monthly (minimum)                  |
| End-user devices        | Monthly / Continuous (agent-based) |
| Network devices         | Monthly                            |

**4.2 Application Scanning**

| **Type**                    | **Frequency**                   |
|-----------------------------|---------------------------------|
| Web applications (external) | Weekly or after major release   |
| Internal applications       | Monthly                         |
| APIs                        | Monthly / per deployment        |
| SAST (code scanning)        | Every build (CI/CD integration) |
| DAST                        | Pre-production and periodic     |

**4.3 Cloud & Modern Workloads**

| **Asset Type**      | **Frequency**                          |
|---------------------|----------------------------------------|
| Cloud workloads     | Continuous / Near real-time            |
| Containers (images) | Every build + registry scan            |
| Kubernetes clusters | Continuous monitoring                  |
| Serverless          | Continuous security posture assessment |

**4.4 Event-Driven Scanning**

Additional scans must be triggered upon:

- Critical vulnerability disclosures (e.g., zero-day)

- Major infrastructure changes

- New asset onboarding

- Security incidents

**5. Patch Management Integration**

**5.1 Integration Requirements**

- Vulnerability management tools must integrate with patch management
  systems

- Automatic ticket creation for remediation (ITSM integration, e.g.,
  ServiceNow)

- Bi-directional status updates between tools

**5.2 Patch Prioritization**

- Align patching with risk-based prioritization (CVSS + business
  context)

- Prioritize:

  - Exploited vulnerabilities

  - Internet-facing systems

  - Critical business services

**5.3 Patch Deployment Controls**

- Test patches in staging environments before production deployment

- Maintain rollback procedures

- Track patch success and failure rates

**5.4 Verification**

- Conduct re-scans post-remediation

- Validate closure of vulnerabilities

- Ensure no regression issues

**6. Credential Management for Scanners**

**6.1 Credential Security Requirements**

- Store credentials securely in vault systems (e.g., enterprise secrets
  vault)

- Enforce encryption at rest and in transit

- Prohibit hardcoded credentials

**6.2 Access Control**

- Use least privilege access model

- Separate credentials per environment (prod, non-prod)

- Enforce multi-factor authentication (where applicable)

**6.3 Credential Rotation**

- Rotate scanning credentials periodically (e.g., every 60–90 days)

- Immediately rotate upon suspected compromise

**6.4 Monitoring & Audit**

- Log all credential usage by scanning tools

- Audit access periodically

- Detect abnormal usage patterns

**7. Tool Standards**

The organization must standardize on approved vulnerability management
tools to ensure consistency and scalability.

**7.1 Approved Tool Categories**

**7.1.1 Vulnerability Scanning Platforms**

- Tenable (e.g., Tenable.io / Nessus)

- Qualys Vulnerability Management

- Microsoft Defender Vulnerability Management

**7.2 Tool Selection Criteria**

All tools must meet the following requirements:

- Support authenticated and unauthenticated scanning

- Provide CVSS scoring and risk-based prioritization

- Integrate with SIEM (e.g., Microsoft Sentinel)

- Provide API-based integrations

- Support cloud-native environments

- Enable agent-based and agentless scanning

- Provide reporting and dashboards

**7.3 Configuration Standards**

- Standardized scan templates across environments

- Centralized policy management

- Tagging of assets based on business criticality

- Integration with CMDB for asset inventory

**7.4 Tool Governance**

- Maintain tool inventory and ownership

- Periodically review tool effectiveness

- Ensure licensing compliance

- Perform regular tool updates and upgrades

**8. Data Management & Reporting**

**8.1 Data Retention**

- Retain scan data for minimum 12 months (or per regulatory requirement)

**8.2 Reporting Requirements**

- Daily/weekly operational reports

- Monthly executive dashboards

- SLA compliance reporting

- Audit-ready evidence generation

**9. Compliance & Audit Controls**

This standard supports compliance with:

- ISO 27001 (A.12.6.1 – Technical Vulnerability Management)

- NIST SP 800-53 (RA-5, SI-2)

- PCI DSS (Req. 6 & 11)

**10. Exceptions**

Any deviation from this standard must:

- Follow formal exception process defined in the policy

- Be documented and approved

- Include compensating controls

**11. Enforcement**

- Non-compliance will be escalated to Security Governance

- Repeat violations may result in audit findings

- Critical control failures require immediate remediation

**12. Review & Updates**

- This standard must be reviewed annually

- Updated based on emerging threats and technologies

**13. Document Control**

| **Version** | **Date**        | **Owner**            | **Approval** |
|-------------|-----------------|----------------------|--------------|
| 1.0         | \[Insert Date\] | Security Engineering | CISO         |

**End of Document**
