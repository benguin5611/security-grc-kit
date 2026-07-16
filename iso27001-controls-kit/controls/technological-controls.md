# A.8 Technological controls

The 34 controls governing the technical implementation of security: endpoints, access, cryptography, operations, networks, and the secure development lifecycle. This is the second-largest theme by control count (A.5 Organizational has 37), and the one where engineering-heavy teams will already recognise most of the content.

---

### A.8.1 User endpoint devices

**What it requires:** Information stored on, processed by, or reachable from devices end users work on (laptops, phones, tablets) needs to stay protected no matter where or how that device is used.

**Implementation guidance:**
- Maintain a documented endpoint/mobile device policy covering issuance, acceptable use, and offboarding.
- Enforce full-disk encryption, automatic screen lock, and remote-wipe capability on every endpoint that holds or can reach company information.
- Manage devices centrally through an endpoint/mobile device management tool so security baselines can be pushed out and drift detected.
- If BYOD is permitted, separate personal and corporate data on the device (containerisation or managed app profiles); otherwise issue managed corporate devices only.
- Require devices to be enrolled and compliant before they're granted access to corporate systems, tying device posture to conditional access rules.
- Define and follow a secure wipe/disposal process for devices being retired, lost, or reissued.

**Evidence an assessor would want to see:**
- Current endpoint/mobile device policy, reviewed at least annually.
- Device management enrolment and compliance reports showing coverage across the fleet.
- Records of wipe/offboarding actions for departed staff or retired devices.
- Conditional access configuration linking device compliance to system access.

### A.8.2 Privileged access rights

**What it requires:** Accounts with elevated system access need to be tightly controlled, limited to people who genuinely need them, and reviewed regularly so entitlements don't quietly accumulate.

**Implementation guidance:**
- Maintain a documented privileged access policy defining what counts as privileged access and who is eligible to hold it.
- Grant privileged access on a named, least-privilege, need-to-know basis; never shared or generic admin accounts.
- Require separate accounts for everyday work versus administrative tasks, so privileged sessions are deliberate and traceable.
- Enforce multi-factor authentication on every privileged account without exception.
- Log and actively monitor privileged account activity, alerting on unusual or out-of-hours use.
- Run a periodic (e.g., quarterly) review of everyone holding privileged access and remove entitlements no longer justified by role.

**Evidence an assessor would want to see:**
- Privileged access policy and any supporting procedure/standard.
- Current register or system export of privileged accounts mapped to business justification.
- Completed privileged-access review records with sign-off.
- Logging/alerting configuration showing privileged activity is actively monitored.

### A.8.3 Information access restriction

**What it requires:** Access to information and the systems holding it must follow a defined, risk-based access control policy rather than being granted informally.

**Implementation guidance:**
- Maintain a documented access control policy built on least privilege, need-to-know, and role-based access principles.
- Assign access by role or group rather than one-off per-user grants, using role-based access control where the platform supports it.
- Require a documented approval step (manager or system owner) before granting access to sensitive systems or data sets.
- Review user access rights on a defined schedule, and immediately whenever someone changes role or leaves.
- Apply the same restriction principles consistently to employees and to contractors or third parties.
- Segregate duties for sensitive functions so the same person can't both request and approve their own access, or execute and approve a sensitive transaction unchecked.

**Evidence an assessor would want to see:**
- Access control policy, reviewed and approved within the last 12 months.
- Sample access request/approval trail for critical systems.
- Periodic access review (attestation) records.
- Joiner/mover/leaver process documentation showing access changes with role changes and terminations.

### A.8.4 Access to source code

**What it requires:** Read and write access to source code, build tooling, and libraries must be tightly controlled so only authorised people can view or change them, with changes traceable.

**Implementation guidance:**
- Maintain a secure development standard that sets out access requirements for code repositories, build systems, and library/package sources.
- Host code in a proper version-control repository system with repository- and branch-level permissions; never shared file storage or ad hoc copies.
- Grant repository access on a least-privilege basis tied to actual job responsibility, revoked promptly on role change or offboarding.
- Require independent code review (e.g., a second approver on a pull/merge request) before changes merge into protected branches.
- Turn on audit logging for the repository platform and periodically review access grants and unusual activity, such as bulk clones or permission escalations.
- Keep credentials and secrets out of source code entirely; use a secrets manager and scan repositories for anything accidentally committed.

**Evidence an assessor would want to see:**
- Secure development standard/policy document.
- Repository permission export showing access scoped to authorised individuals or teams, with branch-protection rules requiring independent review before merge.
- Merge/pull request history showing the request → review → approval → merge timeline, with a visible independent-reviewer approval on a sample of recent changes.
- Periodic access review or audit log sample confirming source code access is monitored.

### A.8.5 Secure authentication

**What it requires:** Authentication methods and procedures need to be strong enough for what they're protecting, applied consistently with the organisation's access control policy.

