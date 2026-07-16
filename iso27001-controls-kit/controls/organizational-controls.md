# A.5 Organizational controls

The 37 controls governing how the organisation itself is structured, staffed, and directed to run information security: policy, roles, supplier relationships, incident management, business continuity, and compliance.

---

### A.5.1 Policies for information security

**What it requires:** The organisation must define, formally approve, publish, and communicate an information security policy (plus supporting topic-specific policies), and review them on a set schedule and whenever something significant changes.

**Implementation guidance:**
- Maintain one overarching information security policy plus a set of topic-specific policies (access control, acceptable use, cryptography, etc.), each with a named executive approver.
- Publish policies in a single accessible location that all staff and relevant third parties can reach. Don't let versions live in scattered personal drives.
- Require documented acknowledgement (e-signature or training-system completion record) from staff and contractors, tied into onboarding.
- Set a fixed review cadence (e.g., annually) plus a trigger-based review clause for material changes in the business, technology, legal/regulatory landscape, or after a significant incident.
- Version and date-stamp every policy, keep a change log, and formally retire superseded versions instead of silently overwriting them.
- Cross-reference each topic-specific policy back to the master policy and the overall ISMS scope document so the hierarchy is traceable.

**Evidence an assessor would want to see:**
- Current, dated, and approved policy documents with a visible owner/approver.
- Acknowledgement/attestation records showing staff and contractor sign-off, e.g. a screenshot from a security-awareness training platform showing the list of published policies and a sample employee's acknowledgement.
- A policy review log or minutes showing the last review date and the rationale for any changes made.
- Version history demonstrating superseded versions are retained, not deleted.

### A.5.2 Information security roles and responsibilities

**What it requires:** Security-related roles and responsibilities need to be explicitly defined, assigned to named roles, and given the authority and resources to be carried out.

**Implementation guidance:**
- Name an accountable owner for the ISMS overall (e.g., a Head of Information Security or equivalent) with a direct reporting line to leadership.
- Document a RACI (or similar) matrix mapping key security activities (risk management, incident response, access reviews, vendor risk) to specific roles, not just teams.
- Record each role's authority (who can accept risk, who can approve exceptions) and the resources they're entitled to draw on to do the job.
- Embed the security responsibilities of every other role (managers, engineers, HR, procurement) into position descriptions or a responsibilities register, so accountability extends beyond the security team.
- Review the role/responsibility allocation whenever the organisational structure changes materially, and at the standard ISMS review cycle.

**Evidence an assessor would want to see:**
- A documented ISMS roles/responsibilities register or RACI matrix, dated and approved.
- An organisation chart annotated with security responsibilities overlaid on top of it.
- Position descriptions containing explicit security responsibilities.
- Records showing the register was reviewed following an organisational change.

### A.5.3 Segregation of duties

**What it requires:** Conflicting tasks and areas of responsibility should be split across different people so no single individual can both perform and conceal a security-relevant action unchecked.

**Implementation guidance:**
- Map conflict-prone process pairs (requesting vs approving access, developing vs deploying code, initiating vs authorising payments) and assign them to different individuals, or require dual sign-off.
- Where headcount is too small for full segregation, use compensating controls: independent review, audit logging, or mandatory second-person sign-off.
- Build approval gates into workflows and tooling so a single person cannot unilaterally release, withdraw, or modify a sensitive asset (e.g., a production deployment or access grant).
- Turn on activity logging and audit trails for privileged actions so segregation can be verified after the fact.
- Reflect the separation in position descriptions and access provisioning: a role's system permissions should match the duties it's meant to hold, not exceed them.
- Periodically sample high-risk workflows to confirm the segregation actually holds in practice.

**Evidence an assessor would want to see:**
- A documented conflict-of-duties map, or a written statement of segregated duties.
- Position descriptions showing distinct, non-conflicting duties.
- Access-control or workflow configuration showing dual-authorisation gates.
- Audit logs or sampled reviews demonstrating the segregation held up in practice.

### A.5.4 Management responsibilities

**What it requires:** Management must actively require, enable, and check that everyone (employees, contractors, and other personnel) follows the organisation's security policies and procedures.

**Implementation guidance:**
- Brief new employees, contractors, and third parties on their security obligations before granting them access to systems or information, not after.
- Run mandatory security/compliance training with completion tracking, and automatically alert both the individual and their manager when training falls overdue.
- Include security-policy adherence explicitly in onboarding checklists and, where appropriate, in contracts or engagement letters for contractors and third parties.
- Have management periodically audit compliance with key policies and standards (not just review the policy documents themselves), and act on the findings.
- Make policy compliance a visible leadership priority: reference it in team meetings, performance expectations, and management reporting.

**Evidence an assessor would want to see:**
- Onboarding records showing a security briefing/acknowledgement occurred before access was granted.
- Training-platform completion dashboards for security awareness and any role-specific modules, segmented by audience (all staff vs. engineering vs. IT/security), plus overdue-notification logs for the last 12 months.
- Audit reports or checklists from management-led compliance reviews.
- Contractor/vendor agreements referencing security policy obligations.

### A.5.5 Contact with authorities

**What it requires:** The organisation should maintain a working relationship with relevant external authorities so it can engage them quickly during an incident or compliance need.

**Implementation guidance:**
- Maintain a documented, current list of relevant authorities, e.g., the national data protection regulator, a national computer emergency response team, law enforcement cybercrime units, telecom/hosting abuse contacts, and any sector-specific regulator.
- Assign a named role (e.g., the security lead) responsibility for keeping the list current and for making contact when needed.
- Note, for each authority, why contact might be needed (breach notification, incident reporting, legal request, business continuity) and any pre-registration required (e.g., regulator portals).
- Test the contact pathway periodically, for example as part of incident-response tabletop exercises, rather than relying on it for the first time during a real event.
- Review the list annually and whenever the organisation's regulatory footprint changes (new jurisdiction, new licence, new data type handled).

