# Worked examples

These are the two SOC 2 templates in this kit, filled in end to end for a single fictional company so you can see what a completed version looks like before you write your own.

**Everything in these files is invented.** Tanager Technologies Pty Ltd is not a real company; every name, figure, date, address, auditor, and vendor is made up to illustrate how the templates are populated. The pair is internally consistent (the assertion refers to the same entity, period, scope, and subservice organisations as the description), so you can see how the two documents line up in a real report.

| Example | Fills in |
|---|---|
| [tanager-system-description.md](tanager-system-description.md) | [system-description-template.md](../system-description-template.md) |
| [tanager-management-assertion.md](tanager-management-assertion.md) | [management-assertion-template.md](../management-assertion-template.md) |

## The fictional company, in one paragraph

Tanager is a mid-market B2B SaaS platform for accounts-payable automation: customers send it supplier invoices, it extracts and validates the data, runs an approval workflow, and pushes approved records into the customer's own accounting system. It is a data processor acting on its customers' instructions, runs on a single public cloud provider, and holds ISO/IEC 27001:2022 certification. Its example SOC 2 Type II covers Security, Availability, Confidentiality, and Processing Integrity; it has not elected the Privacy category, and the description shows the processor rationale for that.

## How to use these

- Read the example next to its template to see how each section and placeholder gets turned into concrete content.
- Do not copy Tanager's facts into your own report. Start from the template, and fill it with your own organisation's real, current detail.
- Note the sensitivity guidance in the templates: a real system description shared with your auditor under NDA carries more specific infrastructure and vendor detail than anything you would publish. These examples stay at the level of detail appropriate for a public illustration and say so where it matters.