**Implementation guidance:**
- Centralise authentication through a single sign-on identity provider wherever the application supports it, rather than scattered local accounts.
- Enforce multi-factor authentication at the identity provider and directly on any high-value application that supports it.
- For the smaller set of systems that can't integrate with single sign-on, apply compensating controls: enforced password complexity/length, a company-approved password manager, and MFA where the application allows it.
- Disable or tightly restrict legacy authentication protocols that bypass multi-factor authentication.
- Set session controls: idle timeouts and step-up re-authentication for sensitive actions.
- Monitor sign-in logs for anomalies such as impossible travel, repeated failures, or credential-stuffing patterns.

**Evidence an assessor would want to see:**
- Application inventory showing SSO/MFA coverage versus exceptions and their compensating controls.
- Identity provider configuration evidence showing MFA enforcement.
- Password policy configuration (complexity, history, lockout thresholds).
- Sign-in log samples or alerting configuration for anomalous authentication.

### A.8.6 Capacity management

**What it requires:** Resource usage across infrastructure and services must be monitored and planned ahead so that current and forecast demand doesn't outrun available capacity.

**Implementation guidance:**
- Maintain a capacity management process covering compute, storage, network, and key application-level resources.
- Monitor utilisation of critical infrastructure and services against defined thresholds, with alerting before limits are reached.
- Forecast future capacity needs based on growth trends, planned initiatives, and seasonal or peak demand.
- Build in scaling mechanisms (auto-scaling, elastic storage) for workloads with variable demand.
- Review capacity plans and actual utilisation on a regular cadence and after any major growth event.
- Fold capacity impact assessment into the change management process for new services or significant scaling changes.

**Evidence an assessor would want to see:**
- Capacity management process document.
- Monitoring dashboards or reports showing utilisation trends against thresholds.
- Records of capacity planning reviews and resulting decisions.
- Evidence of a scaling action taken in response to a forecast or threshold breach.

### A.8.7 Protection against malware

**What it requires:** Technical defences against malware must be in place and reinforced by user awareness, so malicious code is detected, prevented, and recovered from.

**Implementation guidance:**
- Deploy a centrally managed endpoint anti-malware/EDR solution across all corporate endpoints and servers, with policy and reporting managed centrally.
- Keep detection signatures/behavioural models and the agent itself updating automatically.
- Enable host-based firewalls on every endpoint using the protections built into the operating system, layered on top of network-level controls.
- Restrict execution of unauthorised or unapproved software where practical, through allow-listing or removing local admin rights.
- Provide regular security awareness training covering phishing, social engineering, and safe handling of attachments and links, in line with a documented training policy.
- Define and test an incident response procedure specific to malware/ransomware detections, including isolation and recovery steps.

**Evidence an assessor would want to see:**
- Anti-malware/EDR deployment and coverage report confirming all endpoints are protected and current.
- Host firewall configuration/policy evidence.
- Security awareness training policy and completion records.
- A sample malware detection alert with the resulting response/ticket.

### A.8.8 Management of technical vulnerabilities

**What it requires:** The organisation needs to stay informed about technical vulnerabilities affecting its systems, assess its exposure to them, and act on that assessment in good time.

**Implementation guidance:**
- Run regular automated vulnerability scans across infrastructure, endpoints, and applications.
- Subscribe to vendor security advisories and relevant public vulnerability feeds for all software and platforms in use.
- Commission independent penetration testing at least annually, and after significant architecture changes.
- Maintain a vulnerability management policy defining severity ratings and remediation timeframes by risk level.
- Track every identified vulnerability through to remediation or a documented risk-acceptance decision, with a named owner.
- Periodically test systems for compliance with the organisation's own access control and secure development standards, not only against known CVEs.

**Evidence an assessor would want to see:**
- Vulnerability management policy defining scan cadence and remediation SLAs.
- Automated dependency/secret-scanning tool output wired into the CI pipeline, plus vulnerability scan reports with remediation tracked and closed within SLA.
- Most recent independent penetration test report with evidence findings were remediated or formally risk-accepted.
- Vendor advisory/patch tracking log for critical systems, and a threat-intelligence/CVE feed subscription feeding the process.

### A.8.9 Configuration management

**What it requires:** Secure configuration baselines for hardware, software, services, and networks need to be defined, documented, applied, monitored, and periodically reviewed.

**Implementation guidance:**
- Define secure configuration baselines/hardening standards for each major platform type (endpoints, servers, network devices, cloud services), referencing recognised industry hardening benchmarks.
- Document baselines in a central, version-controlled location and reference them from the relevant technical standards.
- Deploy configuration through managed tooling (device management, infrastructure-as-code, configuration management systems) rather than manual one-off setup, so baselines are repeatable and drift is detectable.
- Monitor deployed systems for drift from the approved baseline and remediate or formally re-approve any deviation.
- Review baseline configurations on a defined schedule, at minimum annually, and immediately after any material change to the system or its threat environment.
- Record the outcome of each baseline review, including any changes made and the reasoning behind them.

**Evidence an assessor would want to see:**
- Documented configuration baselines/hardening standards for each platform type.
- Configuration or drift monitoring reports, or an infrastructure-as-code repository showing baseline enforcement.
- Records of the most recent baseline review (date, scope, outcome).
- Change records showing baseline updates following a material system change.

