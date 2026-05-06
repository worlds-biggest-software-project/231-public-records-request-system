# Public Records Request System

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source platform for FOIA and public-records request intake, tracking, and response management.

The Public Records Request System is an agency-side platform for handling FOIA, state public-records, and equivalent requests end-to-end: structured citizen intake, statutory deadline tracking, departmental routing, document review and redaction, and disclosure. It is built for city and county clerks, federal FOIA officers, state agency counsels, and police records units who today face high-cost commercial suites or unsupported open-source alternatives.

---

## Why Public Records Request System?

- Market-leading commercial tools (GovQA, NextRequest, FOIAXpress, Casepoint) carry custom enterprise pricing typically running $5,000–$200,000+ per year, putting them out of reach for many small municipalities.
- Most incumbents lack a public, open API: NextRequest does not currently offer one, and GovQA exposes no documented open API for third-party FOIA portals to push requests in.
- Existing AI capabilities are largely confined to PII redaction (RapidReview, FOIAXpress AI Assistant, Casepoint); no surveyed tool offers AI-suggested exemption classification with confidence scoring.
- Open-source options exist but are partial: ArkCase requires significant IT capacity, and Alaveteli is a requester portal with no agency-side workflow, redaction, or fee management.
- GAO-26-109034 and federal procurement pressure are driving demand for tools that reduce backlogs and improve consistency across agencies.

---

## Key Features

### Citizen Intake and Status Tracking

- Structured, dynamic online request intake forms (not free-text email)
- Requester self-service status portal without staff interaction
- Multilingual support for requester-facing pages
- Public archive options inspired by Alaveteli-style transparency

### Workflow, Routing, and Deadlines

- Automated statutory deadline calculation and overdue alerts, configurable per jurisdiction
- Department routing with task assignment and in-app notifications
- Interagency collaboration portal for non-staff subject matter experts
- Full audit trail covering all actions, communications, and document events

### Document Review, Redaction, and Disclosure

- Automated PII pattern matching for SSNs, emails, phone numbers, and financial identifiers
- Manual redaction with precise compliance control
- Secure document release portal for delivering responsive records
- Correspondence management with letter and email templates

### Fees, Payments, and Reporting

- Fee calculation, online payments, and invoicing
- Standard and ad-hoc reports on volume, backlog, response times, and exemption usage
- DOJ Annual FOIA Report generation for federal deployments

### Interoperability

- FOIA.gov Portal API integration for federal agency deployments
- Integrations with common ECM platforms such as Laserfiche, SharePoint, and OnBase
- Open API for third-party requester portals to push requests in

---

## AI-Native Advantage

Unlike incumbents whose AI is largely limited to PII redaction, this project targets the underserved gap of AI-assisted exemption classification with confidence scoring and human-in-the-loop review. Additional AI capabilities include intelligent triage and routing of incoming requests by topic and likely exemption, natural-language parsing of free-text requests to pre-populate routing fields, ML-driven backlog prediction and SLA alerting trained on historical processing data, and proactive disclosure recommendations that scan agency repositories to surface records suitable for pre-emptive publication. Research cites potential 60–80% reductions in manual review time vs. current semi-manual workflows.

---

## Tech Stack & Deployment

The project is designed for both self-hosted and cloud deployments, with FedRAMP-aligned configurations on the roadmap to match the procurement bar set by Tyler FOIA, Casepoint, and ArkCase. Architecture references include ArkCase (Apache 2.0, BPMN 2.0 workflow, REST APIs via Spring Boot, Alfresco ECM integration) and Alaveteli (MIT, JSON read API, Atom feeds, Ruby on Rails). Standards alignment covers FOIA (5 U.S.C. § 552), the FOIA Improvement Act of 2016, state Public Records Acts, NARA Records Management Standards (36 CFR Chapter XII), OMB Memorandum M-19-21, and DCAT / Project Open Data for proactive disclosure metadata.

---

## Market Context

No widely published standalone market-size figure exists for FOIA/public-records-request software specifically; the broader US government transparency and records-management software market is valued at several hundred million dollars annually, with Granicus and CivicPlus/Tyler serving thousands of agencies collectively (research.md). Small-agency solutions start around $5,000/year while enterprise contracts run $50,000–$200,000+/year. Primary buyers are city and county clerks, federal FOIA officers, state agency general counsels, police department records units, and public university compliance offices.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

Note: Granicus/GovQA describes its predictive intake deflection mechanism as patented. Any AI-native deflection feature in this project must be independently designed rather than replicating the GovQA mechanism.

---

## Licence

Licence to be determined. See [discussion](#) for context.
