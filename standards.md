# Standards & API Reference

> Project: Public Records Request System · Generated: 2026-05-03

## Industry Standards & Specifications

### Statutory & Regulatory Framework

- **Freedom of Information Act (FOIA), 5 U.S.C. § 552**
  URL: https://www.foia.gov/foia-statute.html
  The primary US federal statute mandating disclosure of executive-branch records. Sets the 20-business-day response window, nine exemption categories, and fee waiver criteria. Any system serving federal agencies must model its workflow around these requirements.

- **FOIA Improvement Act of 2016**
  URL: https://www.congress.gov/bill/114th-congress/senate-bill/337
  Amended FOIA to mandate a centralised National FOIA Portal (FOIA.gov), require proactive disclosure of frequently requested records, and restrict use of the deliberative-process exemption (b)(5) to documents within 25 years. Software must support proactive-disclosure flagging and FOIA.gov API interoperability.

- **OMB Memorandum M-19-10 (FOIA.gov Interoperability)**
  URL: https://www.whitehouse.gov/wp-content/uploads/2019/04/M-19-10.pdf
  Requires all federal agencies to become interoperable with FOIA.gov by accepting requests either via the FOIA.gov API or through an agency-designated email inbox. Sets the technical baseline for federal system integration.

- **OMB Memorandum M-19-21 (Electronic Records Management)**
  Requires federal agencies to manage email and other electronic records in electronic form; drives demand for systems capable of ingesting, indexing, and processing electronic records at scale.

- **NARA 36 CFR Chapter XII (Federal Records Management)**
  URL: https://www.ecfr.gov/current/title-36/chapter-XII/subchapter-B
  National Archives regulations governing retention schedules, disposition authorities, and records scheduling. Software must support configurable retention policies tied to NARA-approved schedules (General Records Schedules and agency-specific SF-115 authorities).

- **State Public Records Acts / Sunshine Laws (50 state variants)**
  Each US state has distinct open-records law with different response windows (commonly 5–10 business days), exemption structures, and fee schedules. A multi-jurisdiction system must support configurable jurisdiction profiles for statutory parameters.

---

### ISO Standards

- **ISO/IEC 27001:2022 — Information Security Management Systems**
  URL: https://www.iso.org/standard/27001
  The internationally recognised standard for information security management. Relevant to any cloud-hosted public records platform storing government records and PII. FedRAMP requires controls aligned to NIST SP 800-53, which maps closely to ISO 27001.

- **ISO 15489-1:2016 — Records Management**
  URL: https://www.iso.org/standard/62542.html
  Defines principles and requirements for the creation, capture, and management of records in all formats. Establishes concepts of authenticity, reliability, integrity, and usability for managed records — the same attributes required for legally defensible FOIA production.

- **ISO 30300 Series — Management Systems for Records**
  URL: https://www.iso.org/committee/54612.html
  Supplements ISO 15489 with a management-system framework for records; supports integration of records management requirements into organisational governance, relevant to agencies seeking formal records governance certification.

---

### W3C & IETF Standards

- **W3C WCAG 2.1 Level AA**
  URL: https://www.w3.org/TR/WCAG21/
  Web Content Accessibility Guidelines. Section 508 of the Rehabilitation Act (revised 2018) incorporates WCAG 2.0 AA by reference, and the 2024 ADA Title II rule requires state/local governments to meet WCAG 2.1 AA for public web portals (deadline April 2026 for larger jurisdictions). All citizen-facing portal pages must comply.

- **Section 508, Rehabilitation Act (36 CFR Part 1194)**
  URL: https://www.access-board.gov/ict/
  US federal law requiring federal agencies and federally funded organisations to make electronic and information technology accessible. Applies directly to any FOIA software procured by or for federal agencies.

- **RFC 9110 — HTTP Semantics**
  URL: https://www.rfc-editor.org/rfc/rfc9110
  The current consolidated HTTP/1.1 and HTTP semantics specification. Foundational for REST API design, including the FOIA.gov Agency API and any public-facing request or status APIs.