### A.8.10 Information deletion

**What it requires:** Information should not be retained indefinitely. Once data held in systems, devices, or any storage media is no longer needed for its original purpose, a legal obligation, or a contractual duty, it must be securely and irreversibly deleted or destroyed.

**Implementation guidance:**
- Maintain a data retention and disposal schedule that maps each category of information (customer data, logs, HR records, financial records, etc.) to a defined retention period and the legal or contractual basis for it.
- Define clear deletion triggers: end of contract, expiry of the retention period, a data subject erasure request, or decommissioning of a system or device.
- Use destruction methods appropriate to the medium: cryptographic erasure or multi-pass wipe for storage media, physical destruction for end-of-life hardware, and verified deletion across all replicas (including backups and caches) for cloud-held data.
- Extend deletion obligations contractually to any third party or subprocessor that holds copies of the data on your behalf.
- Log and evidence each deletion or destruction event, including who authorised it and confirmation that the full data set was removed.
- Build in an exceptions process for legal holds or active investigations that require scheduled deletion to be paused.

**Evidence an assessor would want to see:**
- A documented retention and disposal schedule covering all major information categories.
- Deletion logs or certificates of destruction.
- Evidence that erasure requests were completed within the policy timeframe.
- Subprocessor contracts showing deletion obligations on offboarding.

### A.8.11 Data masking

**What it requires:** Sensitive data should be obscured or transformed so it can be used in lower-trust contexts (testing, analytics, support) without exposing the real underlying values.

**Implementation guidance:**
- Classify which fields hold sensitive or personal information so masking rules can be scoped precisely, avoiding both over-masking (breaking usability) and under-masking (leaving gaps).
- Apply the technique that fits the use case: substitution, character redaction, hashing, date or numeric perturbation ("jittering"), or format-preserving encryption.
- Prefer irreversible techniques (hashing, anonymisation) when the original value is never needed again; reserve reversible techniques (encryption, tokenisation) for cases where a legitimate process must recover the original, and keep the reversal key or mapping under separate, tighter access control.
- Apply masking automatically as data flows into non-production environments so real sensitive values never land in test, staging, or analytics systems in the clear.
- Revisit masking rules whenever the schema changes, so new sensitive fields don't slip through unmasked.
- Periodically test that masked data can't be re-identified by inference or by combining it with other available datasets.

**Evidence an assessor would want to see:**
- A data classification or inventory identifying which fields require masking.
- A documented masking standard describing approved techniques per data type.
- Pipeline or configuration evidence showing masking is applied before data reaches lower-trust environments.
- Records of periodic review of masking rules against the current data model.

### A.8.12 Data leakage prevention

**What it requires:** Controls should be in place across the networks, endpoints, and systems that handle sensitive information to detect and stop its unauthorised disclosure or exfiltration.

**Implementation guidance:**
- Map the channels through which leakage could realistically occur (email, cloud file-sharing, removable media, printing, code repositories, chat and collaboration tools) and apply controls proportionate to the risk on each.
- Deploy a data loss prevention (DLP) capability that inspects outbound content for sensitive data patterns (PII, credentials, financial data) and can block, quarantine, or alert on violations.
- Restrict or monitor removable storage and personal cloud storage on endpoints that handle sensitive data.
- Apply egress controls at the network boundary, complementing endpoint-level controls rather than relying on either alone.
- Pair technical DLP controls with strong access control and least privilege, so fewer people and systems can reach sensitive data in the first place.
- Review DLP alerts on a defined cadence and route confirmed incidents into the incident management process.

**Evidence an assessor would want to see:**
- DLP policy and ruleset configuration, with change history.
- Sample alert/incident records showing detection, triage, and resolution.
- Records of periodic review of DLP rules and their effectiveness.
- Endpoint or removable-media control configuration (e.g., disabled USB storage, managed file-sharing allowlist).

### A.8.13 Information backup

**What it requires:** Critical information, software, and systems must be backed up on a regular schedule, and those backups must actually be tested to confirm they can be restored within the required timeframe.

**Implementation guidance:**
- Set backup frequency, retention, encryption, and location per system based on its criticality, working back from agreed recovery point objectives (RPO) and recovery time objectives (RTO).
- Build a buffer above the minimum RPO/RTO so a single delayed or failed job doesn't put you outside your service commitments.
- Automate backups where possible and monitor job success and failure actively, so a missed backup is caught immediately rather than discovered during a real recovery.
- Store backups with logical, and where practical physical or geographic, separation from the source system, so a single failure or compromise (e.g., ransomware) can't take out both the primary data and its backup.
- Encrypt backups at rest and in transit, and apply the same access controls to backup data as to the production data it contains.
- Run restore tests on a regular schedule, not just backup-success checks, and record the outcome, including time taken to restore, against the RTO target.