**Evidence an assessor would want to see:**
- A current, dated authorities-contact register (a maintained list or spreadsheet) with a named internal owner and a review-date column.
- An incident response plan referencing when and how each authority is engaged.
- Evidence the contact list was tested or reviewed (e.g., tabletop exercise notes).
- Records of any actual authority notifications made, where applicable.

### A.5.6 Contact with special interest groups

**What it requires:** The organisation should stay connected to external security communities and forums so it keeps pace with the evolving threat landscape.

**Implementation guidance:**
- Assign responsibility for external engagement (e.g., to the security lead) to identify and join relevant professional associations, vendor security-advisory lists, information-sharing communities, and industry forums.
- Subscribe to threat-intelligence sharing communities and sector-specific groups relevant to the business.
- Attend relevant conferences, webinars, or working groups, and feed useful takeaways back into risk assessments or control updates.
- Track which memberships and subscriptions are active and revisit their relevance annually: drop ones that no longer add value, and add new ones as threats evolve or the business changes.
- Feed information from these sources into the threat intelligence and risk management processes so it turns into action.

**Evidence an assessor would want to see:**
- A maintained register of active memberships/subscriptions with an assigned owner and review dates.
- Evidence that intelligence from these sources fed into a risk assessment or control change.
- An annual review record of group memberships and their continued relevance.

### A.5.7 Threat intelligence

**What it requires:** The organisation should systematically gather, analyse, and act on information about security threats.

**Implementation guidance:**
- Identify and vet a mix of internal sources (logs, alerts, incident history) and external sources (vulnerability databases, threat feeds, information-sharing communities) for reliability and relevance.
- Run continuous detective controls that generate intelligence: endpoint detection and response, network/intrusion detection, and centralised log or observability monitoring.
- Establish a regular cadence of proactive threat hunting: scheduled log reviews looking for indicators of compromise, not just reactive alert triage.
- Subscribe to public vulnerability feeds (e.g., a national vulnerability database) and vendor security bulletins relevant to the technology stack in use.
- Translate raw intelligence into a digestible internal format and route it to the people who own risk treatment, preventive controls, and detection tuning.
- Where appropriate, contribute indicators of compromise back to relevant sharing communities to support the wider ecosystem.
- Fold threat-intelligence findings into the periodic risk assessment cycle so they directly influence control prioritisation.

**Evidence an assessor would want to see:**
- A documented threat-intelligence process describing sources, cadence, and distribution.
- Log-review / threat-hunting records for the last 12 months.
- Risk register entries showing intelligence inputs changed a risk rating or control.
- A subscription list for external threat feeds and information-sharing sources.

### A.5.8 Information security in project management

**What it requires:** Security considerations should be part of project and product delivery from the outset, for every type of project, and stay in scope through to completion.

**Implementation guidance:**
- Add a mandatory security checkpoint to the project/development lifecycle (e.g., at design/requirements, before release, and post-implementation), regardless of project size or type.
- Require threat modelling for new features or architecture changes that touch sensitive data or trust boundaries.
- Incorporate security requirements (authentication, authorisation, data protection, logging) into requirements and acceptance criteria at the design stage, not as a late-stage review.
- Maintain a documented secure coding standard and require code review or automated scanning against it before merge/release.
- Track security-related project risks and actions the same way other project risks are tracked, with an owner and due date.
- Fold lessons from post-project reviews back into the project-management and development-lifecycle policies.

**Evidence an assessor would want to see:**
- Project templates or lifecycle checklists with an explicit security gate.
- Threat model documents for a sample of recent projects.
- A secure coding standard plus code review/scan results referencing it.
- Risk log entries showing security risks tracked to closure within a project.

### A.5.9 Inventory of information and other associated assets

**What it requires:** The organisation must keep a current, owned inventory of the information and other assets (people, software, hardware, services) that need protecting.

**Implementation guidance:**
- Maintain a single asset register covering information assets, software, hardware, and services, kept current through a defined update process (e.g., triggered on procurement or decommission).
- Assign an accountable owner for every asset or asset category: a specific individual or team, not a generic department.
- Classify each asset by criticality and sensitivity using a defined scheme that considers confidentiality, integrity, availability, and legal/regulatory obligations.
- Tier security controls (access restrictions, encryption, monitoring) to match each classification level, rather than applying one blanket control set to everything.
- Reconcile the register periodically against actual systems/accounts in use (e.g., cloud resource inventories, joiner-mover-leaver records) to catch drift.
- Formally retire assets from the register when decommissioned, with evidence of secure disposal or data destruction where relevant.

**Evidence an assessor would want to see:**
- A current asset register with assigned owners and classification labels.
- The classification scheme or policy document.
- Reconciliation records showing the register was checked against live systems.
- Evidence that controls applied match each asset's classification tier (e.g., encryption configuration, access lists).

### A.5.10 Acceptable use of information and other associated assets

**What it requires:** The organisation must set out clear, documented rules for how staff may use information and assets, and how those assets should be handled.

**Implementation guidance:**
- Publish an acceptable use policy covering devices, accounts, email/internet use, removable media, and the boundaries of personal use.
- Pair it with a handling standard specifying what staff must and must not do with information at each classification tier: storage, transmission, external sharing, disposal.
- Tailor the rules to actual business impact: default to enabling legitimate sharing and collaboration for low-sensitivity information, and tighten controls sharply for higher-sensitivity tiers.
- Require acknowledgement of the acceptable use policy at onboarding and again at each policy review cycle.
- Provide practical examples (e.g., "do not send customer data via personal email") rather than abstract rules alone, so staff can self-check compliance.
- Enforce key rules technically where possible (e.g., data loss prevention rules, blocking personal webmail on corporate devices) rather than relying on policy alone.

**Evidence an assessor would want to see:**
- A published, approved acceptable use policy and information handling standard.
- Staff acknowledgement records.
- Technical control configuration supporting the policy (e.g., DLP rules, device management policy).
- Records of any acceptable-use violations and how they were actioned.