- **RFC 7617 — The 'Basic' HTTP Authentication Scheme**
  URL: https://www.rfc-editor.org/rfc/rfc7617
  Referenced in government API patterns; any agency API supporting basic auth must implement this correctly, though modern deployments prefer OAuth 2.0 / API keys.

- **RFC 8288 — Web Linking**
  URL: https://www.rfc-editor.org/rfc/rfc8288
  Defines link relations used in REST APIs for pagination, related resources, and hypermedia navigation — relevant for FOIA.gov API compliance (JSON API standard with link relations).

---

### Data Model & API Specifications

- **FOIA.gov RESTful HTTPS Agency API Specification**
  URL: https://www.foia.gov/developer/agency-api/
  The official DOJ specification describing how agencies must expose an API endpoint to receive FOIA requests from the National FOIA Portal. Defines the JSON payload structure for request intake (requester info, description, fee waiver requests, attachments) and acknowledgement responses. Compliance is required under OMB M-19-10.

- **FOIA Annual Report XML Schema (NIEM-conformant)**
  URL: https://www.foia.gov/developer/
  Standardised XML schema for representing and exchanging agency FOIA annual report data, conforming to the National Information Exchange Model (NIEM). Used by FOIAXpress and Tyler Technologies for automated DOJ Annual Report generation.

- **NIEM (National Information Exchange Model) — NIEMOpen**
  URL: https://www.niem.gov/
  An OASIS Open Project providing a common vocabulary and XML/JSON schema framework for government data exchange. The FOIA Annual Report schema is NIEM-conformant. NIEM Version 6.0 supports both XML and JSON serialisations.

- **JSON API Specification**
  URL: https://jsonapi.org/
  The FOIA.gov Agency Component API follows the JSON API standard (leveraging the Drupal JSON API module). Systems integrating with FOIA.gov must produce and consume JSON API-compliant payloads.

- **OpenAPI Specification 3.1**
  URL: https://spec.openapis.org/oas/v3.1.0
  The world standard for describing RESTful APIs. UK Government Digital Service recommends OpenAPI 3 for all government APIs. Any public-facing FOIA system API (request intake, status, document release) should be documented with an OpenAPI 3.1 specification.

---

### Security & Authentication Standards

- **NIST SP 800-53 Rev. 5 — Security and Privacy Controls**
  URL: https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final
  The definitive US government security controls catalogue (1,189 controls across 20 families). FedRAMP Moderate and High authorisations use 800-53 Rev. 5 control baselines. Any FOIA software targeting federal agencies must demonstrate alignment with applicable control families including Access Control (AC), Audit and Accountability (AU), Configuration Management (CM), and PII Processing and Transparency (PT).

- **FedRAMP (Federal Risk and Authorization Management Program)**
  URL: https://www.fedramp.gov/
  GSA program providing standardised cloud security assessment and authorisation for federal procurement. FedRAMP Moderate authorization is held by Casepoint, Tyler Technologies FOIA, and ArkCase — a competitive differentiator for federal contracts. Achieving FedRAMP Moderate requires demonstrating compliance with ~325 NIST 800-53 controls.

- **RFC 6749 — OAuth 2.0 Authorization Framework**
  URL: https://www.rfc-editor.org/rfc/rfc6749
  The standard authorisation protocol for delegated API access. Government APIs (including FOIA.gov) use OAuth 2.0 / API keys for controlling access to agency endpoints. Any developer-facing API for a FOIA system should support OAuth 2.0.

- **OpenID Connect 1.0 (OIDC)**
  URL: https://openid.net/specs/openid-connect-core-1_0.html
  Identity layer on top of OAuth 2.0, used for federated login in government portals. FedRAMP-compliant systems commonly implement SAML 2.0 or OIDC for agency single sign-on (SSO) integration with existing identity providers.