**Evidence an assessor would want to see:**
- A backup standard defining frequency, retention, and RPO/RTO per system tier.
- Backup job success/failure monitoring records.
- A restore-test report or log with a specific test date and the result (data restored successfully within target), not just a record that backups completed.
- Evidence of backup encryption, access restrictions, and geographic separation from the source system.

### A.8.14 Redundancy of information processing facilities

**What it requires:** Systems and infrastructure that process information should carry enough redundancy to meet the organisation's availability requirements, so that a single failure doesn't take a service down.

**Implementation guidance:**
- Define availability requirements (target uptime, acceptable downtime) per service based on business impact, and size redundancy to match; not every system needs the same level of resilience.
- Deploy critical systems across multiple availability zones or physically separate facilities so a localised outage in power, network, or hardware doesn't take out the whole service.
- Confirm redundant power, network connectivity, and other critical infrastructure components are genuinely in place at each zone or facility relied on.
- Where infrastructure or platform services come from third parties, obtain and track service level agreements (SLAs) stating expected availability and performance.
- Monitor actual availability and performance against those SLA commitments on an ongoing basis, and escalate with the provider when targets are missed.
- Test failover between zones or regions periodically, rather than assuming redundancy works until the day it's needed.

**Evidence an assessor would want to see:**
- Architecture documentation showing redundant components or availability zones for critical systems.
- Provider SLAs and periodic reports showing actual availability against target.
- Records of failover testing, or of incidents where redundancy was exercised.
- Business-impact or availability requirements mapped to system criticality tiers.

### A.8.15 Logging

**What it requires:** User activity, system exceptions and faults, and security-relevant events should be logged, retained for an appropriate period, protected against tampering, and reviewed.

**Implementation guidance:**
- Enable logging of user activity, exceptions/faults, and security-relevant events across critical systems, applications, and infrastructure.
- Give particular attention to privileged and administrative activity: these accounts carry the most risk, and their actions should be individually attributable.
- Set a log retention period long enough to support investigations and any regulatory or contractual requirement, and apply it consistently across systems.
- Protect log data from tampering and unauthorised access by writing it to a centralised, access-controlled store separate from the systems that generate it, and restricting who can modify or delete entries.
- Review logs on a defined, recurring cadence rather than only after something goes wrong, and keep a record that the review happened.
- Capture enough detail in each entry (timestamp, actor, action, outcome) to support an investigation, and keep clocks synchronised across systems so events can be correlated.

**Evidence an assessor would want to see:**
- A logging standard listing which systems and event types are captured.
- Evidence of centralised, access-restricted log storage.
- Records of periodic log review (notes, tickets, or reports).
- Sample logs showing privileged/admin activity is captured and attributable.

### A.8.16 Monitoring activities

**What it requires:** Networks, systems, and applications should be actively watched for abnormal behaviour, with a defined process for assessing and responding to anything that could indicate a security incident.

**Implementation guidance:**
- Run monitoring reviews on a regular cycle (e.g., monthly, or more frequently for higher-risk environments) rather than relying purely on ad hoc alerting.
- Cover a broad set of sources: inbound/outbound network traffic to and from cloud and hosting environments, logs from business-critical applications, endpoint protection and threat alerts, web/content filtering logs, DLP alerts, mobile device management logs, vulnerability scan results, and device enrolment requests.
- Define what counts as "anomalous" for each source so reviewers and tooling are consistent, and tune thresholds over time to cut noise.
- Assign clear ownership per monitoring source: who reviews it, how often, and what they do when something looks wrong.
- Feed confirmed anomalies into the incident response process with a defined escalation path and timeframe.
- Keep a record of each review cycle (what was checked, what was found, and what action was taken) as ongoing evidence the control is operating.

**Evidence an assessor would want to see:**
- A monitoring schedule or checklist showing sources covered and review cadence.
- Completed review records for recent cycles (e.g., sign-off logs).
- Sample alerts with their resolution/escalation trail.
- An ownership matrix mapping monitoring sources to responsible roles.

### A.8.17 Clock synchronisation

**What it requires:** All information processing systems should have their clocks synchronised to a single, accurate reference time source, so timestamps stay consistent across the environment.

**Implementation guidance:**
- Choose one authoritative time source (e.g., a trusted NTP/NTS service) as the reference for the whole environment, rather than letting each system rely on its own local clock.
- Configure servers, network devices, endpoints, and cloud resources to synchronise to that reference automatically and on a regular interval.
- Monitor for clock drift and alert when a system falls out of tolerance.
- Apply the same reference source consistently across production, staging, on-premises, and cloud environments so timestamps from different systems can be correlated during an investigation.
- Restrict who can change time-source configuration, since altering system time can be used to obscure the true sequence of events during an attack.

**Evidence an assessor would want to see:**
- Time synchronisation configuration across representative systems.
- Monitoring/alerting configuration for clock drift.
- Records of any drift incidents and their remediation.
- Confirmation that log timestamps across systems are consistent and correlatable.

### A.8.18 Use of privileged utility programs

**What it requires:** Tools capable of overriding normal system, application, or security controls (admin utilities, debugging tools, low-level scripts) need to be tightly restricted so they can't be used to bypass security measures, whether by accident or intent.

