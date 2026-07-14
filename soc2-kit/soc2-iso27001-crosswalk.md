---
Artefact type: Reference
Owner role: Information Security Manager
Review cadence: Annual, or when either standard revises
Version: 1.0 (template)
---

# SOC 2 to ISO 27001:2022 crosswalk

> Part of [soc2-kit](README.md#before-you-rely-on-anything-here). Read that disclaimer before relying on this crosswalk. Pairs with the companion [iso27001-controls-kit](../iso27001-controls-kit/).

If you're running both an ISO 27001 ISMS and a SOC 2 report (a common combination for a SaaS company selling into enterprise customers), most of your evidence overlaps. This crosswalk maps each SOC 2 Trust Services Criteria (TSC) common criterion, plus the Additional Criteria for Availability, Confidentiality, Processing Integrity, and Privacy, to the ISO/IEC 27001:2022 Annex A controls (and, where relevant, the ISO 27001 clauses themselves) that typically satisfy it. Use it to avoid building two parallel evidence sets for the same underlying control.

The criterion descriptions below are paraphrased from the AICPA's Trust Services Criteria, not quoted verbatim (the official wording is the AICPA's own copyrighted text). If you need the authoritative criterion text for an actual SOC 2 engagement, get it from the AICPA or your auditor.

## How to use this

- Each row lists one TSC criterion, a plain-language summary of what it asks for, and the ISO 27001:2022 controls (Annex A and, where applicable, the management-system clauses) that most directly address it.
- A single ISO control commonly satisfies several TSC criteria at once (for example, A.6.8 Information security event reporting shows up across the monitoring, incident, and privacy sections). Build your evidence library around the ISO control, then point to it from wherever the TSC crosswalk needs it, rather than duplicating the evidence.
- Where the mapping says "no direct ISO control", that criterion sits outside typical ISO 27001 Annex A scope, most often because it's about a business or contractual practice (fraud consideration, capacity planning, output completeness) rather than an information-security control specifically. You'll still need to evidence it for a SOC 2 report; it just won't come from your ISMS.

## Common criteria

### CC1: Control environment

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC1.1 | The organisation commits to integrity and ethical values, set from the top. | Clause 5 (Leadership); A.5.4 Management responsibilities; A.6.3 Information security awareness, education and training; A.6.4 Disciplinary process |
| CC1.2 | The board demonstrates independence from management and oversees the control system. | Clause 5 (Leadership); A.5.4 Management responsibilities |
| CC1.3 | Management establishes structures, reporting lines, and authority in pursuit of its objectives. | Clause 4 (Context of the organisation); Clause 5 (Leadership); A.5.2 Information security roles and responsibilities; A.5.3 Segregation of duties; A.5.5 Contact with authorities; A.5.6 Contact with special interest groups |
| CC1.4 | The organisation attracts, develops, and retains people competent enough to meet its objectives. | Clause 7 (Support); A.5.1 Policies for information security; A.5.2 Information security roles and responsibilities; A.6.1 Screening; A.6.3 Information security awareness, education and training |
| CC1.5 | Individuals are held accountable for their control responsibilities. | A.5.2 Information security roles and responsibilities; A.6.4 Disciplinary process |

### CC2: Information and communication

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC2.1 | The organisation obtains and uses quality information to support its internal control. | A.5.12 Classification of information; A.5.13 Labelling of information |
| CC2.2 | The organisation communicates control objectives and responsibilities internally. | Clause 7 (Support); A.5.26 Response to information security incidents; A.5.27 Learning from information security incidents; A.5.37 Documented operating procedures; A.6.2 Terms and conditions of employment; A.6.3 Information security awareness, education and training; A.6.5 Responsibilities after termination or change of employment; A.6.8 Information security event reporting; A.8.32 Change management |
| CC2.3 | The organisation communicates with external parties about matters affecting its internal control. | Clause 7 (Support); A.5.21 Managing information security in the ICT supply chain; A.6.2 Terms and conditions of employment; A.6.6 Confidentiality or non-disclosure agreements; A.6.8 Information security event reporting |