- **NIST SP 800-63B — Digital Identity Guidelines (Authentication)**
  URL: https://pages.nist.gov/800-63-3/sp800-63b.html
  Defines authenticator assurance levels (AAL1–AAL3) for government digital services. Public-facing requester portals typically require AAL1; staff-facing agency portals with access to exempt records require AAL2 (multi-factor authentication).

- **CUI (Controlled Unclassified Information) Program — 32 CFR Part 2002**
  URL: https://www.archives.gov/cui
  NARA-administered program defining how agencies handle, mark, and protect CUI — categories of government information that require safeguarding but are not classified. Records under FOIA review frequently contain CUI; software must support CUI marking, access control, and disposition rules.

---

### MCP Server Specifications

Not directly applicable to the core FOIA management workflow. An AI-native FOIA tool built on an LLM agent architecture could expose document review, exemption classification, or redaction capabilities as MCP tools, enabling integration with Claude or other LLM assistants. If implemented:

- **Model Context Protocol (MCP) Specification**
  URL: https://modelcontextprotocol.io/specification
  Enables AI agents to call tools exposed by an MCP server. FOIA-relevant MCP tools could include: `classify_exemptions(document_text)`, `detect_pii(document_text)`, `suggest_redactions(document_text, jurisdiction)`, and `check_request_status(request_id)`.

---

## Similar Products — Developer Documentation & APIs

### FOIA.gov (US DOJ National FOIA Portal)

- **Description:** The US federal government's centralised FOIA request portal, enabling citizens to submit requests to any participating federal agency from a single website. Powered by a public REST API.
- **API Documentation:** https://www.foia.gov/developer/
- **Agency API Spec:** https://www.foia.gov/developer/agency-api/ (Swagger/OpenAPI documentation)
- **GitHub (back-end):** https://github.com/usdoj/foia-api
- **GitHub (front-end / spec):** https://github.com/usdoj/foia.gov
- **Standards:** JSON API, RESTful HTTPS, NIEM-conformant XML for annual reports
- **Authentication:** API key via api.data.gov; agency endpoints restricted to FOIA.gov portal IP range

---

### USCIS FOIA Request and Status API

- **Description:** Immigration agency API allowing third-party immigration case management software vendors to programmatically submit FOIA/Privacy Act requests for Alien File material and check request status.
- **API Documentation:** https://developer.uscis.gov/api/foia-request-and-status
- **Developer Portal:** https://developer.uscis.gov/home (USCIS TORCH API platform)
- **Getting Started:** Developer team registration required; demo scheduling available
- **Standards:** REST/JSON
- **Authentication:** TORCH API developer account and API key; OAuth 2.0 token flow

---

### MuckRock API

- **Description:** Requester-side FOIA platform with a documented REST API and Python SDK for programmatic request filing, status tracking, and archive querying. Largest public FOIA request archive in the US.
- **API Documentation:** https://www.muckrock.com/api/ and https://help.muckrock.com
- **SDK / Libraries:** python-muckrock (Python wrapper, released February 2025)
- **GitHub:** https://github.com/MuckRock (includes API-examples repository)
- **Developer Guide:** https://www.muckrock.com/news/archives/2025/may/06/build-your-next-project-using-muckrocks-tools/
- **Standards:** REST/JSON; rate limited to 1 req/s (burst to 20 req/s)
- **Authentication:** API token from user profile (session-based token, not OAuth 2.0)

---

### Alaveteli (mySociety)

- **Description:** Open-source FOI request portal (MIT licence) used by 30+ country-specific deployments (WhatDoTheyKnow UK, RightToKnow AU, etc.). Both a read API (Atom/JSON) and write API (request creation) are documented.
- **API Documentation:** https://alaveteli.org/docs/developers/api/
- **Developer Docs:** https://alaveteli.org/docs/developers/
- **GitHub:** https://github.com/mysociety/alaveteli
- **SDK / Libraries:** No official SDK; Ruby on Rails application; PostgreSQL back-end
- **Standards:** Atom (XML) feeds; JSON responses; no OpenAPI specification documented
- **Authentication:** API key required for write API (request creation); read API is public