**Implementation guidance:**
- Default every workstation and account to a standard, non-privileged profile; do not grant local admin rights as a default setting.
- Restrict privileged/admin access to a defined technical role (e.g. engineering or IT) unless a documented exception process grants it elsewhere.
- Provide a lightweight, auditable exception process for non-technical staff with a genuine business need for elevated access, scoped or time-boxed where practical.
- Use endpoint/device management tooling to enforce the standard-user baseline and log all use of privileged utilities so activity is reviewable after the fact.
- Periodically review who holds privileged or admin rights and revoke anything no longer needed.

**Evidence an assessor would want to see:**
- Device management configuration showing a standard-user baseline enforced organisation-wide.
- A current list of accounts/roles with privileged access, plus approval records for any exceptions.
- Logs demonstrating privileged utility use is captured and periodically reviewed.
- Records of periodic access reviews with dates and outcomes.

### A.8.19 Installation of software on operational systems

**What it requires:** Organisations need controlled procedures governing what software can be installed on live systems, who can install it, and how installations are kept in check, so unauthorised or unvetted software doesn't reach operational environments.

**Implementation guidance:**
- Maintain a documented standard covering end-user software installation, procurement/update of licensed commercial software, and use of third-party or open-source components within your own products and infrastructure.
- Keep a central, living register of approved software and technology, including version information where relevant, and require new tools to be vetted and added before use rather than installed ad hoc.
- Deploy proactive alerting that flags installation of unapproved software so exceptions surface immediately rather than at the next audit.
- Run periodic compliance reviews against the approved list, formally recording any non-compliance found and tracking remediation to closure.
- Restrict install privileges on operational/production systems to authorised roles only, tying this control back to your privileged-access controls.

**Evidence an assessor would want to see:**
- The approved technology/software register, kept current.
- Alerting configuration and sample output showing unauthorised installs are detected.
- Periodic review reports documenting checks performed, exceptions found, and remediation evidence.
- Approval records for additions to the approved software register.

### A.8.20 Networks security

**What it requires:** Networks and the devices that make them up must be actively secured, managed, and monitored so that information flowing through systems and applications stays protected from unauthorised access or disruption.

**Implementation guidance:**
- Maintain a documented network security standard covering how networks and network devices are configured, hardened, monitored, and maintained.
- Maintain a companion standard for remote and third-party connectivity, since most organisations' effective network boundary now includes home offices, shared workspaces, and mobile connections.
- Define minimum security requirements for any network a company system or endpoint connects through: encryption in transit, authenticated access, and monitoring at a minimum.
- Assign clear ownership for network security controls: who configures them, who reviews them, who responds to alerts.
- Review the network architecture and controls on a regular cadence and whenever the topology changes materially (new sites, new cloud regions, new connectivity models).

**Evidence an assessor would want to see:**
- Current network security and remote-connectivity standards, version-controlled with review history.
- A network architecture diagram reflecting the actual environment.
- Evidence of scheduled control reviews, including sign-off.
- Records of any network security incidents and their resolution.

### A.8.21 Security of network services

**What it requires:** For every network service in use, in-house or third-party, the organisation must identify and validate the security features, agreed service levels, and management requirements that apply to it.

**Implementation guidance:**
- Identify every network service in use (cloud provider networking, ISP links, shared/coworking-space networks, VPN or zero-trust access services) and document them in one place.
- For each externally provided service, capture the relevant security commitments and service levels from the provider's agreement (encryption standard, uptime, incident-notification obligations).
- Cross-reference those commitments against your own network security, remote-access, and cryptography standards so gaps are visible.
- Where a facility is a shared or third-party-managed space, treat its network service levels as governed by that provider's contract rather than assuming your own controls apply, and document that boundary explicitly.
- Periodically confirm each provider is still meeting the documented service levels, via reported uptime, certifications, or contract renewal review.

**Evidence an assessor would want to see:**
- A register of network services mapped to their provider agreements and required security levels.
- Extracts of contracts/terms evidencing the committed security and service levels.
- Periodic review notes confirming providers still meet agreed requirements.

### A.8.22 Segregation of networks

**What it requires:** Distinct groups of users, systems, and services should be separated within the network so that a compromise of one segment doesn't give an attacker unrestricted reach into another.

**Implementation guidance:**
- Map your actual network topology first (remote/home connections, mobile hotspots, VPN entry points, and any office or shared-workspace networks) before deciding how to segment it.
- Require remote connections into corporate systems to go through an approved path: a reasonably secured home network, a private mobile hotspot, or a company-managed VPN/zero-trust client, rather than untrusted public networks directly.
- In cloud-hosted environments where the underlying physical network isn't owned or managed by you, achieve segregation through logical controls instead of physical boundaries: access control lists, security groups, and role-based network policies that define exactly what can talk to what.
- Apply least privilege at the network layer, segmenting by function or sensitivity (production vs non-production, management plane vs application plane) using these logical constructs.
- Document the reasoning where logical, identity-based segregation is the primary control in place of physical segregation, so the design decision is traceable in your risk assessment.