### CC3: Risk assessment

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC3.1 | Objectives are specified clearly enough to allow risk identification and assessment. | Clause 6 (Planning); Clause 7 (Support); Clause 9 (Performance evaluation); A.5.31 Legal, statutory, regulatory and contractual requirements; A.5.32 Intellectual property rights |
| CC3.2 | Risks to objectives are identified across the organisation and analysed. | Clause 6 (Planning); A.5.12 Classification of information; A.5.19 Information security in supplier relationships; A.5.20 Addressing information security within supplier agreements; A.5.21 Managing information security in the ICT supply chain |
| CC3.3 | The organisation considers the potential for fraud when assessing risk. | Clause 6 (Planning); no dedicated ISO Annex A control (a business-integrity consideration, not an information-security control) |
| CC3.4 | Changes that could significantly affect internal control are identified and assessed. | Clause 6 (Planning); A.8.32 Change management |

### CC4: Monitoring activities

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC4.1 | The organisation runs ongoing or separate evaluations to confirm controls are present and functioning. | Clause 7 (Support); Clause 9 (Performance evaluation); Clause 10 (Improvement); A.5.35 Independent review of information security; A.5.36 Compliance with policies, rules and standards for information security |
| CC4.2 | Control deficiencies are evaluated and communicated to the people responsible for fixing them. | Clause 9 (Performance evaluation); Clause 10 (Improvement); A.5.22 Monitoring, review and change management of supplier services; A.5.36 Compliance with policies, rules and standards for information security; A.6.8 Information security event reporting |

### CC5: Control activities

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC5.1 | The organisation selects and develops controls that mitigate risk to an acceptable level. | Clause 6 (Planning); A.5.3 Segregation of duties |
| CC5.2 | The organisation develops general technology controls to support its objectives. | Clause 6 (Planning); Clause 8 (Operation) |
| CC5.3 | Controls are deployed through policies that set expectations and procedures that put them into practice. | Clause 5 (Leadership); Clause 7 (Support); Clause 10 (Improvement); A.5.1 Policies for information security; A.6.3 Information security awareness, education and training |

### CC6: Logical and physical access controls

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC6.1 | Logical access software, infrastructure, and architecture protect information assets. | A.5.9 Inventory of information and other associated assets; A.5.15 Access control; A.5.17 Authentication information; A.5.18 Access rights; A.5.31 Legal, statutory, regulatory and contractual requirements; A.8.2 Privileged access rights; A.8.3 Information access restriction; A.8.5 Secure authentication; A.8.24 Use of cryptography |
| CC6.2 | New users are registered and authorised before credentials are issued; access is removed when no longer authorised. | A.5.16 Identity management; A.5.18 Access rights |
| CC6.3 | Access is authorised, modified, or removed based on role, least privilege, and segregation of duties. | A.5.3 Segregation of duties; A.5.18 Access rights; A.8.2 Privileged access rights |
| CC6.4 | Physical access to facilities and protected assets is restricted to authorised personnel. | A.5.11 Return of assets; A.5.18 Access rights; A.7.1 Physical security perimeters; A.7.2 Physical entry; A.7.3 Securing offices, rooms and facilities; A.7.6 Working in secure areas; A.7.7 Clear desk and clear screen; A.7.8 Equipment siting and protection; A.7.9 Security of assets off-premises; A.7.12 Cabling security |
| CC6.5 | Physical and logical protections over retired assets are discontinued only once data recovery from them is no longer possible or needed. | A.5.11 Return of assets; A.7.1, A.7.2, A.7.3, A.7.6, A.7.8, A.7.9, A.7.12, A.7.14 (physical controls theme, disposal-focused); A.8.10 Information deletion |
| CC6.6 | Logical access controls protect against threats originating outside the system boundary. | A.8.2 Privileged access rights; A.8.21 Security of network services; A.8.22 Segregation of networks |
| CC6.7 | Transmission, movement, and removal of information is restricted to authorised users and protected in transit. | A.5.14 Information transfer; A.7.10 Storage media; A.7.14 Secure disposal or re-use of equipment; A.8.1 User endpoint devices; A.8.21 Security of network services; A.8.24 Use of cryptography; A.8.26 Application security requirements |
| CC6.8 | Controls prevent, detect, and act on unauthorised or malicious software. | A.8.7 Protection against malware; A.8.19 Installation of software on operational systems; A.8.31 Separation of development, test and production environments; A.8.32 Change management |