### A.5.11 Return of assets

**What it requires:** When someone's employment, contract, or engagement with the organisation ends (or their role changes such that they no longer need certain assets), they must hand back everything belonging to the organisation that was issued to them.

**Implementation guidance:**
- Maintain an asset register that ties each issued device, credential, or physical item (laptop, phone, access card, token, storage media) to the individual it was issued to, so there's a clear checklist at offboarding.
- Build asset return into the standard offboarding workflow triggered automatically by HR when a termination or role change is logged, rather than relying on informal follow-up.
- Require IT or the line manager to confirm physical return before final systems access is revoked and before final pay/settlement is processed.
- Include an equivalent asset-return clause in contractor and third-party engagement terms.
- Track outstanding returns through your IT service/ticketing system so nothing is closed out until return is confirmed, with escalation for overdue items.
- For remote workers, provide a defined return mechanism (e.g., a prepaid courier/return kit) rather than assuming assets will find their way back.

**Evidence an assessor would want to see:**
- A documented offboarding procedure with an explicit asset-return step.
- An asset register showing assets, custodians, and current return status.
- Closed tickets/records evidencing confirmed asset return for a sample of recent leavers.
- Contract templates for contractors/third parties containing an asset-return clause.

### A.5.12 Classification of information

**What it requires:** Information should be sorted into a small number of categories based on how sensitive or critical it is, so everyone knows how much protection a given piece of information needs.

**Implementation guidance:**
- Define a small, usable set of classification tiers (e.g., Public, Internal, Confidential, Restricted) rather than an overly granular scheme nobody will apply consistently.
- Base each tier on the business impact of loss of confidentiality, integrity, or availability, not gut feel, and factor in any legal or contractual sensitivity.
- Assign responsibility for classifying information at the point of creation, typically to the information's owner or creator.
- Map each tier to concrete handling rules covering who can access it, how it can be stored and shared, and how it must be disposed of.
- Communicate the scheme to all staff through induction and periodic refresher training so classification decisions are applied consistently.
- Review the classification scheme itself periodically to confirm it still matches current legal, contractual, and business needs.

**Evidence an assessor would want to see:**
- An approved information classification policy defining the tiers and the criteria behind them.
- Induction/training records showing staff awareness of the scheme.
- Examples of information classified in practice across the different tiers.
- A review history showing the policy has an owner and a set review cadence.

### A.5.13 Labelling of information

**What it requires:** Information needs to be marked in a way that reflects its classification, so anyone handling it can immediately tell what level of protection applies.

**Implementation guidance:**
- Define concrete labelling mechanisms per medium: document headers/metadata for files, subject tags or banners for email, watermarks for print, and tags at the folder/system level for stored data.
- Set a default classification for anything not explicitly labelled, and default to the most protective tier rather than assuming low sensitivity: treating unlabelled information as sensitive is the safer failure mode.
- Automate labelling wherever tooling allows (templates, data-loss-prevention tools, classification add-ins) rather than relying purely on manual discipline.
- Extend labelling beyond files people read directly, to databases, backups, and removable media.
- Train staff on how to apply and interpret labels, and on what to do if they receive information that looks mislabelled or unlabelled.

**Evidence an assessor would want to see:**
- A documented labelling procedure tied to the classification scheme, including the default-to-most-restrictive rule.
- Sample labelled documents, emails, or systems across each classification tier.
- Template or tooling configuration demonstrating automatic label application.
- Training records covering labelling awareness.

### A.5.14 Information transfer

**What it requires:** Agreed rules need to be in place for moving information safely between people, systems, and organisations across every transfer channel, so information isn't intercepted, altered, or misdirected in transit.

**Implementation guidance:**
- Require encryption in transit for information above a defined sensitivity threshold, across email, file transfer, APIs, and messaging tools.
- Put written transfer agreements in place with external parties that spell out the security controls each side must apply when exchanging information.
- Set acceptable-use rules for electronic messaging covering when encryption or digital signing is required, based on the classification of the content.
- Train staff to double-check recipient details before sending sensitive information, and provide a mechanism to contain or recall accidental misdirection.
- Restrict or monitor the use of removable media and personal file-sharing/cloud services for organisational information transfers.
- Log and periodically review transfers of highly sensitive information to detect anomalies.

**Evidence an assessor would want to see:**
- A documented information transfer / acceptable-use policy covering messaging and file transfer.
- Signed data transfer or exchange agreements with key external parties.
- Configuration evidence for encryption in transit (e.g., enforced TLS, encrypted attachments).
- Training records showing staff awareness of safe transfer practices.

### A.5.15 Access control

**What it requires:** Access to systems, networks, and premises must be governed by a defined set of rules that reflect business need and risk, rather than being granted ad hoc.

**Implementation guidance:**
- Publish an access control policy defining how access is requested, approved, granted, and reviewed, covering both physical and logical access.
- Centralise authentication through a single identity provider with single sign-on wherever possible, rather than maintaining separate credentials per system.
- Apply role-based access so permissions map to job function, granted on a least-privilege, need-to-know basis.
- Define network access rules: segmentation of internal networks, controls on remote/VPN or zero-trust access, and rules for third parties or visitors using organisational networks.
- Apply the same principles to shared or co-working spaces if the organisation uses them.
- Review the access control policy periodically to keep pace with new systems and changing risk.

**Evidence an assessor would want to see:**
- An approved access control policy covering physical and logical access.
- Identity provider/SSO configuration or an architecture diagram showing centralised authentication.
- Role/permission matrices mapping access to job function.
- Network access policy plus evidence of enforcement (e.g., segmentation or VPN/zero-trust configuration).

### A.5.16 Identity management

**What it requires:** Every identity used to access systems needs to be managed across its full life, from creation, through changes, to eventual removal, so that only current, legitimate identities exist.