---

### ArkCase (Armedia)

- **Description:** Open-source (Apache 2.0) case management platform with a FOIA module, FedRAMP Moderate ATO, deployed by federal agencies including EEOC. Spring Boot REST API back-end.
- **API Documentation:** https://armedia.com/technology/arkcase-as-a-technology-partner/
- **GitHub:** https://github.com/ArkCase/ArkCase
- **Developer Guide:** Community documentation on GitHub; Armedia provides implementation support
- **Standards:** REST/JSON; BPMN 2.0 workflow engine; Alfresco ECM integration
- **Authentication:** Role-based access control; SAML/LDAP integration for agency SSO

---

### GovQA / Granicus Platform API

- **Description:** Commercial FOIA and public records management platform. The broader Granicus platform exposes SOAP and REST APIs primarily for automating backend tasks (not public-facing FOIA request intake).
- **API Documentation:** https://support.granicus.com/s/article/API-Integration (requires Granicus customer account)
- **SDK / Libraries:** .NET SDK (SOAP): https://github.com/Granicus/platform-api-net
- **Developer Guide:** https://developers.govdelivery.com/ (GovDelivery/Communications Cloud API)
- **Standards:** REST and SOAP; HTTP integrations for event-driven webhooks
- **Authentication:** Customer account credentials; API key

---

### Laserfiche (ECM Integration Partner)

- **Description:** Enterprise content and records management platform widely integrated with FOIA software (NextRequest/CivicPlus, JustFOIA, ArkCase). Exposes a documented REST API for document management operations.
- **API Documentation:** https://developer.laserfiche.com/
- **Getting Started:** https://developer.laserfiche.com/docs/getting-started/guide_getting-started/
- **SDK / Libraries:** Laserfiche SDK for .NET, Java; REST client libraries
- **Standards:** REST/JSON; OpenAPI specification published at developer.laserfiche.com
- **Authentication:** OAuth 2.0 (Laserfiche Cloud); NTLM/Windows auth (on-premises)

---

### Logikcull / Reveal Data

- **Description:** Cloud-based eDiscovery and FOIA document review platform with AI redaction, PII detection, and collection connectors for Google Vault, Slack, Microsoft 365, and Box.
- **API Documentation:** Not publicly documented; available to enterprise customers under contract
- **Connectors:** Google Vault, Slack, Microsoft 365 (Exchange/Teams/OneDrive), Box
- **Standards:** REST/JSON (inferred from modern SaaS architecture); no OpenAPI spec published
- **Authentication:** Session-based for web UI; API details under NDA for enterprise customers

---

## Notes

**Gaps in standard coverage:**
- No ISO standard specifically addresses FOIA or public records request processing as a workflow; the closest applicable standard is ISO 15489 (records management) supplemented by US-specific statutory requirements.
- The FOIA.gov Agency API specification has not been updated to OpenAPI 3.x; it remains informally documented via Swagger UI. An AI-native tool targeting federal deployments should implement against the current spec and be prepared for future updates as FOIA.gov evolves.
- NIEM is transitioning from XML-only to a Metamodel supporting JSON; projects building FOIA annual report generation should monitor NIEMOpen (https://niemopen.org/) for JSON-based schema availability.

**Emerging areas:**
- AI Act (EU, 2024–2026 phased implementation): if an AI-native FOIA tool is deployed in EU jurisdictions or by EU member state agencies, the AI Act's transparency and human oversight requirements for high-risk AI systems (government decision-making) will apply to automated redaction and exemption classification features.
- Zero-trust architecture (NIST SP 800-207): increasingly required by US federal agencies under Executive Order 14028 (Improving the Nation's Cybersecurity, 2021); any federal FOIA system should be designed with zero-trust network access principles.