### CC7: System operations

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC7.1 | Detection and monitoring identify new vulnerabilities and configuration changes that introduce them. | Clause 9 (Performance evaluation); A.8.8 Management of technical vulnerabilities |
| CC7.2 | System components are monitored for anomalies indicating malicious activity, disaster, or error. | A.6.8 Information security event reporting; A.8.15 Logging |
| CC7.3 | Security events are evaluated to determine whether they represent an incident, and action is taken if so. | Clause 7 (Support); A.5.24 Information security incident management planning and preparation; A.5.25 Assessment and decision on information security events; A.5.26 Response to information security incidents; A.6.8 Information security event reporting |
| CC7.4 | The organisation runs a defined incident response programme to understand, contain, remediate, and communicate incidents. | Clause 7 (Support); Clause 10 (Improvement); A.5.24, A.5.25, A.5.26; A.6.8 Information security event reporting |
| CC7.5 | The organisation recovers from identified security incidents. | Clause 7 (Support); Clause 10 (Improvement); A.5.25, A.5.26, A.5.27; A.5.29 Information security during disruption |

### CC8: Change management

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC8.1 | Changes to infrastructure, data, software, and procedures are authorised, tested, approved, and implemented in a controlled way. | Clause 7 (Support); Clause 8 (Operation); A.5.8 Information security in project management; A.5.34 Privacy and protection of PII; A.6.6 Confidentiality or non-disclosure agreements; A.8.19, A.8.25, A.8.27, A.8.29, A.8.30, A.8.31, A.8.32, A.8.33 |

### CC9: Risk mitigation

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| CC9.1 | The organisation identifies and develops risk mitigation activities for business-disruption risks. | A.5.30 ICT readiness for business continuity |
| CC9.2 | The organisation assesses and manages risks associated with vendors and business partners. | A.5.19, A.5.20, A.5.21, A.5.22 (supplier relationship controls); A.5.36 Compliance with policies, rules and standards for information security; A.6.6 Confidentiality or non-disclosure agreements |

## Additional criteria

### A1: Availability

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| A1.1 | Processing capacity is maintained, monitored, and evaluated against demand. | A.8.6 Capacity management |
| A1.2 | Environmental protections, backup, and recovery infrastructure are authorised, implemented, and monitored. | Clause 7 (Support); A.5.29 Information security during disruption; A.7.5 Protecting against physical and environmental threats; A.7.13 Equipment maintenance; A.8.13 Information backup; A.8.14 Redundancy of information processing facilities |
| A1.3 | Recovery plan procedures are tested. | A.5.29 Information security during disruption; A.8.13 Information backup |

### C1: Confidentiality

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| C1.1 | Confidential information is identified and maintained. | Clause 7 (Support); A.5.31 Legal, statutory, regulatory and contractual requirements |
| C1.2 | Confidential information is disposed of appropriately. | Clause 7 (Support); A.5.31 Legal, statutory, regulatory and contractual requirements; A.8.10 Information deletion; A.7.14 Secure disposal or re-use of equipment |

### PI1: Processing integrity

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| PI1.1 | Quality information about processing objectives, data definitions, and specifications is obtained and communicated. | A.5.12 Classification of information; A.5.13 Labelling of information |
| PI1.2 | Policies and procedures over system inputs ensure completeness and accuracy. | No dedicated ISO Annex A control; usually evidenced through your software development lifecycle and QA process instead |
| PI1.3 | Policies and procedures over system processing meet the entity's objectives. | No dedicated ISO Annex A control; same as above |
| PI1.4 | Output is delivered completely, accurately, and on time per specification. | No dedicated ISO Annex A control; same as above |
| PI1.5 | Inputs, in-process items, and outputs are stored completely, accurately, and on time. | A.8.13 Information backup |

### Privacy criteria (P1 to P8)