**Implementation guidance:**
- Define a joiner-mover-leaver process that ties identity creation, modification, and removal to authoritative HR events (start date, role change, termination).
- Issue one unique identity per person, no shared accounts, so every action can be traced to an individual; manage any necessary service/system accounts separately with their own ownership and review process.
- Automate provisioning and deprovisioning where possible by integrating the HR system with the identity provider, to cut manual delay and error.
- Set a target turnaround for both provisioning (so new starters aren't blocked) and deprovisioning (so leavers lose access promptly, ideally the same day).
- Keep an audit trail of identity creation, changes, and removal for accountability.
- Periodically reconcile the active identity list against current HR records to catch orphaned or stale accounts.

**Evidence an assessor would want to see:**
- A documented joiner-mover-leaver / identity lifecycle procedure.
- Logs or tickets showing identity creation and deprovisioning tied to HR events for a sample of recent starters/leavers.
- Evidence of unique-identity enforcement, plus any exception register for shared or service accounts.
- Reconciliation records comparing active identities to current headcount.

### A.5.17 Authentication information

**What it requires:** The way people prove their identity (passwords, tokens, biometrics, and similar) must be issued, communicated, and used securely, and users must understand how to protect it.

**Implementation guidance:**
- Define how initial credentials are issued to new users (e.g., via a secure, one-time channel) and require a forced setup/change on first use.
- Require multi-factor authentication for access to sensitive systems, applied based on a risk assessment rather than uniformly without justification.
- Prefer single sign-on to reduce the number of credentials a person has to manage; where SSO isn't available, require use of a password manager rather than reused or written-down passwords.
- Set minimum password/passphrase standards (length and complexity or entropy, with rotation only where it genuinely adds value) aligned with current good practice rather than outdated rules like frequent forced rotation.
- Train staff on secure handling of authentication information: not sharing credentials, recognising phishing attempts aimed at harvesting them, and reporting suspected compromise immediately.
- Ensure temporary or default credentials are unique per user/system and expire quickly.

**Evidence an assessor would want to see:**
- A documented authentication/credential management standard covering issuance, MFA, and password manager requirements.
- MFA enforcement configuration or reports for sensitive systems.
- Training records/materials on secure credential handling.
- Evidence of secure initial-credential distribution (e.g., one-time links, forced first-login reset).

### A.5.18 Access rights

**What it requires:** Access rights must be granted, changed, and removed through a controlled process, and reviewed regularly to confirm people still need what they have.

**Implementation guidance:**
- Require every access request and revocation to go through a documented approval workflow (e.g., a ticket with manager or system-owner sign-off) rather than informal requests.
- Tie access changes to HR triggers: grant on start, adjust on role change, revoke on termination, with a target turnaround for each (e.g., revoke access on or before the last working day).
- Conduct a periodic access recertification, at minimum annually, where system and data owners review who has access and confirm it's still required, removing anything no longer justified.
- Apply segregation-of-duties checks during access reviews so no individual accumulates conflicting privileged permissions without a compensating control.
- Keep records of every access grant, change, and revocation, including who approved it, for audit purposes.
- Review privileged/admin accounts more frequently than standard user access.

**Evidence an assessor would want to see:**
- A documented access provisioning, review, and revocation procedure.
- Records from the most recent access recertification (e.g. a quarterly privileged-access review and an annual full access review), including sign-off from system/data owners and any revocations actioned as a result.
- Onboarding/offboarding tickets (ideally auto-generated by the HR system) showing access granted and revoked, tied to starter/mover/leaver events.
- A privileged access register with evidence of its review cadence.

### A.5.19 Information security in supplier relationships

**What it requires:** Organisations need a defined process to identify and manage the information security risks that come from using a supplier's products or services, including agreeing security expectations before granting the supplier access.

**Implementation guidance:**
- Perform a security risk assessment before onboarding a new supplier, scaled to the level of access the supplier will have: a supplier hosting infrastructure or handling sensitive data needs deeper scrutiny than a low-risk vendor.
- Include information security obligations in supplier contracts: confidentiality, breach notification timeframes, right-to-audit, and data handling/return/destruction requirements on termination.
- Maintain a register of suppliers with access to organisational information, including their risk tier and date of last review.
- Re-assess supplier risk periodically and whenever the relationship materially changes, for example the scope of access expands, or a security incident occurs at the supplier.
- Define a supplier offboarding process that revokes access and confirms return or destruction of any organisational information the supplier held.
- For critical or high-risk suppliers, seek independent assurance (their own certification, audit reports, or a completed security questionnaire) rather than relying on self-attestation alone.

**Evidence an assessor would want to see:**
- A supplier/vendor risk management policy or procedure, including a completed due-diligence questionnaire template.
- A supplier register tiered by criticality, with a named business-unit owner per relationship and a documented review cadence for high-tier vendors (commonly annual).
- Signed contracts or data processing agreements containing information security clauses (confidentiality, breach notification, right-to-audit).
- A supplier's own third-party assurance report (their equivalent certification or audit) accepted as evidence in place of re-testing them directly.

### A.5.20 Addressing information security within supplier agreements

**What it requires:** Before any supplier can access, process, store or host your organisation's information, security expectations proportionate to that relationship need to be agreed in writing and signed off, not handled informally or after the fact.

**Implementation guidance:**
- Maintain a standard information security clause set (or schedule) that gets attached to every supplier contract, scaled to risk: a supplier touching production data warrants fuller terms than one supplying office equipment.
- Classify each new supplier relationship by the type of access involved (data access, system access, physical access, subcontracted service) before agreeing terms, so the right clause set gets applied.
- As a baseline, require confidentiality obligations, breach notification timeframes, right-to-audit or evidence-of-controls provisions, and disclosure of any subcontractors before granting access.
- Make the signed security schedule a hard gate in onboarding: no production or data access is provisioned until it is in place, not a follow-up item to chase later.
- Review and refresh the standard clause set periodically against current threats and regulatory obligations.
- Keep a central register showing which suppliers have which security terms in place, so gaps are visible at a glance.

**Evidence an assessor would want to see:**
- The current supplier security clause template, version-controlled with a review date.
- A sample of signed supplier agreements showing the security schedule attached.
- A supplier register showing risk tier and security-clause status per active supplier.
- Onboarding workflow documentation showing the security sign-off as a blocking step.

### A.5.21 Managing information security in the ICT supply chain

**What it requires:** Security risk management needs to extend beyond your direct suppliers to the wider chain of products and services they in turn depend on, including having a plan for when a critical link in that chain fails.

**Implementation guidance:**
- Tier suppliers by criticality and require deeper assurance from higher tiers, for example a certification report and named subcontractor list from a critical infrastructure supplier, versus a simple questionnaire for a low-risk one.
- Require critical suppliers to disclose their own significant subcontractors or sub-processors and to notify you when that chain changes.
- Build supply-chain failure into business continuity planning: name alternate providers in advance for your highest-criticality dependencies, rather than discovering the gap during an outage.
- Contractually require suppliers to notify you of material security incidents, certification changes, or business changes (ownership, region, subcontracting) that affect the risk profile.
- Feed supplier and supply-chain risks into the same risk register and review cadence used for internal risks, so they get equivalent governance attention.
- Track end-of-life and end-of-support dates for critical third-party components so unsupported software doesn't quietly become a liability.

**Evidence an assessor would want to see:**
- A supplier criticality/tiering register with assurance requirements mapped to each tier.
- A business continuity plan naming alternate providers for top-tier critical suppliers.
- Due diligence records (questionnaires, certifications, audit reports) on file for critical suppliers.
- Risk register entries showing supply-chain risks assessed alongside other organisational risks.

### A.5.22 Monitoring, review and change management of supplier services

**What it requires:** A supplier's security posture and service delivery need ongoing monitoring and periodic formal review after the contract is signed, with a controlled process for reassessing risk when their service changes.

**Implementation guidance:**
- Give each critical supplier relationship a clear internal owner and a place (ticket queue, shared inbox, dedicated channel) where service issues, security notices and status updates are logged and visible.
- Run a periodic (for example annual) formal review of each critical supplier's current assurance evidence: certifications, audit reports, penetration test summaries, SLA performance.
- Define what counts as a "material change" from a supplier (new subprocessor, infrastructure region change, ownership change, reported incident) and require suppliers to notify you of these under contract.
- When a supplier notifies a material change, re-run a lightweight risk assessment scaled to that supplier's criticality before accepting the change.
- Track service performance against contracted SLAs and escalate persistent underperformance through a defined path.
- Keep a log of completed supplier reviews, findings, and any resulting actions.

**Evidence an assessor would want to see:**
- A supplier review log or calendar showing periodic reviews completed, with dates and outcomes.
- Current assurance evidence on file for each critical supplier.
- An example of a supplier-notified change triggering a documented risk reassessment.
- SLA performance tracking for at least one critical supplier.

### A.5.23 Information security for use of cloud services

**What it requires:** Cloud services need security requirements applied across their full lifecycle: selecting a provider, using and managing the service day to day, and eventually exiting it.

**Implementation guidance:**
- Define selection criteria for cloud providers up front (data residency, relevant certifications, transparency about sub-processors, clarity of the shared-responsibility model) and assess candidates against them before signing.
- Document exactly which security responsibilities sit with your organisation versus the provider for each service, and assign a named internal owner accountable for that service's security configuration.
- Actively configure and use the security capabilities the provider exposes (logging, access controls, encryption options, alerting) rather than leaving them at default settings.
- Monitor cloud services on an ongoing basis for availability and security advisories, and route any cloud-related incidents through the same incident management process as everything else.
- Define an exit strategy for each cloud service at or shortly after onboarding (how data would be retrieved, in what format, and within what timeframe) and follow a documented offboarding checklist (data export verified, access revoked, deletion confirmed) when actually leaving a provider.
- When running multiple cloud services together, explicitly manage the integration points between them (e.g. identity federation, data flows) as their own control point.

**Evidence an assessor would want to see:**
- Cloud provider selection criteria and a completed assessment for a recent onboarding.
- A documented shared-responsibility matrix for at least one major cloud service in use.
- A named internal owner per cloud service, e.g. in a service register.
- An exit strategy and offboarding checklist for at least one cloud service, with evidence it was followed on a past offboarding.

### A.5.24 Information security incident management planning and preparation

**What it requires:** Detecting, triaging, escalating and resolving a security incident should follow a documented plan with clear ownership at each step, not be improvised in the moment.

**Implementation guidance:**
- Maintain a written incident response plan defining severity levels, escalation paths, and named roles (incident commander, communications lead, technical lead) rather than a generic "IT will handle it."
- Keep an up-to-date on-call/escalation contact list for security incidents, including after-hours coverage.
- Pre-define playbooks for your most likely incident types (credential compromise, data exposure, ransomware, denial of service, a breach at a third party affecting you).
- Establish a clear, well-known channel for staff to report a suspected incident, so reports don't get lost in general support queues.
- Run periodic tabletop exercises to test the plan and roles before a real incident happens, and update the plan based on what's learned.
- Set clear objectives up front: contain damage, preserve evidence, restore operations, identify root cause, so responders aren't inventing priorities mid-incident.

**Evidence an assessor would want to see:**
- A current incident response plan, version-controlled with a review date, naming roles in a RACI.
- An on-call/escalation contact list, kept up to date.
- At least one incident-type-specific playbook.
- Records of a tabletop exercise or simulation, including date, participants and findings.
- A sample incident ticket showing the full lifecycle: detection, triage/classification (including a "not a security incident" disposition path for false alarms), response actions, and closure, referencing the plan directly.

### A.5.25 Assessment and decision on information security events

**What it requires:** There needs to be a consistent, documented way to decide whether something noticed (an event) actually rises to the level of a genuine security incident requiring a response.

**Implementation guidance:**
- Define clear criteria distinguishing a routine event or alert from an actual incident, for example confirmed unauthorised access or data exposure, versus a false positive or benign anomaly.
- Assign a specific role or team the authority to make the incident/no-incident call, so it isn't decided ad hoc by whoever happens to notice the event.
- Define a severity classification scheme (e.g. critical/high/medium/low) tied to objective factors: data sensitivity involved, number of systems or users affected, whether exploitation is confirmed or only suspected.
- Set a target time-to-triage from when an event is first flagged to when a classification decision is made.
- Log every assessed event, including ones later closed as non-incidents, so the triage process itself can be reviewed and improved.
- Feed a "yes, incident" classification directly into the incident response process so there's a clear, immediate next step.

**Evidence an assessor would want to see:**
- Documented triage criteria and severity classification scheme.
- A log of assessed security events showing the decision made, date, and classification, including non-incidents.
- The named role or team with decision authority, documented in the plan or a responsibility matrix.

### A.5.26 Response to information security incidents

**What it requires:** Once something is confirmed as an incident, it should be worked through the same consistent, documented response process every time.

**Implementation guidance:**
- Follow a standard incident lifecycle: detect/confirm, contain, eradicate, recover, close, so responders always know what phase they're in and what comes next.
- Assign a single incident owner for the duration who coordinates activity and owns status communication, even when multiple teams are doing the technical work.
- Contain first, investigate root cause second: stop ongoing harm (revoke access, isolate a system, rotate credentials) before pursuing full root cause analysis, unless containment would destroy evidence.
- Define communication protocols in advance: who needs to be told, at what stage, in what format, including any legally mandated notification windows for regulators or affected customers.
- Keep a real-time incident timeline during the response, capturing what was done, when, and by whom.
- Only close an incident once recovery is verified, with a post-incident review scheduled as part of closing it out.

**Evidence an assessor would want to see:**
- A documented incident response lifecycle/procedure.
- A completed incident timeline for a real or simulated incident.
- Communication templates or protocols for notifying stakeholders during an incident.
- A record of formal incident closure, including confirmation that recovery was verified.

### A.5.27 Learning from information security incidents

**What it requires:** Every incident, and near miss, should feed back into improving controls and processes once it's resolved.

**Implementation guidance:**
- Run a blameless post-incident review after every incident above a defined severity threshold, and periodically in aggregate for lower-severity ones.
- Use a consistent root-cause method (e.g. five whys) to get past symptoms to the underlying control or process gap.
- Capture each review in a standard template: what happened, root cause, what worked, what didn't, and concrete follow-up actions with owners and due dates.
- Track follow-up actions in the same system used for other risk/improvement items, and confirm they're actually completed rather than left open indefinitely.
- Periodically look across multiple incidents for recurring themes rather than treating each one in isolation.
- Feed lessons learned back into training, playbooks, and the incident response plan itself: update the plan, not just the specific control that failed.

**Evidence an assessor would want to see:**
- Completed post-incident review reports for recent incidents, using a consistent template, explicitly capturing "lessons learned" and cross-linked back to the risk register.
- A tracked list of post-incident follow-up actions with status and owner.
- An example of a playbook or plan update that traces back to a specific lesson learned.
- A periodic trend analysis showing incidents reviewed for recurring themes.

### A.5.28 Collection of evidence

**What it requires:** There needs to be a consistent procedure for identifying, collecting and preserving evidence related to security events, so that if it's ever needed for disciplinary, legal, or regulatory purposes, it hasn't been lost or contaminated.

**Implementation guidance:**
- Treat evidence handling as mandatory for every incident from the outset, regardless of whether legal action seems likely at the time: evidence not collected early usually can't be recovered later.
- Establish a chain-of-custody process: who collected the evidence, when, how it was stored, and who has accessed it since, logged and retained.
- Use forensically sound collection methods for anything at risk of alteration (e.g. system images or log hashes rather than working directly on primary evidence).
- Define retention periods for incident evidence aligned to legal and regulatory obligations, and don't dispose of it before then.
- Restrict access to stored evidence to a limited, named set of people and log all access to it.
- Involve legal counsel early when an incident might lead to legal or regulatory action, so evidence handling meets the standard actually required for that process.

**Evidence an assessor would want to see:**
- A documented evidence collection and chain-of-custody procedure.
- A completed chain-of-custody log for a real or simulated incident.
- Defined evidence retention periods, with evidence that expired material is disposed of per policy (or held where a legal hold applies).
- An access log showing restricted, tracked access to stored evidence.

### A.5.29 Information security during disruption

**What it requires:** The organisation must plan how to keep information security controls operating at an acceptable level when normal operations are disrupted.

**Implementation guidance:**
- Define, as part of your continuity planning, which information security controls (access control, logging, encryption, monitoring) must remain active even in a degraded or crisis operating mode, not just which systems must stay available.
- Document minimum acceptable security postures for each disruption scenario (e.g. loss of primary site, key supplier outage, extended remote-only operation) so staff know what "good enough" looks like under pressure.
- Assign clear ownership for invoking and standing down disruption-mode security arrangements, including who can authorise temporary control exceptions and how those exceptions are logged and reversed.
- Build information security considerations into existing business continuity and disaster recovery plans rather than maintaining a separate, disconnected security continuity plan.
- Test the security-during-disruption arrangements at least annually, alongside or as part of broader continuity exercises, and record what worked and what didn't.
- Feed lessons from real disruptions and from test exercises back into the plan and into risk assessments.

**Evidence an assessor would want to see:**
- A continuity or disruption-response plan that explicitly addresses information security, with an owner and a review date.
- Records of at least annual testing (tabletop or live) with dated outcomes and follow-up actions.
- Examples of any temporary control exceptions granted during a real disruption, showing approval and later reversal.

### A.5.30 ICT readiness for business continuity

**What it requires:** ICT systems and services must be made resilient and recoverable in a way that is deliberately planned, tested, and directly tied to the organisation's wider business continuity objectives.

**Implementation guidance:**
- Run a business impact analysis (BIA) that identifies critical business activities, the ICT services that support them, and acceptable service level objectives (e.g. recovery time and recovery point targets) for each.
- Use the BIA together with a risk assessment of ICT services to choose continuity strategies covering the period before, during, and after a disruption (e.g. redundant infrastructure, standby environments, alternative processing arrangements, supplier failover).
- Translate the chosen strategies into concrete, written ICT continuity plans (including step-by-step recovery procedures) rather than leaving them as strategic intent.
- Assign clear roles with the authority and technical competence to prepare for, respond to, and recover from ICT disruptions, and make sure those people are trained and available (with backups for key roles).
- Exercise the ICT continuity plans on a regular cadence (e.g. annually, or after major infrastructure changes) using realistic scenarios, and update the plans based on what the exercises reveal.
- Have management formally review and approve the continuity plans and the recovery objectives they're built around.

**Evidence an assessor would want to see:**
- A documented BIA identifying critical activities, dependencies, and recovery objectives.
- ICT continuity/disaster recovery plans with named owners and a management approval record.
- A dated test report (e.g. "BCDR exercise conducted [month/year]") describing the specific scenario tested and the outcome or gaps found, with remediation actions and dates.
- Multi-region or multi-availability-zone architecture evidence supporting the availability/resilience claim, showing recovery objectives (RTO/RPO) were actually met in the most recent test.

### A.5.31 Legal, statutory, regulatory and contractual requirements

**What it requires:** The organisation needs to actively identify every legal, regulatory, statutory, and contractual obligation that affects its information security posture, keep that list current, and make sure its practices actually meet those obligations.

**Implementation guidance:**
- Maintain a single, owned register of applicable legal, regulatory, statutory, and contractual requirements relevant to information security (e.g. data protection law, sector-specific regulation, breach notification duties, customer contractual security clauses).
- Assign ownership of the register to a named role (e.g. an information security or compliance lead) responsible for keeping it current as laws, regulations, and contracts change.
- Review the register on a defined schedule and whenever a new jurisdiction, product, customer contract, or regulatory change could introduce new obligations.
- Map each identified requirement to the internal policy, control, or process that satisfies it, so gaps are visible rather than assumed away.
- Ensure use of cryptography specifically is checked against relevant import/export control laws, data sovereignty rules, and contractual restrictions before deployment in a new market or for a new customer.
- Make the register available to relevant stakeholders (legal, security, product) so new initiatives are checked against it before launch, not after.

**Evidence an assessor would want to see:**
- A maintained compliance/requirements register with an owner and last-review date.
- A mapping from each requirement to the control or policy that addresses it.
- Records of periodic review, including any updates triggered by new laws, regulations, or contracts.
- Documentation showing cryptographic usage was checked against applicable legal constraints for the relevant jurisdictions.

### A.5.32 Intellectual property rights

**What it requires:** The organisation must have procedures that protect its own intellectual property and respect the intellectual property rights of others, particularly around software licensing and proprietary materials.

**Implementation guidance:**
- Maintain a policy covering acceptable use of software and materials, including a prohibition on installing or using unlicensed or unauthorised software on organisational systems.
- Keep a software asset inventory that records licence type, seat/usage limits, and expiry or renewal dates, and reconcile it periodically against what's actually installed or provisioned.
- Include IP assignment and confidentiality clauses in employment and contractor agreements so work product created for the organisation is clearly owned by it.
- Track open-source components used in products and their licence obligations (e.g. attribution, copyleft terms) as part of the software development lifecycle.
- Protect the organisation's own trademarks, copyrighted material, and proprietary code from unauthorised external use or disclosure, including through contractual and technical controls.
- Provide guidance or training to staff on respecting third-party IP (e.g. not copying licensed content, not installing personal software on corporate assets) and on how to report suspected IP issues.

**Evidence an assessor would want to see:**
- A software asset/licence inventory with periodic reconciliation records.
- Policy documentation on acceptable software use and IP protection, with a review date.
- Signed employment/contractor agreements containing IP assignment clauses.
- Records of any open-source licence review as part of release processes.

### A.5.33 Protection of records

**What it requires:** Organisational records must be safeguarded against loss, destruction, tampering, and unauthorised access or disclosure for as long as they are legally, regulatorily, or contractually required to be kept.

**Implementation guidance:**
- Maintain a records retention schedule that classifies record types (e.g. financial, HR, security logs, customer data) and specifies how long each must be retained and why (legal, regulatory, or contractual basis).
- Apply access controls and encryption appropriate to the sensitivity of each record category, both at rest and in transit, consistent with the organisation's data classification scheme.
- Ensure records are stored in a way that is resilient to accidental loss (backups, versioning) and to deliberate tampering (audit trails, integrity checks, restricted write/delete access).
- Define and follow a secure disposal process for records once their retention period expires, so they aren't kept indefinitely or deleted prematurely.
- Extend retention and protection requirements to records held by third parties or processors acting on the organisation's behalf, via contract terms.
- Periodically test that archived or backed-up records can actually be retrieved intact when needed.

**Evidence an assessor would want to see:**
- A records retention schedule mapped to legal/regulatory/contractual bases, with a review date.
- Access control and encryption configuration for record repositories.
- Secure disposal records/logs showing records were destroyed in line with the schedule.
- A test log demonstrating successful restoration of archived or backed-up records.

### A.5.34 Privacy and protection of PII

**What it requires:** The organisation must identify what privacy and PII-protection obligations apply to it under relevant law, regulation, and contract, and put controls in place to actually meet them.

**Implementation guidance:**
- Maintain a privacy policy and supporting data protection standards that describe what personal data is collected, why, how it's protected, and how long it's kept.
- Maintain a record of processing activities (what personal data is held, its purpose, legal basis, and where it flows, including to third parties) and keep it current as processing changes.
- Perform a privacy or data protection impact assessment before launching new products, features, or vendor integrations that involve materially new PII processing.
- Put data processing agreements in place with any third party that processes personal data on the organisation's behalf, covering security obligations, sub-processing, and breach notification.
- Establish a documented procedure for handling data subject rights requests (access, correction, deletion) within the timeframes required by applicable law.
- Establish a breach notification procedure that identifies who assesses a suspected personal data breach, the criteria for notifying regulators and affected individuals, and the required timeframes.
- Apply data minimisation and purpose limitation principles: only collect and retain the personal data actually needed for the stated purpose.

**Evidence an assessor would want to see:**
- A published privacy policy and a maintained record of processing activities.
- Data processing agreements with relevant third-party processors.
- Completed privacy/data protection impact assessments for recent higher-risk projects.
- A documented breach notification procedure and, if applicable, records of past notifications and their timeliness.

### A.5.35 Independent review of information security

**What it requires:** The organisation's information security approach (its policies, controls, and their implementation) must be checked periodically by parties independent of the teams running it, not only self-assessed.

**Implementation guidance:**
- Run an independent audit programme (internal audit function or external assessors who are not responsible for operating the controls being reviewed) on a defined schedule, and additionally whenever a significant change to the security environment occurs.
- Engage external specialists for technical assurance activities such as penetration testing, separate from the certification or compliance audit process, so technical findings and management-system findings are both covered.
- Where the organisation holds or seeks a security certification, undergo the associated periodic surveillance or recertification audits from an accredited external certification body.
- Refresh the organisation's risk assessment at least annually (or after significant change) so independent reviews are checked against a current risk picture, not a stale one.
- Track findings from all independent reviews to closure, with owners and target dates, and report status to leadership.
- Rotate or vary the scope/focus of internal reviews over time so that no area goes unexamined for multiple cycles.

**Evidence an assessor would want to see:**
- An audit schedule/programme showing planned and completed independent reviews with dates and scope.
- Independent penetration-test reports commissioned from a third party on a defined (commonly annual) cadence, with findings tracked to remediation.
- A current risk assessment, refreshed within the last 12 months.
- A corrective-action/deficiency register, separate from the risk register, tracking audit findings to closure with dates.

### A.5.36 Compliance with policies, rules and standards for information security

**What it requires:** The organisation must regularly check that its actual day-to-day practices, across teams and systems, align with its stated information security policies, rules, and standards, and correct any gaps found.

**Implementation guidance:**
- Require managers to periodically verify that security procedures and work instructions within their own area are actually being followed, and to record and act on any shortfalls they find.
- Define key risk or compliance indicators tied to policy requirements (e.g. patch currency, access review completion, security training completion) and track them on a recurring basis to surface non-compliance trends.
- Feed the results of manager checks and indicator tracking into a central non-compliance or issues register, and review that register ahead of internal and external audits.
- Technically test information systems for compliance with security policies and standards (configuration baselines, hardening standards, vulnerability scanning) on a regular schedule.
- Commission independent penetration testing at least annually to validate that technical controls hold up against real-world attack techniques.
- Maintain a mapping from each control requirement to its supporting evidence so audit preparation is a matter of retrieval, not a scramble.

**Evidence an assessor would want to see:**
- Manager compliance-check records with identified shortfalls and remediation actions.
- A compliance/risk indicator dashboard or report with a defined review cadence.
- Technical compliance scan and penetration test reports from the last 12 months.
- A non-compliance/issues register showing items tracked to closure.

### A.5.37 Documented operating procedures

**What it requires:** Procedures for running information processing systems and facilities must be written down and accessible to the people who need to perform them.

**Implementation guidance:**
- Identify which operational activities affecting the confidentiality, integrity, or availability of information processing need a documented procedure (e.g. backup and restore, access provisioning/deprovisioning, incident handling, change deployment, system hardening).
- Write procedures at a level of detail that lets a suitably trained person execute them consistently without relying on the original author's memory.
- Maintain a central, indexed register of all operating procedures, including an owner and a review/next-due date for each, so gaps and stale procedures are visible.
- Store procedures where the relevant team can actually find and access them when needed, including during an incident or when the usual owner is unavailable.
- Version-control procedures and review them on a defined cadence and after any related process or system change, retiring or updating outdated ones.
- Include new-starter onboarding steps that direct staff to the procedures relevant to their role.

**Evidence an assessor would want to see:**
- A register or index of documented operating procedures with owners and review dates.
- Sample procedures for key operational activities (backup, access management, incident response) showing sufficient step-by-step detail.
- Version history showing procedures have been reviewed/updated on schedule.
- Evidence that procedures are accessible to the staff who need them (e.g. onboarding checklist references, access logs to the procedure repository).

---

## Adapt this to your context

- A lean team can't run all 37 of these at full maturity from day one. Prioritise the controls that gate a certification audit or a customer security questionnaire first (policy, roles, access control, supplier relationships, incident management), and treat the rest as a maturity roadmap rather than a simultaneous requirement.
- Several controls here (A.5.19 to A.5.23, supplier and cloud relationships) assume the organisation actually uses third-party suppliers and cloud services at meaningful scale. If the estate is small, the depth of due diligence should scale down accordingly, but the discipline of *doing* due diligence, however lightweight, still matters.
- "Independent review" (A.5.35) doesn't have to mean an expensive external audit on day one for a very early-stage team: a genuinely independent internal reviewer (someone who didn't build the control being reviewed) can satisfy the spirit of the control until the organisation can afford external assurance.
- Framework references throughout this file are deliberately generic (a "national data protection regulator," "hardening standards") rather than naming a specific jurisdiction's regulator or a specific standard's edition. Substitute your own jurisdiction's actual regulator and the hardening standards your team actually follows.