**Evidence an assessor would want to see:**
- A network/segmentation diagram showing logical boundaries between environments.
- Configuration exports or infrastructure-as-code showing the security-group/ACL rules that enforce segregation.
- A remote-access standard defining approved connection methods.
- Periodic review records of segmentation rules and any changes made.

### A.8.23 Web filtering

**What it requires:** Outbound access to external websites should be actively managed so users and systems are less likely to reach malicious or otherwise unwanted content.

**Implementation guidance:**
- Deploy web/content filtering at the endpoint or network egress level (DNS-based filtering, secure web gateway, or endpoint agent) to block known-malicious domains and categories of unwanted content.
- Maintain and regularly update filtering rules using category- and threat-intelligence-based lists rather than a static, manually curated list.
- Apply filtering consistently across all managed devices, including remote and home-based endpoints, not just office networks.
- Log blocked and flagged access attempts and review them periodically for signs of compromise, such as repeated attempts to reach known bad domains.
- Define a clear exception process for legitimately blocked business sites, with a named approver and an audit trail.

**Evidence an assessor would want to see:**
- Web filtering configuration and policy showing the categories/lists enforced.
- Logs of blocked attempts and evidence of periodic review.
- Exception requests and approvals for unblocked sites.

### A.8.24 Use of cryptography

**What it requires:** The organisation must set clear rules for when and how cryptography is used (including acceptable algorithms and key lengths) and manage cryptographic keys through their full lifecycle.

**Implementation guidance:**
- Maintain a cryptography standard specifying, for each common scenario (data at rest, data in transit, authentication tokens, etc.), whether encryption is mandatory and which algorithm and key length are acceptable.
- Provide practical guidance alongside the rules: what's allowed and when to apply which control, so engineers can make correct decisions without escalation.
- Define key-management responsibilities explicitly: who generates keys, how they're stored, rotated, and retired, and who owns that lifecycle end to end.
- Assign a named owner for each information asset in scope of the standard, responsible for confirming the required cryptographic control is actually applied.
- Maintain a register of sensitive cryptographic material, such as API keys, tied to your asset/technology register, so ownership and rotation status stay traceable.
- Review the standard periodically against current best practice (algorithm deprecation, key-length recommendations) and update it proactively.

**Evidence an assessor would want to see:**
- The cryptography standard itself, version-controlled with review history.
- A register of API keys/cryptographic material with named owners.
- Evidence that asset owners have attested their assets meet the required control.
- Key rotation records or key-management tool configuration.

### A.8.25 Secure development life cycle

**What it requires:** Software and systems must be built under a defined set of secure-development rules applied consistently across the full development lifecycle, including work carried out by external or contracted developers.

**Implementation guidance:**
- Maintain a secure development standard covering the full lifecycle: secure design and architecture review, secure coding practices, code review, security testing (static analysis, dependency scanning, etc.), and secure deployment.
- Extend the same rules to third-party or contracted development work by writing secure-development requirements into contracts and statements of work, not just internal practice.
- Cross-reference the secure development standard with your software-installation and network-security standards so environment provisioning and dependency management follow consistent rules.
- Define a narrow, explicit carve-out for prototypes or proof-of-concept work that will never reach production, so the rules stay meaningful for real delivery work rather than being diluted everywhere.
- Bound that carve-out clearly: prototypes must be rebuilt to standard before promotion toward production, and must never handle real customer data.
- Review the secure development standard on a regular cadence and after any significant tooling or process change, such as a new pipeline, language, or cloud service.

**Evidence an assessor would want to see:**
- The secure development standard, with version and review history.
- Contract or statement-of-work language requiring secure development practices from third-party developers.
- Evidence of secure code review and security testing embedded in the delivery pipeline (tickets, pipeline configuration, scan reports).
- A documented definition of what qualifies as prototype/proof-of-concept work, with evidence it isn't used to bypass controls for production work.

### A.8.26 Application security requirements

**What it requires:** Before building or acquiring an application, the specific information-security needs it must satisfy should be identified, documented, and formally agreed upfront, not left to be discovered after the fact.

**Implementation guidance:**
- Add a security-requirements step to the intake process for any new application, feature, or purchased software product.
- Classify the data the application will handle (e.g. public, internal, confidential, restricted) and derive control requirements (encryption, access control, retention, logging) from that classification.
- Maintain a baseline security requirements checklist (authentication, authorisation, input validation, audit logging, data protection, dependency vetting) that every project either follows or explicitly deviates from with a documented reason.
- For purchased or SaaS applications, fold these requirements into vendor due-diligence and contractual clauses rather than treating security as a bolt-on after selection.
- Require sign-off from someone with security accountability, separate from the delivery lead, before requirements are considered final.
- Revisit requirements whenever an application's data classification, user base, or integration surface changes materially.

**Evidence an assessor would want to see:**
- A documented security requirements template and completed examples for recent projects.
- Approval/sign-off records for those requirements.
- Data classification linked explicitly to the requirements selected.
- Vendor due-diligence records showing security requirements factored into procurement decisions.