Including the Privacy category in a SOC 2 report is a management election, whether you're a data controller (you decide why and how personal information is processed) or a data processor acting solely on a customer's instructions. If you do elect it as a processor, most of the individual privacy criteria are typically marked not applicable, with the rationale documented in your system description instead of a control response. Where privacy criteria are in scope:

| Criterion | What it asks | Mapped ISO 27001:2022 controls |
|---|---|---|
| P1.1 | Notice is given to data subjects about privacy practices. | Typically excluded for a data processor; see above |
| P2.1 | Choices about collection, use, retention, and disclosure are communicated to data subjects. | Typically excluded for a data processor; see above |
| P3.1 | Personal information is collected consistent with privacy objectives. | A.5.34 Privacy and protection of PII |
| P3.2 | Explicit consent is obtained before collecting information that requires it. | Typically excluded for a data processor; see above |
| P4.1 | Use of personal information is limited to identified purposes. | Clause 7 (Support); A.5.34 Privacy and protection of PII |
| P4.2 | Personal information is retained consistent with privacy objectives. | Clause 7 (Support); A.5.34 Privacy and protection of PII; A.8.13 Information backup |
| P4.3 | Personal information is securely disposed of. | Clause 7 (Support); A.8.10 Information deletion; A.7.10 Storage media; A.7.14 Secure disposal or re-use of equipment |
| P5.1 | Data subjects can access their stored personal information. | Clause 7 (Support); A.5.34 Privacy and protection of PII; A.8.5 Secure authentication |
| P5.2 | Data subjects can have their information corrected, amended, or appended. | Clause 7 (Support); A.5.34 Privacy and protection of PII |
| P6.1 | Personal information is disclosed to third parties only with explicit consent. | Clause 5 (Leadership); Clause 6 (Planning) |
| P6.2 | A record of authorised disclosures is created and retained. | No dedicated ISO Annex A control; usually evidenced through your data processing records |
| P6.3 | A record of detected or reported unauthorised disclosures is created and retained. | No dedicated ISO Annex A control; usually evidenced through your incident register |
| P6.4 | Privacy commitments are obtained from vendors and third parties with access to personal information. | Clause 10 (Improvement); A.6.6 Confidentiality or non-disclosure agreements |
| P6.5 | Vendors and third parties commit to notifying the organisation of actual or suspected unauthorised disclosures. | Clause 10 (Improvement); A.5.20 Addressing information security within supplier agreements; A.6.8 Information security event reporting |
| P6.6 | Affected data subjects, regulators, and others are notified of breaches. | Clause 10 (Improvement); A.6.8 Information security event reporting |
| P6.7 | Data subjects can get an accounting of the personal information held about them. | A.5.12 Classification of information |
| P7.1 | Personal information collected and maintained is accurate, complete, and up to date. | No dedicated ISO Annex A control; usually evidenced through your data quality process |
| P8.1 | Inquiries, complaints, and disputes from data subjects are received, addressed, and resolved, with periodic compliance monitoring. | Clause 9 (Performance evaluation); A.5.35 Independent review of information security; A.5.36 Compliance with policies, rules and standards for information security |

## Adapt this to your context

- This crosswalk assumes ISO 27001:2022 (the 93-control, four-theme Annex A). If you're still certified against the 2013 edition, the control numbers won't match; re-derive the mapping against your actual Annex A version.
- Several criteria above have "no dedicated ISO Annex A control" because they're about business or product quality practices (fraud consideration, output completeness, data quality) rather than information security specifically. Don't force these into your ISMS; evidence them from wherever they naturally live (QA process, data governance process, etc.).
- If you're not pursuing the Privacy criteria at all (the common case for a B2B data processor), you can drop that whole section from your own crosswalk and just record the exclusion rationale once, in your system description.
- Treat the "Mapped ISO 27001:2022 controls" column as a starting point for your own evidence library, not a substitute for reading each control's actual requirement yourself; a control can satisfy a criterion only if it's genuinely implemented, not just cited.

**Frameworks referenced**: AICPA Trust Services Criteria (SOC 2), ISO/IEC 27001:2022 Annex A
