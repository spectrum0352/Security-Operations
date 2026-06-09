**Vulnerability Management Runbook (Critical)**

**(Enterprise / Fortune-500 Grade – Operational Runbook for SOC, IT Ops
& DevSecOps)**

**1. Purpose**

This runbook provides **step-by-step operational procedures** for
executing the Vulnerability Management lifecycle, specifically focused
on **critical operational activities**.

It ensures:

- Consistent execution across teams

- Rapid response to critical vulnerabilities and zero-days

- Audit-ready operational processes

**2. Scope**

This runbook applies to:

- Security Operations Center (SOC)

- IT Operations

- DevSecOps teams

- Cloud and infrastructure teams

**3. Roles & Responsibilities**

| **Role**                   | **Responsibility**                    |
|----------------------------|---------------------------------------|
| SOC                        | Scan monitoring, triage, escalation   |
| IT Ops                     | Infrastructure remediation            |
| DevSecOps                  | Application vulnerability remediation |
| Security Engineering       | Tool configuration, tuning            |
| CISO / Security Leadership | Oversight during critical events      |

**4. Scan Scheduling Procedures**

**4.1 Objective**

Ensure timely and consistent execution of vulnerability scans across all
environments.

**4.2 Procedure**

**Step 1: Define Scan Scope**

- Identify asset groups (servers, endpoints, cloud, apps)

- Validate against CMDB

**Step 2: Select Scan Type**

- Authenticated scan (preferred)

- Unauthenticated scan (external perspective)

**Step 3: Configure Scan Templates**

- Use standardized templates

- Include latest vulnerability plugins/signatures

**Step 4: Schedule Scans**

| **Scan Type**           | **Frequency**        |
|-------------------------|----------------------|
| Internet-facing assets  | Weekly               |
| Internal servers        | Monthly              |
| Endpoints (agent-based) | Continuous           |
| Applications            | Weekly / per release |

**Step 5: Execute Scan**

- Monitor scan progress

- Ensure successful completion

**Step 6: Validate Results**

- Check scan coverage

- Identify failed scans or unreachable assets

**4.3 Failure Handling**

- Retry failed scans within 24 hours

- Escalate repeated failures to IT Ops

- Investigate network/firewall issues

**5. Credential Rotation Procedure**

**5.1 Objective**

Ensure secure and compliant use of credentials for authenticated
scanning.

**5.2 Procedure**

**Step 1: Identify Credentials**

- Service accounts used for scanning

- Privileged access accounts

**Step 2: Store in Secure Vault**

- Use enterprise secrets management solution

- Enforce encryption

**Step 3: Rotate Credentials**

| **Frequency**     | **Requirement**    |
|-------------------|--------------------|
| Standard          | Every 60–90 days   |
| High-risk systems | Every 30 days      |
| Post-incident     | Immediate rotation |

**Step 4: Update Scanner Configuration**

- Replace credentials in scanning tools

- Validate connectivity

**Step 5: Validate Scans**

- Run test scan to confirm authentication success

**5.3 Monitoring**

- Log credential usage

- Alert on unauthorized access

- Audit periodically

**6. False Positive Handling**

**6.1 Objective**

Ensure accuracy of vulnerability findings and reduce remediation noise.

**6.2 Procedure**

**Step 1: Identify Potential False Positive**

- Reported by IT Ops / Dev teams

- Detected during validation

**Step 2: Validate Finding**

- Cross-check with:

  - Vendor advisories

  - Patch levels

  - System configuration

**Step 3: Reproduce Issue**

- Attempt to verify vulnerability manually

- Use secondary tools if required

**Step 4: Classification**

| **Outcome**             | **Action**                       |
|-------------------------|----------------------------------|
| Confirmed vulnerability | Proceed with remediation         |
| False positive          | Suppress / exclude               |
| Needs further analysis  | Escalate to Security Engineering |

**Step 5: Documentation**

- Record justification for false positive

- Maintain audit trail

**Step 6: Tool Tuning**

- Update scan configurations

- Apply exclusions or filters

**7. Emergency Scanning (Zero-Day Response)**

**7.1 Objective**

Rapidly identify and respond to critical vulnerabilities (zero-day
threats).

**7.2 Trigger Conditions**

- Public disclosure of zero-day vulnerability

- Active exploitation detected (threat intelligence)

- Vendor advisory (e.g., critical patch release)

**7.3 Procedure**

**Step 1: Threat Intelligence Validation**

- Confirm vulnerability details (CVE, affected systems)

- Assess impact to organization

**Step 2: Identify Affected Assets**

- Query CMDB and vulnerability tools

- Use asset tagging and exposure data

**Step 3: Initiate Emergency Scan**

- Launch targeted scan for affected assets

- Use updated plugins/signatures

**Step 4: Prioritize Findings**

- Mark as Critical

- Escalate immediately to SOC and IT Ops

**Step 5: Containment Actions (if needed)**

- Apply temporary controls:

  - Network segmentation

  - Firewall rules

  - Endpoint isolation

**Step 6: Remediation**

- Deploy patches or mitigations

- Apply vendor-recommended workarounds

**Step 7: Executive Communication**

- Provide status updates to leadership

- Report risk exposure and actions taken

**8. Re-Scan Validation Process**

**8.1 Objective**

Ensure vulnerabilities are effectively remediated and closed.

**8.2 Procedure**

**Step 1: Trigger Re-Scan**

- After remediation completion

- Automatically via workflow or manually

**Step 2: Execute Validation Scan**

- Focus on affected assets

- Use authenticated scanning where possible

**Step 3: Verify Results**

| **Result**             | **Action**           |
|------------------------|----------------------|
| Vulnerability resolved | Proceed to closure   |
| Still detected         | Reopen ticket        |
| Partial remediation    | Continue remediation |

**Step 4: Update Ticketing System**

- Update status in ServiceNow

- Attach validation evidence

**Step 5: Closure**

- Mark vulnerability as closed

- Record remediation details

**8.3 Audit Evidence**

- Scan reports

- Patch records

- Ticket closure logs

**9. SLA & Escalation**

| **Severity** | **SLA**      | **Escalation**                     |
|--------------|--------------|------------------------------------|
| Critical     | ≤ 7 days     | Immediate escalation to leadership |
| High         | ≤ 15 days    | Escalate on breach                 |
| Medium       | ≤ 30 days    | Monitor                            |
| Low          | ≤ 60–90 days | Routine                            |

**10. Tools & Platforms**

- Vulnerability scanners (Tenable, Qualys, Defender VM)

- SIEM: Microsoft Sentinel

- EDR: Microsoft Defender for Endpoint

- ITSM: ServiceNow

**11. Key Metrics**

- Scan success rate (%)

- False positive rate (%)

- Time to remediate (MTTR)

- SLA compliance (%)

- Reopen rate after closure

**12. Risks & Mitigations**

| **Risk**                        | **Mitigation**                |
|---------------------------------|-------------------------------|
| Missed critical vulnerabilities | Emergency scanning procedures |
| Credential compromise           | Regular rotation              |
| False positives                 | Validation and tuning         |
| Failed remediation              | Re-scan validation            |

**13. Review & Maintenance**

- Quarterly runbook review

- Update procedures based on incidents and lessons learned

**14. Document Control**

| **Version** | **Date**        | **Owner**           | **Approval** |
|-------------|-----------------|---------------------|--------------|
| 1.0         | \[Insert Date\] | Security Operations | CISO         |

**End of Document**