### A.8.27 Secure system architecture and engineering principles

**What it requires:** A documented set of secure-by-design engineering principles should be established, maintained, and consistently applied across all system development work.

**Implementation guidance:**
- Adopt a documented set of secure-engineering principles (e.g. defence in depth, least privilege, fail securely, secure defaults, trust boundaries between components) as the reference standard for architecture decisions.
- Require an architecture or design review for new services and significant changes, checking alignment with these principles before implementation begins.
- Maintain reusable reference architectures or approved patterns (authentication flows, data-storage patterns, network segmentation) so teams don't reinvent security decisions on every project.
- Make threat modelling a standard step for new systems or major architectural changes, especially those handling sensitive data or exposed to untrusted networks.
- Review and refresh the principles periodically against emerging threats, past incidents, and current industry guidance.
- Ensure the principles are trained on and accessible to all engineers, not held only by a security team.

**Evidence an assessor would want to see:**
- A version-controlled secure-engineering principles/standards document.
- Design review records for a sample of recent projects showing the principles applied.
- Threat-model artefacts for at least one recent significant system or change.
- Evidence the principles have been reviewed/updated on a defined cadence.

### A.8.28 Secure coding

**What it requires:** Secure coding standards and practices should be applied consistently so software resists common vulnerability classes from the outset, rather than having security retrofitted later.

**Implementation guidance:**
- Adopt a secure coding standard covering the languages and frameworks in use: input validation, output encoding, parameterised queries, safe error handling, secrets management, dependency hygiene.
- Provide secure-coding training for all engineers as part of onboarding, refreshed periodically, with completion tracked.
- Enforce secure coding practices through automated static analysis in the build pipeline, with agreed thresholds for what blocks a merge or release.
- Require peer review for all code changes, with security-relevant checks (authentication, input handling, data exposure) as an explicit line item in the review checklist.
- Maintain an approved list of vetted libraries/frameworks and a process for evaluating, updating, and patching third-party dependencies.
- Track recurring vulnerability classes found in review or testing and feed them back into the coding standard and training material.

**Evidence an assessor would want to see:**
- The secure coding standard/guideline document.
- Training completion records for engineering staff.
- Static analysis configuration and sample results showing findings were triaged and resolved.
- Code review records demonstrating the security checklist was applied.

### A.8.29 Security testing in development and acceptance

**What it requires:** Security testing should be defined and carried out at set points across the development lifecycle so vulnerabilities are found and fixed before release.

**Implementation guidance:**
- Define which security tests apply at which stage: static analysis on every change, dependency/vulnerability scanning at build time, dynamic or penetration testing ahead of major releases.
- Set clear pass/fail or risk-acceptance criteria per test type, so a release cannot proceed with unresolved critical or high findings without a documented, approved exception.
- Make security testing a mandatory part of acceptance criteria for new systems, major changes, and third-party integrations, not a functional-testing afterthought.
- Commission independent security testing (e.g. penetration testing, external review) periodically, in addition to automated in-pipeline checks.
- Track identified vulnerabilities through to remediation with an owner and target date, and retest after a fix to confirm it holds.
- Feed patterns from recurring findings back into secure coding standards and training.

**Evidence an assessor would want to see:**
- A documented security testing process mapped to lifecycle stages.
- Sample test reports (static analysis, dependency scan, penetration test) with remediation tracking.
- Acceptance criteria documentation showing security testing as a required gate.
- Records of independent/external testing and the resulting follow-up actions.

### A.8.30 Outsourced development

**What it requires:** Development work carried out by external parties should be directed, monitored, and reviewed to the same standard as in-house work, so outsourcing doesn't create a security blind spot.

**Implementation guidance:**
- Include security requirements (secure coding standards, testing obligations, confidentiality, IP ownership) explicitly in contracts and statements of work with development vendors.
- Vet outsourced developers through the same (or an equivalent) security due-diligence process used for other third parties before granting code or system access.
- Restrict outsourced contractors to the minimum systems, environments, and data needed for their specific task, with time-bound access where practical.
- Route code produced by outsourced parties through the same review, static analysis, and testing gates as internally developed code before it merges or deploys.
- Monitor outsourced development activity on an ongoing basis (commit review, milestone check-ins, test results) rather than treating delivery as a black box.
- Revoke access promptly at the end of an engagement and confirm return or destruction of any organisational information the vendor held.

**Evidence an assessor would want to see:**
- Contracts/SOWs with security clauses for outsourced development.
- Due-diligence/vetting records for development vendors.
- Access provisioning and de-provisioning records for contractor accounts.
- Evidence that outsourced code passed the same review and testing gates as internal code.

### A.8.31 Separation of development, test and production environments

**What it requires:** Development, testing, and production environments should be kept separate and independently secured, so changes cannot be made against or tested directly on live systems.

