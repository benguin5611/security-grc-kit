---
Artefact type: Reference
Owner role: Information Security Manager, with input from Engineering leadership
Review cadence: Per audit period (typically every 6 to 12 months), plus whenever the system changes materially
Version: Worked example (fictional)
---

# SOC 2 system description: Tanager Technologies Pty Ltd

> **This is a worked example for a fictional company, Tanager Technologies Pty Ltd.** Every name, figure, date, and vendor below was invented to show how the template is filled in. Tanager does not exist. Replace all of it with your own organisation's real detail. The blank template this example is built from lives at [../system-description-template.md](../system-description-template.md).

## Examination information

| Field | Tanager's answer |
|---|---|
| Company name | Tanager Technologies Pty Ltd |
| Trading name (if different) | Tanager |
| Company registration number | ABN 49 001 002 003 |
| Registered address | Level 9, 240 Kent Street, Sydney NSW 2000, Australia |
| Scope of services | Tanager operates a cloud accounts-payable automation platform for mid-market finance teams. The system ingests supplier invoices, extracts and validates the invoice data, runs a configurable approval workflow, and exports approved payment-ready records into each customer's own ERP or accounting system. Tanager does not move money. |
| Service auditor | Ashworth Beale Assurance, Chartered Accountants |
| Examination standard | AICPA description criteria DC section 200 (2018 description criteria); AICPA trust services criteria TSP section 100 (2017 criteria with 2022 revised points of focus); examination conducted under AICPA attestation standards and ISAE 3000 (dual-reported for international customers) |
| Report type | SOC 2 Type II |
| Examination period | 1 October 2025 to 31 March 2026 |
| Applicable Trust Services Criteria | Security, Availability, Confidentiality, Processing Integrity. Privacy is not elected (see [Criteria not relevant to the system](#criteria-not-relevant-to-the-system)). |

## Types of service provided

Tanager provides a single product: a business-to-business accounts-payable automation platform delivered as software-as-a-service. The company was founded in 2019 and runs remote-first within Australia with a small Sydney office and around 60 staff. Customers are the finance teams of mid-market businesses.

A customer sends supplier invoices to Tanager by one of three routes: forwarding them to a dedicated email-ingestion address, uploading them in the web application, or posting them to the REST API. Tanager reads the invoice, extracts the line items and header fields, and validates the result against the customer's configuration and supplier master data. Each invoice then moves through a multi-step approval workflow that the customer defines. Once approved, the record is exported to the customer's ERP or accounting system over an API as a payment-ready record.

The capabilities the system exposes to a customer are:

- Submit invoices by email, web upload, or REST API.
- Configure approval rules and approver hierarchies.
- Review invoices and approve or reject them.
- Create and maintain supplier master records.
- Export approved records to the connected ERP or accounting system.
- Retrieve audit logs through the API.
- Manage the customer's own users and role assignments.

## Principal service commitments and system requirements

### Service commitments

Tanager makes the following assurances to its customers, and reflects them in customer agreements and public service documentation.

- **Security, availability, and confidentiality.** Tanager protects customer and supplier data with encryption in transit and at rest, restricts access to that data on a least-privilege basis, monitors the platform for security-relevant events, and operates the service to meet a published availability target. Confidential customer data is handled only for the purpose of delivering the service.
- **Operational functionality.** The platform ingests, extracts, validates, routes for approval, and exports invoice data as described in the service documentation, and processes that data accurately and completely according to the customer's configuration.
- **Regulatory support.** Tanager acts as a data processor and supports customers in meeting their own obligations, including retention of financial records for a configurable period. Tanager makes its commitments through the data processing agreement and contractual terms rather than making regulatory representations on the customer's behalf.

### Operational requirements

To meet those commitments, Tanager has established functional and non-functional requirements for the system, and monitors the third parties it depends on.

- **Functional requirements.** Invoice data must be extracted and validated against the customer's configuration before it can enter the approval workflow, approval steps must be enforced in the order the customer defines, and only approved records may be exported to a customer's ERP.
- **Non-functional requirements.** The service must meet its availability target, encrypt data in transit and at rest, log security-relevant and processing-relevant events, and keep production data isolated from lower environments.
- **Third-party monitoring.** Tanager reviews the assurance reports of its subservice organisations (see [Subservice organisations](#subservice-organisations)) at least annually, tracks their status and any reported incidents, and reassesses the dependency if a provider's assurance lapses or a material issue is disclosed.

### System requirements

Tanager holds ISO/IEC 27001:2022 certification. The information security management system built to that standard drives Tanager's system requirements and its control set. The requirement categories the ISMS covers are:

- Context and alignment of the ISMS with business objectives.
- Leadership and accountability.
- Risk-based planning.
- Operational implementation of controls.
- Monitoring and evaluation.
- Continual improvement.
- Asset management.
- Risk management.
- Access management.
- Asset protection.
- Operational security.
- Supplier and third-party management.
- Incident response and recovery.
- Compliance and reporting.

## System components

### Infrastructure

Tanager runs entirely on a single Tier-1 public cloud provider (Amazon Web Services) under a shared-responsibility model: the provider is responsible for the security of the underlying cloud (physical facilities, host hardware, and the managed-service control plane), and Tanager is responsible for security in the cloud (configuration, identity, data, and application code).

The primary environment runs in the Sydney region (ap-southeast-2) across multiple availability zones for resilience. A disaster-recovery standby is maintained in the Melbourne region (ap-southeast-4). Application services are containerised and run on managed orchestration. The application tier is stateless and sits behind a load balancer and a web application firewall.

> This example fills the infrastructure section with specific provider, region, and service detail because it stands in for the full-detail version shared with an auditor and vetted customers under NDA. A public trust-page version of the same document would describe the pattern ("a single Tier-1 cloud provider, multiple availability zones, a separate disaster-recovery region") without naming the provider, regions, or managed services. Decide who the audience is before deciding how much to disclose.

### Software

The categories of software and tooling that build, support, secure, and monitor the system, with the products Tanager uses shown for illustration:

| Category | Product |
|---|---|
| Workforce identity and access management (SSO and MFA) | Okta |
| Version control and CI/CD | GitHub and GitHub Actions |
| Infrastructure as code | Terraform |
| Application and infrastructure observability | Datadog |
| Alerting and on-call | PagerDuty |
| Endpoint management | MDM-managed laptops with full-disk encryption and anti-malware |
| Secrets management | Cloud-native secrets manager |
| Cloud security posture management | Cloud security posture management tool |
| Vulnerability management | Dependency and container scanning in CI, plus periodic external penetration testing |
| Data storage | Managed PostgreSQL (multi-AZ, encrypted at rest) and encrypted object storage |
| Customer support | Ticketing platform |

### People

Tanager organises its people by function. The functions and their responsibilities are:

- **CEO.** Overall accountability for the business and its strategy.
- **CTO (Dana Whitmore).** The accountable executive for the platform, its architecture, and its security posture, and the management signatory for this description.
- **Head of Engineering.** Delivery of the platform and management of the engineering teams.
- **Information Security Manager.** Owns the ISMS and the control matrix, runs risk assessments, and coordinates the SOC 2 examination.
- **Platform / SRE.** Operates the production environment, infrastructure as code, monitoring, and incident response.
- **Product.** Defines and prioritises the product roadmap and requirements.
- **Customer Success and Support.** Onboards customers and handles support requests through the ticketing platform.
- **People Operations.** Recruitment, onboarding and offboarding, and staff security awareness.

A board with an independent non-executive chair provides governance oversight.

### Data

**Data lifecycle.** Data moves through the system in the following stages:

- **Ingestion.** Invoices arrive by email, web upload, or REST API.
- **Validation and extraction.** Header and line-item data is extracted and validated against the customer's configuration and supplier master data.
- **Storage.** Extracted data and original documents are stored encrypted.
- **Workflow processing and approval.** Records move through the customer's configured approval steps.
- **Export.** Approved records are pushed to the customer's ERP or accounting system.
- **Archival.** Records are retained for the customer's configured retention period (financial records default to seven years).
- **Deletion.** Customer data is deleted within 30 days of contract termination unless a legal hold applies.

**Data categories.** The system holds two categories with different handling rules. The first is Tanager's own contractual data: customer account and user records for the businesses that hold a Tanager subscription. The second is data processed on a customer's behalf: supplier master data, invoice and transaction data, and the approval and workflow metadata that goes with it. Customers control the supplier and invoice data as data controllers; Tanager processes it on their instruction under a data processing agreement. The system also generates system and audit logs.

**Types of data collected.** The categories of data the system processes are customer account and user data, supplier master data (including supplier names, contact details, bank account details, and business identifiers), invoice and transaction data, approval and workflow metadata, and system and audit logs. A version of this description prepared for an auditor would list the literal fields in each category.

**Supported file types.** The system accepts and produces PDF documents, common image formats, CSV files, and structured JSON payloads through the API.

**Personal data and protections.** Any personal data the system holds sits within the supplier and customer-user categories above. The baseline protections applied to it are encryption in transit (TLS 1.2 or higher) and at rest (AES-256 through the cloud key management service), least-privilege access control administered through the identity provider, and monitoring of access and security-relevant events.

**Third-party access and data considerations.** The subservice organisations that may hold or process data on Tanager's behalf operate under contractual data-protection obligations. Tanager satisfies itself of their continuing compliance by reviewing each provider's own SOC 2 report or ISO/IEC 27001 certificate at least annually, as described under [Subservice organisations](#subservice-organisations).

**Boundary definitions.** Tanager's responsibility covers the web application, the REST API, the email-ingestion endpoint, and the processing and workflow backend. The following are outside the system boundary: the customer's ERP or accounting system, the customer's devices and browsers, the customer's identity provider when SSO federation is used, and suppliers' own systems. Data leaving Tanager for a customer's ERP passes out of the boundary at the API integration point.

### Procedures

Tanager's internal control environment is documented as procedures, organised by the categories used in its control matrix. Each is reviewed at least annually as part of the ISMS cycle, and out of cycle whenever a material system change, a risk assessment, or an incident calls for it.

- **Control environment.** Governance, security policy, roles and accountabilities, and staff security awareness.
- **Information and communication.** How security responsibilities and changes are communicated internally and to customers.
- **Risk assessment.** Periodic and event-driven identification, evaluation, and treatment of risk.
- **Monitoring activities.** Logging, alerting, and management review of control operation.
- **Control activities.** The day-to-day controls that enforce the policies.
- **Logical and physical access controls.** Identity, authentication, authorisation, and access reviews.
- **Change management.** How code and infrastructure changes are reviewed, tested, approved, and released.
- **System operations.** Operating the production environment, backups, and incident response.
- **Risk mitigation.** Vendor management, business continuity, and disaster recovery.

## Applicable Trust Services Criteria and related controls

Four of the five Trust Services Criteria categories apply to Tanager's system: Security (the common criteria, always included), Availability, Confidentiality, and Processing Integrity. Processing Integrity applies because the accuracy, completeness, and validity of invoice processing is a core function of the service. Privacy is not elected; the reason is set out under [Criteria not relevant to the system](#criteria-not-relevant-to-the-system).

The detailed control-to-criterion mapping is maintained in Tanager's control matrix rather than repeated here. See the companion [SOC 2 to ISO 27001 crosswalk](../soc2-iso27001-crosswalk.md) for how the controls map across the two frameworks.

## Changes to the system

Two changes were made during the examination period that a reader should be aware of. Neither materially changed the control environment, and both went through Tanager's change-management process.

- SSO and SCIM provisioning was introduced for customer administrators, allowing customers to federate authentication and manage user lifecycle from their own identity provider.
- The primary datastore migration to a multi-availability-zone configuration was completed, improving resilience of the managed PostgreSQL tier.

## System incidents

No security incident during the examination period met Tanager's disclosure materiality threshold.

## Complementary user entity controls

Tanager's controls are designed on the assumption that its customers (the user entities) operate certain controls on their own side. Tanager's control objectives cannot be met by Tanager alone if these are absent. The controls Tanager relies on customers to implement are:

1. Enforce SSO, MFA, and strong authentication for their own users.
2. Encrypt any data the customer controls, in transit and at rest, on their own systems.
3. Submit accurate and complete invoice and supplier data.
4. Handle privacy and confidentiality appropriately for any personal or sensitive data the customer chooses to submit.
5. Run periodic access reviews and deprovision leavers promptly on their side.
6. Keep customer-controlled endpoints that interact with Tanager protected against malware.
7. Meet their own obligations as data controller under applicable data-protection law.
8. Configure retention and issue deletion instructions, and validate exported records once they land in the customer's ERP.
9. Notify Tanager of suspected security events on their side of the integration.

This list is indicative. It is each user entity's own auditor's responsibility to assess whether the customer's implementation of these controls is adequate.

## Subservice organisations

Tanager depends on the following subservice organisations. Tanager uses the **carve-out method** for all of them: this description covers Tanager's own monitoring of each provider, and excludes the provider's internal controls from the scope of Tanager's report. Tanager relies on each provider's own SOC 2 report or ISO/IEC 27001 certification for assurance over their internal controls, and reviews that evidence at least annually.

| Subservice organisation | Role in the system | Method |
|---|---|---|
| Cloud infrastructure provider (Amazon Web Services) | Hosts all compute, storage, database, and networking for the platform | Carve-out |
| Workforce identity provider (Okta) | Provides SSO and MFA for Tanager staff | Carve-out |
| Source-control and CI/CD platform (GitHub) | Hosts source code and runs the build and deployment pipeline | Carve-out |
| Observability platform (Datadog) | Collects application and infrastructure telemetry | Carve-out |
| Incident and alerting platform (PagerDuty) | Routes alerts to the on-call engineers | Carve-out |
| Customer-support platform | Records and manages customer support requests | Carve-out |

Tanager's own controls that address these dependencies are vendor risk assessment before onboarding, annual review of each provider's assurance report, and monitoring of provider status and disclosed incidents. These sit in the risk-mitigation and supplier-management sections of the control matrix.

The Complementary Subservice Organisation Controls (CSOCs) Tanager relies on include physical and environmental security of the hosting facilities, logical access controls over the providers' own systems, availability and backup of the managed services, and secure operation of each provider's platform. A reader with a valid business need can request the relevant provider's SOC 2 report or ISO/IEC 27001 certificate from Tanager, subject to the provider's own terms.

## Criteria not relevant to the system

Tanager is a data processor rather than a data controller. It processes personal information (contained within supplier and customer-user records) only as instructed by its customers, and it does not interact directly with the individuals whose information it holds. On that basis the Privacy category of the Trust Services Criteria is not applicable to Tanager's system and has not been elected.

- **Control.** The Privacy criteria (TSP section 100, category P), covering notice and choice, collection, use, retention, disclosure, and disposal of personal information as they apply to a data controller's direct relationship with data subjects.
- **Reason for exclusion.** Tanager does not collect personal information directly from data subjects, does not decide the purposes for which supplier or invoice data is processed, and has no direct relationship with the individuals concerned. Those responsibilities sit with Tanager's customers as data controllers.
- **Disclosure.** Tanager's obligations relating to personal data are set by the data processing agreement it signs with each customer. That agreement places responsibility for lawful basis, notice, and data-subject rights on the customer as controller, and obliges Tanager to process personal data only on documented instructions, to protect it, and to assist the customer where the agreement requires. Confidentiality of that data is addressed under the Confidentiality criteria, which are in scope.
</content>
</invoke>
