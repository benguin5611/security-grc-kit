---
Artefact type: Reference
Owner role: Information Security Manager
Review cadence: Annual, or when either standard revises
Version: 3.0
---

# SOC 2 to ISO 27001:2022 crosswalk

> Part of [soc2-kit](README.md#before-you-rely-on-anything-here). Read that disclaimer before relying on this crosswalk. Pairs with the companion [iso27001-controls-kit](../iso27001-controls-kit/).

If you run both an ISO 27001 ISMS and a SOC 2 report (a common combination for a SaaS company selling into enterprise customers), most of your evidence overlaps. This crosswalk maps SOC 2 to ISO/IEC 27001:2022 so you can build one evidence library instead of two.

It maps at the level of **points of focus**, not just the criterion. Each Trust Services criterion is made up of several points of focus, and in practice you write one or more control activities against each point of focus. So the point of focus, not the criterion heading, is the unit that actually lines up with an ISO control. Each row below takes one point of focus, names the ISO 27001:2022 control or management-system clause that satisfies it, and the "Why it maps" line under each criterion explains the logic rather than leaving you to infer it from a control number.

The point-of-focus summaries are short paraphrases of what each one asks for (the AICPA's wording is copyrighted; get the authoritative text from the AICPA or your auditor). The ISO control names are the 2022 Annex A names.

## How to read this

- **Point of focus**: a plain-language paraphrase of one sub-requirement of the criterion.
- **ISO 27001:2022 mapping**: the Annex A control(s) or clause(s) whose purpose covers that point of focus. Where a requirement lives in the management system rather than a control (planning, resourcing, review), the clause is cited; the AICPA's CC-series leans on the COSO principles, and those map more naturally to clauses than to Annex A controls.
- A control recurs across many points of focus. Build the evidence once and cite it wherever it appears.
- "No direct Annex A control" means the point of focus is a business or product-quality practice (fraud consideration, output completeness, data quality), not an information-security control. You still evidence it for SOC 2; it comes from QA, data governance, or finance, not the ISMS.
- The mapping uses the full 2022 Annex A, including the eleven controls new in the 2022 revision (A.5.7 threat intelligence, A.5.23 cloud services, A.5.30 ICT readiness, A.7.4 physical security monitoring, A.8.9 configuration management, A.8.10 information deletion, A.8.11 data masking, A.8.12 data leakage prevention, A.8.16 monitoring activities, A.8.23 web filtering, A.8.28 secure coding), several of which are the most direct fit for the point of focus they sit under.

---

## Common criteria

### CC1.1: Integrity and ethical values

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Sets the tone at the top for integrity and ethics | Clause 5.1 Leadership and commitment; A.5.4 Management responsibilities |
| Establishes standards of conduct | A.5.1 Policies for information security; A.6.2 Terms and conditions of employment |
| Evaluates adherence to standards | A.5.36 Compliance with policies, rules and standards for information security |
| Addresses departures from standards | A.6.4 Disciplinary process |

**Why it maps:** ethics and conduct in an ISMS are carried by leadership commitment (Clause 5) and the policy set (A.5.1), made binding through employment terms (A.6.2), and enforced by compliance checks (A.5.36) and the disciplinary process (A.6.4).

### CC1.2: Board oversight and independence

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Establishes oversight responsibilities separate from management | Clause 5.1 Leadership and commitment; A.5.4 Management responsibilities |
| Applies relevant expertise to oversight | Clause 7.2 Competence |
| Operates independently and objectively reviews management | Clause 9.3 Management review; A.5.35 Independent review of information security |

**Why it maps:** ISO gives oversight two homes: the periodic management review (Clause 9.3) where top management scrutinises the ISMS, and the independent review (A.5.35) that provides objectivity the management line cannot.

### CC1.3: Structures, reporting lines, and authority

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Considers the organisational structure | Clause 5.1 Leadership and commitment; Clause 4 Context of the organisation |
| Establishes reporting lines | A.5.2 Information security roles and responsibilities |
| Defines authorities and responsibilities | A.5.2 Information security roles and responsibilities; A.5.4 Management responsibilities |
| Segregates incompatible duties | A.5.3 Segregation of duties |

**Why it maps:** A.5.2 is the direct control for assigning roles and reporting lines; A.5.3 handles the conflicting-duty part of "authority" that CC1.3 calls out.

### CC1.4: Competence

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Establishes competence expectations | Clause 7.2 Competence |
| Attracts, develops, and retains capable people | Clause 7.2 Competence; A.6.3 Information security awareness, education and training |
| Screens candidates for suitability | A.6.1 Screening |
| Plans for succession and role change | A.6.5 Responsibilities after termination or change of employment |

**Why it maps:** Clause 7.2 is the management-system requirement for competence; A.6.1 and A.6.3 are the hiring-and-training controls that deliver it; A.6.5 covers the continuity CC1.4 expects when people move.

### CC1.5: Accountability

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Enforces accountability through structures and authorities | A.5.2 Information security roles and responsibilities; A.5.4 Management responsibilities |
| Establishes performance measures and expectations | A.5.1 Policies for information security; A.6.2 Terms and conditions of employment |
| Acts on performance, including corrective action | A.6.4 Disciplinary process |

**Why it maps:** accountability is roles plus consequence: A.5.2/A.5.4 fix who is responsible, A.6.2 makes it a condition of employment, and A.6.4 is the mechanism for acting when responsibilities are not met.

## CC2: Communication and information

### CC2.1: Quality information

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies the information needed to run internal control | A.5.37 Documented operating procedures |
| Captures internal and external sources of data | A.8.15 Logging; A.8.16 Monitoring activities |
| Produces information that is timely and reliable | A.8.16 Monitoring activities; A.8.17 Clock synchronization |

**Why it maps:** the point of focus here is operational information quality, which in an ISMS comes from logging (A.8.15), monitoring (A.8.16), and reliable timestamps (A.8.17) documented and made usable through operating procedures (A.5.37). This is deliberately not classification (A.5.12): CC2.1 is about information that runs the control system, not about rating data sensitivity.

### CC2.2: Internal communication

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Communicates internal-control objectives and responsibilities | Clause 7.4 Communication; A.5.1 Policies for information security |
| Builds awareness of security duties | Clause 7.3 Awareness; A.6.3 Information security awareness, education and training |
| Provides a channel to raise security matters | A.6.8 Information security event reporting |

**Why it maps:** Clause 7.3/7.4 are the ISMS communication requirements; A.6.3 delivers awareness; A.6.8 is the specific reporting channel CC2.2's "separate lines of communication" point of focus calls for.

### CC2.3: External communication

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Communicates with external parties on control matters | Clause 7.4 Communication; A.5.20 Addressing information security within supplier agreements |
| Communicates with authorities and interest groups | A.5.5 Contact with authorities; A.5.6 Contact with special interest groups |
| Binds external parties to confidentiality | A.6.6 Confidentiality or non-disclosure agreements |

**Why it maps:** external communication in ISO splits into supplier channels (A.5.20), authority and peer channels (A.5.5, A.5.6), and the confidentiality that governs what can be shared (A.6.6).

## CC3: Risk assessment

### CC3.1: Objectives clear enough to assess risk against

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Specifies objectives with enough clarity to identify risk | Clause 6.2 Information security objectives |
| Considers tolerances for risk | Clause 6.1.2 Information security risk assessment |
| Includes compliance and reporting objectives | A.5.31 Legal, statutory, regulatory and contractual requirements |

**Why it maps:** ISO requires documented objectives (Clause 6.2) and risk criteria/tolerances (Clause 6.1.2); A.5.31 anchors the compliance objectives CC3.1 references.

### CC3.2: Identify and analyse risk

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies risks across the organisation | Clause 6.1.2 Information security risk assessment; A.5.9 Inventory of information and other associated assets |
| Analyses internal and external threat factors | A.5.7 Threat intelligence |
| Includes supplier and cloud risk | A.5.19 Information security in supplier relationships; A.5.23 Information security for use of cloud services |
| Estimates likelihood and impact and decides responses | Clause 6.1.2; Clause 6.1.3 Information security risk treatment |

**Why it maps:** risk identification runs off the asset inventory (A.5.9) and, new in 2022, threat intelligence (A.5.7) as the external-factor input; supplier and cloud risk (A.5.19, A.5.23) are the parts of "across the organisation" a SaaS most often misses.

### CC3.3: Fraud risk

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Considers fraud types, incentives, opportunities, and rationalisations | Clause 6.1.2 Information security risk assessment. No direct Annex A control: fraud consideration is a business-integrity input to the risk assessment, not a security control. |

**Why it maps:** ISO absorbs fraud only as a factor inside the risk assessment; there is no Annex A control for it, so evidence it as an input to Clause 6.1.2 and from your wider governance.

### CC3.4: Identify and assess change

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Assesses changes in the external environment | Clause 6.1.2 Information security risk assessment |
| Assesses changes in business model and leadership | Clause 6.3 Planning of changes |
| Assesses changes to systems | A.8.9 Configuration management; A.8.32 Change management |

**Why it maps:** CC3.4 spans organisational change (Clause 6.3) and system change; A.8.9 and A.8.32 are the controls that detect and govern the technical side.

## CC4: Monitoring activities

### CC4.1: Ongoing and separate evaluations

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Runs a mix of ongoing and separate evaluations | Clause 9.1 Monitoring, measurement, analysis and evaluation; A.8.16 Monitoring activities |
| Uses objective evaluators | Clause 9.2 Internal audit; A.5.35 Independent review of information security |
| Confirms controls are present and functioning | A.5.36 Compliance with policies, rules and standards for information security |

**Why it maps:** ongoing evaluation is continuous monitoring (Clause 9.1, A.8.16); separate evaluation is internal audit and independent review (Clause 9.2, A.5.35); A.5.36 is the compliance check that a control is actually operating.

### CC4.2: Evaluate and communicate deficiencies

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Assesses the results of evaluations | Clause 9.3 Management review |
| Communicates deficiencies to those who can act | A.6.8 Information security event reporting; A.5.36 Compliance with policies, rules and standards for information security |
| Monitors that corrective action is taken | Clause 10.1 Nonconformity and corrective action |

**Why it maps:** ISO's nonconformity and corrective-action loop (Clause 10.1) plus management review (Clause 9.3) is exactly CC4.2's evaluate-communicate-remediate cycle.

## CC5: Control activities

### CC5.1: Select and develop control activities

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Integrates control selection with the risk assessment | Clause 6.1.3 Information security risk treatment |
| Considers entity-specific factors and where controls apply | Clause 8.1 Operational planning and control |
| Selects a mix of control types | A.5.1 Policies for information security; A.5.3 Segregation of duties |

**Why it maps:** in ISO, selecting controls to treat risk is the risk-treatment step (Clause 6.1.3) feeding the Statement of Applicability; the SoA generator in the companion kit produces the evidence for this criterion directly.

### CC5.2: Technology general controls

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Determines the dependency between business processes and technology | A.8.9 Configuration management |
| Establishes access-security control activities over technology | A.8.2 Privileged access rights; A.8.5 Secure authentication |
| Establishes technology acquisition, development, and maintenance controls | A.8.19 Installation of software on operational systems; A.8.31 Separation of development, test and production environments; A.8.32 Change management |
| Establishes control activities over technology infrastructure | A.8.15 Logging; A.8.16 Monitoring activities |

**Why it maps:** CC5.2 is the IT general controls criterion, so it maps to the technological controls that constitute ITGCs: configuration (A.8.9), privileged access and authentication (A.8.2, A.8.5), change and environment separation (A.8.32, A.8.31, A.8.19), and infrastructure logging and monitoring (A.8.15, A.8.16). A mapping that answers this criterion with only management-system clauses has not really answered it.

### CC5.3: Deploy through policies and procedures

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Establishes policies that set expectations | Clause 5.2 Policy; A.5.1 Policies for information security |
| Puts policies into action through procedures | A.5.37 Documented operating procedures |
| Uses competent people and reassesses over time | A.6.3 Information security awareness, education and training |

**Why it maps:** the policy-to-procedure chain is A.5.1 (policy) to A.5.37 (operating procedures), set at the top by Clause 5.2.

## CC6: Logical and physical access controls

### CC6.1: Logical access protections

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies and manages the inventory of information assets | A.5.9 Inventory of information and other associated assets |
| Restricts logical access by an access-control policy | A.5.15 Access control; A.8.3 Information access restriction |
| Identifies and authenticates users | A.5.16 Identity management; A.5.17 Authentication information; A.8.5 Secure authentication |
| Manages secure configuration of access points | A.8.9 Configuration management |
| Protects encryption keys and encrypts data | A.8.24 Use of cryptography |

**Why it maps:** CC6.1's points of focus split cleanly across the ISO access family (A.5.15, A.8.3), the identity and authentication controls (A.5.16, A.5.17, A.8.5), and cryptography (A.8.24), with the asset inventory (A.5.9) as the thing access is being restricted to.

### CC6.2: Registration and authorisation

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Registers and authorises users before granting access | A.5.16 Identity management; A.5.18 Access rights |
| Removes access when no longer required | A.5.18 Access rights; A.6.5 Responsibilities after termination or change of employment |
| Reviews access periodically | A.5.18 Access rights |

**Why it maps:** the joiner-mover-leaver lifecycle CC6.2 describes is A.5.16 (identity) plus A.5.18 (granting, reviewing, and revoking rights), with A.6.5 covering the leaver trigger.

### CC6.3: Role-based access and segregation of duties

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Grants, modifies, and removes access by role and least privilege | A.5.15 Access control; A.5.18 Access rights |
| Considers segregation of incompatible duties | A.5.3 Segregation of duties |
| Restricts and monitors privileged access | A.8.2 Privileged access rights; A.8.18 Use of privileged utility programs |

**Why it maps:** CC6.3 adds least privilege and SoD on top of CC6.2, so it pulls in A.5.3 (SoD) and the privileged-access controls (A.8.2, A.8.18) specifically.

### CC6.4: Physical access

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Restricts physical access to facilities | A.7.1 Physical security perimeters; A.7.2 Physical entry |
| Protects secure areas and equipment locations | A.7.3 Securing offices, rooms and facilities |
| Monitors physical access | A.7.4 Physical security monitoring |

**Why it maps:** the physical family A.7.1 to A.7.4 is a direct fit; A.7.4 (physical security monitoring, new in 2022) is the point of focus about detecting unauthorised physical access that a 2013-era mapping has no control for.

### CC6.5: Disposal of data on retired assets

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies data and software for disposal | A.7.10 Storage media |
| Renders data unrecoverable before disposal or re-use | A.7.14 Secure disposal or re-use of equipment; A.8.10 Information deletion |

**Why it maps:** CC6.5 is specifically about disposal, so it maps to media handling (A.7.10), secure equipment disposal (A.7.14), and, new in 2022, logical information deletion (A.8.10), not to the whole physical family.

### CC6.6: Threats from outside the boundary

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Restricts and protects access across the system boundary | A.8.20 Networks security; A.8.22 Segregation of networks |
| Secures network services at the perimeter | A.8.21 Security of network services |
| Filters outbound access to malicious destinations | A.8.23 Web filtering |
| Protects credentials and data crossing the boundary | A.8.24 Use of cryptography |

**Why it maps:** boundary protection is the network family (A.8.20 to A.8.22), with web filtering (A.8.23, new in 2022) for the outbound-threat point of focus and cryptography (A.8.24) protecting what crosses.

### CC6.7: Transmission, movement, and removal of information

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Restricts transmission and movement to authorised users | A.5.14 Information transfer |
| Protects information on removable and endpoint media | A.7.10 Storage media; A.8.1 User endpoint devices |
| Prevents unauthorised removal or exfiltration | A.8.12 Data leakage prevention |
| Protects information in transit | A.8.24 Use of cryptography |

**Why it maps:** CC6.7's "removal" point of focus is where A.8.12 (data leakage prevention, new in 2022) belongs; transfer (A.5.14), media and endpoints (A.7.10, A.8.1), and encryption in transit (A.8.24) cover the rest.

### CC6.8: Unauthorised or malicious software

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Detects and acts on malicious software | A.8.7 Protection against malware |
| Restricts software installation | A.8.19 Installation of software on operational systems |
| Reduces exposure to malicious content | A.8.23 Web filtering |
| Keeps untrusted code out of production | A.8.31 Separation of development, test and production environments |

**Why it maps:** malware defence is A.8.7 layered with installation control (A.8.19), web filtering (A.8.23), and environment separation (A.8.31) to keep the delivery paths closed.

## CC7: System operations

### CC7.1: Detect vulnerabilities and unauthorised change

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Defines and maintains configuration standards | A.8.9 Configuration management |
| Detects changes and unauthorised components | A.8.16 Monitoring activities |
| Draws on threat information | A.5.7 Threat intelligence |
| Scans for and manages vulnerabilities | A.8.8 Management of technical vulnerabilities |

**Why it maps:** all three of the 2022-relevant controls land here: configuration baselines (A.8.9), monitoring for drift (A.8.16), and threat intelligence (A.5.7), alongside the long-standing vulnerability control (A.8.8). This is the criterion the previous version of this crosswalk under-served most.

### CC7.2: Monitor for anomalies

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Monitors infrastructure and software for anomalies | A.8.16 Monitoring activities |
| Records activity for analysis | A.8.15 Logging |
| Correlates events on a reliable timeline | A.8.17 Clock synchronization |
| Enables people to report observed events | A.6.8 Information security event reporting |

**Why it maps:** A.8.16 (monitoring activities, new in 2022) is the direct control for anomaly detection; logging (A.8.15) and clock synchronisation (A.8.17) make the detection analysable, and A.6.8 adds the human reporting path.

### CC7.3: Evaluate security events

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Assesses events to decide whether they are incidents | A.5.25 Assessment and decision on information security events |
| Responds when an event is an incident | A.5.26 Response to information security incidents |
| Draws on reported events | A.6.8 Information security event reporting |

**Why it maps:** A.5.25 is the exact control for the triage point of focus (event to incident decision); A.5.26 and A.6.8 supply the response and the input.

### CC7.4: Respond to incidents

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Assigns roles and prepares to respond | A.5.24 Information security incident management planning and preparation |
| Contains, remediates, and ends incidents | A.5.26 Response to information security incidents |
| Preserves evidence | A.5.28 Collection of evidence |
| Feeds corrective action | Clause 10.1 Nonconformity and corrective action |

**Why it maps:** the incident-management family A.5.24 to A.5.28 is a direct fit; A.5.28 (evidence) is the point of focus about forensic handling that generic mappings drop, and Clause 10.1 closes the corrective-action loop.

### CC7.5: Recover from incidents

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Restores operations after an incident | A.5.29 Information security during disruption; A.8.13 Information backup |
| Ensures technology can meet recovery objectives | A.5.30 ICT readiness for business continuity; A.8.14 Redundancy of information processing facilities |
| Applies lessons learned | A.5.27 Learning from information security incidents |

**Why it maps:** recovery pulls in continuity (A.5.29), the 2022 ICT-readiness control (A.5.30), and the technical means of recovery (A.8.13 backup, A.8.14 redundancy), with A.5.27 as the improvement point of focus.

## CC8: Change management

### CC8.1: Change management

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Authorises and governs changes | A.8.32 Change management |
| Considers security in projects and design | A.5.8 Information security in project management; A.8.27 Secure system architecture and engineering principles |
| Designs, develops, and codes securely | A.8.25 Secure development life cycle; A.8.26 Application security requirements; A.8.28 Secure coding |
| Tests changes before deployment | A.8.29 Security testing in development and acceptance; A.8.33 Test information |
| Maintains configuration baselines and separates environments | A.8.9 Configuration management; A.8.31 Separation of development, test and production environments |
| Deploys to production under control | A.8.19 Installation of software on operational systems |

**Why it maps:** CC8.1 is a single criterion that spans the whole secure-change lifecycle, so it maps to the development family A.8.25 to A.8.33 (including A.8.28 secure coding, new in 2022) plus the change, configuration, and deployment controls. NDA and privacy controls do not belong here.

## CC9: Risk mitigation

### CC9.1: Mitigate business-disruption risk

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies and mitigates disruption risks | A.5.29 Information security during disruption; A.5.30 ICT readiness for business continuity |
| Builds resilience into processing | A.8.14 Redundancy of information processing facilities |

**Why it maps:** business-continuity risk maps to the continuity controls (A.5.29, A.5.30) and the redundancy that delivers availability (A.8.14). Insurance, the other CC9.1 point of focus, has no Annex A control and is evidenced from your risk-treatment records.

### CC9.2: Vendor and business-partner risk

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Assesses and manages vendor risk | A.5.19 Information security in supplier relationships |
| Sets security requirements in agreements | A.5.20 Addressing information security within supplier agreements |
| Manages supply-chain and cloud risk | A.5.21 Managing information security in the ICT supply chain; A.5.23 Information security for use of cloud services |
| Monitors vendor service delivery over time | A.5.22 Monitoring, review and change management of supplier services |

**Why it maps:** the supplier family A.5.19 to A.5.22 is a one-to-one fit; A.5.23 (cloud services, new in 2022) is the point of focus for cloud dependencies a SaaS crosswalk cannot leave out.

---

## Additional criteria

### A1: Availability

#### A1.1: Capacity

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Measures current use and sets baselines | A.8.6 Capacity management; A.8.16 Monitoring activities |
| Forecasts average and peak demand | A.8.6 Capacity management; Clause 8.1 Operational planning and control |
| Adds capacity to meet demand | A.8.6 Capacity management; Clause 7.1 Resources |

**Why it maps:** A.8.6 is the direct capacity control, but the point of focus is genuinely split. Measurement leans on monitoring (A.8.16); forecasting and provisioning are management-system activities, so they map to operational planning (Clause 8.1) and the resourcing requirement (Clause 7.1). This is a good example of a criterion where the requirement lives partly in a control and partly in the clauses.

#### A1.2: Environmental protection, backup, and recovery

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Protects against environmental threats | A.7.5 Protecting against physical and environmental threats; A.7.11 Supporting utilities |
| Maintains equipment | A.7.13 Equipment maintenance |
| Backs up data | A.8.13 Information backup |
| Provides recovery infrastructure | A.8.14 Redundancy of information processing facilities; A.5.29 Information security during disruption |

**Why it maps:** the environmental points of focus map to the physical controls (A.7.5, A.7.11, A.7.13); backup and redundancy (A.8.13, A.8.14) are the recovery infrastructure.

#### A1.3: Test recovery

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Tests recovery and continuity procedures | A.5.30 ICT readiness for business continuity; A.5.29 Information security during disruption |
| Confirms backups restore | A.8.13 Information backup |

**Why it maps:** A.5.30 (new in 2022) explicitly requires testing ICT continuity, which is precisely A1.3's point of focus; A.8.13 covers restoration testing.

### C1: Confidentiality

#### C1.1: Identify and protect confidential information

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies and classifies confidential information | A.5.12 Classification of information; A.5.13 Labelling of information |
| Protects confidential information in use | A.8.11 Data masking; A.8.24 Use of cryptography |
| Prevents unauthorised disclosure | A.8.12 Data leakage prevention; A.6.6 Confidentiality or non-disclosure agreements |

**Why it maps:** confidentiality starts with classification (A.5.12, A.5.13), then protects the data with masking (A.8.11) and encryption (A.8.24), and guards against leakage contractually (A.6.6) and technically (A.8.12). A.8.11 and A.8.12, both new in 2022, are the most direct confidentiality controls and were missing from the previous mapping.

#### C1.2: Dispose of confidential information

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Identifies confidential information for disposal | A.5.12 Classification of information |
| Disposes of it so it cannot be recovered | A.7.10 Storage media; A.7.14 Secure disposal or re-use of equipment; A.8.10 Information deletion |

**Why it maps:** disposal maps to media handling and secure disposal (A.7.10, A.7.14) and the 2022 logical-deletion control (A.8.10).

### PI1: Processing integrity

#### PI1.1: Quality information about processing

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Defines data and processing specifications | A.5.12 Classification of information; A.5.13 Labelling of information |
| Documents processing definitions | A.5.37 Documented operating procedures |

**Why it maps:** the data-definition points of focus map to classification and labelling (A.5.12, A.5.13) and documented procedures (A.5.37).

#### PI1.2: Input completeness and accuracy

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Defines and validates input characteristics | A.8.26 Application security requirements |
| Tests input handling | A.8.29 Security testing in development and acceptance |
| Ensures inputs are complete and accurate | No direct Annex A control: input completeness and accuracy is a product-quality control, evidenced through your SDLC and QA. |

**Why it maps:** ISO covers the security of input handling (A.8.26, A.8.29) but not the business correctness of the data, which is a QA matter, so this criterion is only partly an ISMS concern.

#### PI1.3: Processing completeness and accuracy

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Processes data as specified | A.8.9 Configuration management |
| Tests processing | A.8.29 Security testing in development and acceptance |
| Ensures processing is complete and accurate | No direct Annex A control: processing correctness is evidenced through your SDLC and QA. |

**Why it maps:** as with PI1.2, ISO covers the technical controls around processing but not the correctness of the result.

#### PI1.4: Output completeness, accuracy, and timeliness

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Protects and delivers output only to intended recipients | A.5.14 Information transfer; A.8.3 Information access restriction |
| Ensures output is complete, accurate, and on time | No direct Annex A control: output completeness and timeliness is a product-quality and operational matter, evidenced through QA and service monitoring. |

**Why it maps:** ISO protects the confidentiality and integrity of output delivery (A.5.14, A.8.3), but its completeness and timeliness are QA concerns.

#### PI1.5: Storage of inputs, in-process items, and outputs

| Point of focus | ISO 27001:2022 mapping |
|---|---|
| Stores items completely and accurately | A.8.13 Information backup |
| Protects stored and non-production copies | A.8.11 Data masking; A.8.33 Test information |

**Why it maps:** storage integrity maps to backup (A.8.13); where stored data is copied into lower environments, masking (A.8.11) and test-information handling (A.8.33) protect it.

### Privacy criteria (P1 to P8)

Including the Privacy category is a management election. A data processor acting solely on a customer's instructions typically marks most privacy criteria not applicable and records the rationale in the system description rather than a control response (the worked example in [examples/](examples/) shows this). Where privacy criteria are in scope, A.5.34 Privacy and protection of PII is the backbone control and recurs throughout.

| Criterion (point of focus in brief) | ISO 27001:2022 mapping |
|---|---|
| P1.1 Notice of privacy practices | A.5.34 Privacy and protection of PII. Often excluded for a processor. |
| P2.1 Choice and consent communicated | A.5.34 Privacy and protection of PII. Often excluded for a processor. |
| P3.1 Collection consistent with objectives | A.5.34 Privacy and protection of PII |
| P3.2 Explicit consent where required | A.5.34 Privacy and protection of PII. Often excluded for a processor. |
| P4.1 Use limited to identified purposes | A.5.34 Privacy and protection of PII; A.8.3 Information access restriction |
| P4.2 Retention consistent with objectives | A.5.33 Protection of records; A.5.34 Privacy and protection of PII |
| P4.3 Secure disposal when no longer needed | A.5.34 Privacy and protection of PII; A.7.14 Secure disposal or re-use of equipment; A.8.10 Information deletion |
| P5.1 Data-subject access to their information | A.5.34 Privacy and protection of PII; A.8.3 Information access restriction |
| P5.2 Correction and amendment | A.5.34 Privacy and protection of PII |
| P6.1 Disclosure to third parties with consent | A.5.14 Information transfer; A.5.34 Privacy and protection of PII |
| P6.2 Record of authorised disclosures | A.5.33 Protection of records; A.8.15 Logging |
| P6.3 Record of unauthorised disclosures | A.5.28 Collection of evidence; A.8.15 Logging |
| P6.4 Privacy commitments from vendors | A.5.20 Addressing information security within supplier agreements; A.6.6 Confidentiality or non-disclosure agreements |
| P6.5 Vendor breach-notification commitments | A.5.20 Addressing information security within supplier agreements; A.5.22 Monitoring, review and change management of supplier services |
| P6.6 Breach notification to subjects and regulators | A.5.5 Contact with authorities; A.5.26 Response to information security incidents; A.6.8 Information security event reporting |
| P6.7 Accounting of information held and disclosed | A.5.33 Protection of records; A.5.34 Privacy and protection of PII; A.8.15 Logging |
| P7.1 Personal information kept accurate and current | No direct Annex A control: data quality is a data-governance practice evidenced outside the ISMS. |
| P8.1 Handle inquiries, complaints, and disputes, with monitoring | Clause 9.1 Monitoring, measurement, analysis and evaluation; A.5.34 Privacy and protection of PII; A.5.36 Compliance with policies, rules and standards for information security |

**Why it maps:** privacy runs on A.5.34 as the backbone, with retention and records (A.5.33), disclosure and transfer (A.5.14), breach handling (A.5.26, A.6.8, A.5.5), and vendor privacy commitments (A.5.20) attaching to the specific points of focus. Notice, choice, and consent (P1, P2, P3.2) have no security control behind them, which is why a processor usually excludes them.

## Adapt this to your context

- This crosswalk assumes ISO/IEC 27001:2022 (the 93-control, four-theme Annex A). If you are still certified against the 2013 edition, the control numbers will not match, and the 2013 edition has no equivalent for several controls used above; re-derive against your actual Annex A version.
- Map at the point-of-focus level in your own control matrix too. One control activity per point of focus keeps your SOC 2 controls matrix and your ISO Statement of Applicability pointing at the same evidence.
- A point of focus marked "no direct Annex A control" is a business or product-quality practice. Evidence it from where it lives (QA, data governance, finance); do not force it into the ISMS.
- If you are not pursuing the Privacy criteria (the common case for a B2B data processor), drop that section and record the exclusion rationale once, in your system description.
- Treat the mapping as the starting point for your evidence library, not proof of coverage. A control satisfies a point of focus only where it is genuinely implemented and operating, so read each control's requirement (the companion [iso27001-controls-kit](../iso27001-controls-kit/) has per-control guidance) and confirm your implementation before you rely on it.

**Frameworks referenced**: AICPA Trust Services Criteria (SOC 2, TSP section 100), ISO/IEC 27001:2022 Annex A and management-system clauses