**Implementation guidance:**
- Maintain distinct development, test/staging, and production environments with separate access controls and credentials, and separate infrastructure where practical.
- Restrict production access to a defined, limited set of authorised roles, distinct from broader development-environment access.
- Prevent direct developer deployment to production; require changes to pass through pipeline stages with defined promotion gates.
- Use synthetic or de-identified data in non-production environments rather than copies of live production data, unless a documented and approved exception exists.
- Where continuous delivery is used, control exposure of new functionality through techniques such as feature flagging or API versioning, so code can ship without being activated for all users immediately.
- Log and monitor production access separately from non-production access, and alert on unexpected patterns.

**Evidence an assessor would want to see:**
- Environment architecture documentation showing the separation.
- Access control lists/role definitions confirming restricted production access.
- Pipeline configuration showing promotion gates between environments.
- Data handling records confirming production data isn't freely copied into lower environments, or documented exceptions where it is.

### A.8.32 Change management

**What it requires:** Changes to information systems and processing facilities should follow a formal, controlled process so they are planned, reviewed, approved, and implemented without unintended impact.

**Implementation guidance:**
- Define a change process covering request, risk/impact assessment, approval, testing, implementation, and post-implementation review.
- Classify changes by risk (e.g. standard/pre-approved, normal, emergency) and apply a proportionate level of review and approval to each category.
- Require documented approval from an accountable owner before implementation; review emergency changes retrospectively as soon as practical afterward.
- Test changes in a non-production environment first, and for business-critical systems confirm there's no adverse impact on security or operations before release.
- Keep a change record (what changed, who approved it, when it went live, rollback plan) detailed enough to reconstruct history during an incident or audit.
- Define and periodically rehearse rollback/backout procedures for changes that could affect availability or security.

**Evidence an assessor would want to see:**
- The documented change management process, distinguishing standard/pre-approved, normal, and emergency changes.
- A sample of merge/pull-request records or change tickets showing risk assessment, an independent approver, CI/CD pipeline test-gate results, and a documented rollback procedure.
- Records of emergency changes and their retrospective review.
- A change log/register covering a representative period.

### A.8.33 Test information

**What it requires:** Information used for testing should be selected, protected, and managed carefully so testing doesn't expose sensitive data or compromise data integrity.

**Implementation guidance:**
- Prefer synthetic or anonymised/de-identified data for testing; where realistic production-derived data is genuinely needed, mask or anonymise it before it leaves the production environment.
- Apply the same access controls and handling requirements to test data as to its production equivalent whenever realistic data is used.
- Define and document acceptance criteria for new systems, upgrades, and new versions, including what test data is required to validate them.
- Securely delete test data and any copies once a test cycle is complete rather than leaving it to accumulate in test environments.
- Restrict and log who can copy data from production into test or development environments.
- Periodically review test environments for stale or improperly retained sensitive data.

**Evidence an assessor would want to see:**
- A test data handling/management procedure.
- Evidence of anonymisation or masking applied to production-derived test data.
- Acceptance criteria documentation for recent releases.
- Records of test data clean-up after test cycles.

### A.8.34 Protection of information systems during audit testing

**What it requires:** Audit or assurance activities that touch live operational systems (such as penetration testing) should be planned and agreed with the relevant system owners in advance to avoid disrupting the business.

**Implementation guidance:**
- Require any audit, penetration test, or assurance activity touching production systems to be scoped and scheduled in advance with the relevant system or business owner.
- Agree the testing window, methods, and boundaries in writing before testing starts, including any systems or actions explicitly excluded due to fragility or criticality.
- Ensure appropriate technical and management contacts are available during the testing window, with an agreed escalation or stop procedure if something goes wrong.
- Confirm systems are in a recoverable state (e.g. current backups) before testing begins, particularly for destructive test types.
- Log and monitor testing activity separately so it can be distinguished from genuine security incidents during and after the exercise.
- Review findings with relevant stakeholders and track remediation the same way other risk-treatment actions are tracked.

**Evidence an assessor would want to see:**
- Signed-off test/audit plans showing scope, timing, and agreed boundaries.
- Communication records confirming management agreement before testing occurred.
- Evidence of monitoring/logging during the test window.
- Remediation tracking for findings from prior audit or testing activities.

---

## Adapt this to your context

- This is the theme where "prototype/proof-of-concept" carve-outs (A.8.25) matter most in practice: a young engineering team building fast needs a bounded, honest exception path for exploratory work, not a rule everyone quietly ignores.
- Several controls here (A.8.20 to A.8.23, network security) assume meaningful control over network architecture. A team running entirely on managed SaaS and a cloud provider's own network primitives should point to that provider's shared-responsibility documentation rather than trying to independently prove network segregation it doesn't directly control.
- The cryptography standard (A.8.24) should be reviewed against current guidance periodically: algorithm and key-length recommendations move over time, and a standard frozen at the point it was written will eventually recommend something outdated.
- Where a control clearly doesn't apply (e.g. A.8.30 Outsourced development, if the organisation never uses external developers), say so explicitly and record the reasoning in your Statement of Applicability rather than deleting the row; see the [SoA generator](../soa-generator/) for exactly this workflow.
