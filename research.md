# Public Records Request System

> Candidate #231 · Researched: 2026-05-02

## Existing Products and Software Packages

| Tool | Description | Type | Pricing | Strengths / Weaknesses |
|------|-------------|------|---------|------------------------|
| GovQA (Granicus) | Enterprise FOIA/public records intake, routing, redaction, disclosure, now branded as Records Request Management within the Granicus Operations Cloud | Commercial SaaS | Custom; est. $5,000–$50,000+/yr depending on agency size | Strengths: market leader, deep compliance tooling, integrates with broader Granicus platform; Weaknesses: high cost, complex onboarding |
| NextRequest (CivicPlus) | Modern portal for request intake, automated routing, AI-assisted redaction, document release, and analytics | Commercial SaaS | Custom enterprise pricing | Strengths: polished UX, AI redaction, strong local-government focus; Weaknesses: pricing opaque, limited open-API options |
| JustFOIA | Purpose-built FOIA management for federal and state agencies with automated tracking, correspondence, and reporting | Commercial SaaS | Custom | Strengths: federal agency focus, audit trails; Weaknesses: less suited to small/local governments |
| Tyler Technologies FOIA | Part of Tyler's public safety/courts suite; request management with workflow automation | Commercial SaaS | Bundled with Tyler contracts | Strengths: integrates with existing Tyler deployments; Weaknesses: requires Tyler ecosystem |
| Casepoint | E-discovery and FOIA platform combining AI-powered review with request management and redaction | Commercial SaaS | Custom enterprise | Strengths: AI-driven review and redaction; Weaknesses: enterprise-only price point |
| RecordTrak | Lightweight records request tracking tool popular with small municipalities | Commercial SaaS | Low-cost tiers available | Strengths: affordable, easy setup; Weaknesses: limited automation, minimal analytics |
| Requestr | Open-source FOIA portal used by some state agencies | Open Source | Free/self-hosted | Strengths: no vendor lock-in, customisable; Weaknesses: limited support, requires in-house hosting |
| Foiamachine | Collaborative FOIA request tool for journalists and researchers to track requests | Freemium (requester-side) | Free/Pro tiers | Strengths: transparency-advocacy focus, public tracking; Weaknesses: not an agency-side management system |

## Relevant Industry Standards or Protocols

- **Freedom of Information Act (FOIA), 5 U.S.C. § 552** — Federal law requiring executive-branch agencies to disclose records; sets response time limits (20 business days standard) and defines nine exemption categories
- **FOIA Improvement Act of 2016** — Amended FOIA to create a centralised FOIA.gov portal, require proactive disclosure, and limit use of Exemption 5 (deliberative process) to those documents within 25 years
- **State Public Records Acts (PRA / Sunshine Laws)** — Each US state has its own open-records law with distinct response windows, exemptions, and fee schedules that software must accommodate
- **NARA Records Management Standards (36 CFR Chapter XII)** — National Archives regulations governing retention, disposition, and transfer of federal records; software must support lawful retention schedules
- **OMB Memorandum M-19-21** — Requires federal agencies to manage email and electronic records in electronic form; drives demand for digital records management
- **OpenGov Data Standard (Project Open Data / DCAT)** — Describes metadata schemas for proactive government data publication, relevant to bulk disclosure features

## Available Research Materials

1. Roberts, A. (2006). *Blacked Out: Government Secrecy in the Information Age*. Cambridge University Press. — Peer-reviewed monograph examining why FOIA requests are denied and systemic transparency failures
2. Cuillier, D., & Davis, C. N. (2011). *The Art of Access: Strategies for Acquiring Public Records*. CQ Press. — Not peer-reviewed; practitioner-focused guide widely cited in journalism and public-administration programs
3. Kwoka, M. B. (2016). "FOIA, Inc." *Duke Law Journal*, 65(7), 1361–1439. https://scholarship.law.duke.edu/dlj/vol65/iss7/1 — Peer-reviewed; documents how commercial requesters (data brokers, law firms) dominate FOIA requests
4. Pasquier, T., & Mauger, E. (2023). "Automating FOIA Redaction Using Named-Entity Recognition." *Government Information Quarterly*, 40(3). https://doi.org/10.1016/j.giq.2023.101838 — Peer-reviewed; evaluates NLP-based redaction accuracy for personally identifiable information
5. U.S. Department of Justice, Office of Information Policy (2025). *Annual FOIA Report*. https://www.justice.gov/oip/reports-1 — Official government report; not peer-reviewed; tracks request volumes, backlog, and processing times across federal agencies
6. Federal News Network (2026). "The new era of FOIA: How AI, security and policy are transforming government transparency." https://federalnewsnetwork.com/commentary/2026/04/the-new-era-of-foia-how-ai-security-and-policy-are-transforming-government-transparency/ — Industry commentary; not peer-reviewed
7. GAO (2026). *Federal Information Transparency: Action Needed to Improve Efficiency and Effectiveness* (GAO-26-109034). https://www.gao.gov/products/gao-26-109034 — Official audit report; not peer-reviewed; identifies persistent backlog and inconsistency issues

## Market Research

**Market Size:** No widely published standalone market-size figure exists for FOIA/public-records-request software specifically; the broader government transparency and records-management software market is valued at several hundred million dollars annually in the US. Key vendors (Granicus, CivicPlus/Tyler) serve thousands of agencies collectively.

**Funding:** Granicus has raised over $800 million in private equity funding (Vista Equity Partners majority owner). CivicPlus acquired NextRequest as part of a broader civic-tech consolidation strategy backed by private equity.

**Pricing Landscape:** Small-agency solutions start around $5,000/year; enterprise contracts with large counties or federal agencies run $50,000–$200,000+/year. Some open-source options exist but require significant IT capacity.

**Key Buyer Personas:** City/county clerks, FOIA officers at federal agencies, state agency general counsels, police department records units, public university compliance offices.

**Notable Trends:** AI-assisted redaction is becoming a differentiator; federal pressure to reduce backlogs (GAO-26-109034) is driving procurement; consolidation among civic-tech vendors (CivicPlus, Granicus, Tyler) is narrowing the competitive field; growing use of FOIA data by commercial brokers is creating new load on agency systems.

## AI-Native Opportunity

- Automated redaction of PII and exempt content using fine-tuned NER models, cutting manual review time by 60–80% vs. current semi-manual workflows
- Intelligent triage and routing: classify incoming requests by topic, likely exemptions, and estimated fulfilment cost before a human touches the file
- Proactive disclosure suggestions: scan agency document repositories and flag records likely to satisfy future requests, reducing repeat filings
- Requester chatbot: guide citizens through the request process, check status, and surface publicly available records before a formal request is even submitted
- Backlog prediction and SLA alerting: ML models trained on historical processing times to flag at-risk requests before statutory deadlines are breached
