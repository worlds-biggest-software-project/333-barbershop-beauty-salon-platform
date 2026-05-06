# Standards & API Reference

> Project: Barbershop & Beauty Salon Platform · Generated: 2026-05-03

## Industry Standards & Specifications

### ISO Standards

**ISO/IEC 27001:2022 — Information Security Management Systems**
URL: https://www.iso.org/standard/27001
The globally recognised standard for establishing and maintaining an Information Security Management System (ISMS). Salon platforms handle sensitive personal data (contact details, payment tokens, service history) and face enterprise procurement requirements that increasingly demand ISO 27001 certification as a baseline.

**ISO/IEC 27018:2019 — Protection of Personally Identifiable Information in Public Clouds**
URL: https://www.iso.org/standard/76559.html
Extends ISO 27001 to cover PII handling in cloud services. Directly relevant to a multi-tenant SaaS platform storing client profiles, appointment history, and colour formula records across many operators.

**ISO/IEC 29101:2018 — Privacy Architecture Framework**
URL: https://www.iso.org/standard/75293.html
Provides a reference architecture for privacy protection in ICT systems. Applicable when designing the client-data model and consent-management features, particularly for GDPR and CCPA compliance.

---

### W3C & IETF Standards

**RFC 5545 — Internet Calendaring and Scheduling Core Object Specification (iCalendar)**
URL: https://datatracker.ietf.org/doc/html/rfc5545
Defines the iCalendar format (VCALENDAR, VEVENT, VTODO components) used by Google Calendar, Apple Calendar, Outlook, and others. Essential for calendar sync features: any appointment created in the platform should be exportable as a .ics file or pushed to client calendars via CalDAV.

**RFC 4791 — Calendaring Extensions to WebDAV (CalDAV)**
URL: https://datatracker.ietf.org/doc/html/rfc4791
Protocol for reading and writing calendar data over HTTP. Enables two-way sync with Google Calendar, Apple Calendar, and Exchange; widely used by Vagaro, Timely, and Mangomint.

**RFC 6350 — vCard Format Specification**
URL: https://datatracker.ietf.org/doc/html/rfc6350
Standard for representing contact information in a structured format. Relevant to client profile import/export — vCard is the universal format for moving contact records between CRM systems and mobile address books.

**RFC 6749 — OAuth 2.0 Authorization Framework**
URL: https://datatracker.ietf.org/doc/html/rfc6749
The industry standard for token-based API authorisation. All major salon software APIs (Boulevard GraphQL, Booksy REST, Zenoti REST) use OAuth 2.0 for third-party developer access. The platform's own API should support OAuth 2.0 client credentials flow for server-to-server integrations and authorisation code flow for user-authorised third-party apps.

**RFC 7519 — JSON Web Token (JWT)**
URL: https://datatracker.ietf.org/doc/html/rfc7519
JWT is used by Booksy's Public API for authentication (Bearer tokens with 10-hour access token lifetimes). The platform's own API authentication scheme should follow JWT best practices with appropriate token expiry and refresh flows.

**RFC 7231 — HTTP/1.1 Semantics and Content**
URL: https://datatracker.ietf.org/doc/html/rfc7231
Defines HTTP method semantics, status codes, and content negotiation. A REST API for a booking platform should strictly follow RFC 7231 for predictable behaviour across integrations.

**W3C JSON-LD 1.1**
URL: https://www.w3.org/TR/json-ld11/
Linked Data format used by schema.org structured data. The platform's business listing pages should use JSON-LD to embed schema.org markup for improved search engine indexing and Google Reserve integration.

---

### Data Model & API Specifications

**Schema.org BeautySalon and HealthAndBeautyBusiness**
URL: https://schema.org/BeautySalon and https://schema.org/HealthAndBeautyBusiness
W3C-maintained vocabulary for describing local businesses. BeautySalon is a subtype of HealthAndBeautyBusiness > LocalBusiness. Implementing JSON-LD markup with these types on business profile pages enables rich results in Google Search, supports Google Maps integration, and is required for full Reserve with Google functionality. Key properties: name, address, telephone, openingHours, makesOffer, priceRange.

**OpenAPI Specification 3.1**
URL: https://spec.openapis.org/oas/v3.1.0
The de-facto standard for describing RESTful APIs. All major salon APIs (Zenoti, Vagaro, Booksy) either publish OpenAPI/Swagger documents or maintain Postman collections. The platform's public API should ship an OpenAPI 3.1 document to enable auto-generated SDKs, API explorer tools, and partner integrations.

**GraphQL — June 2018 Specification**
URL: https://spec.graphql.org/June2018/
Boulevard uses GraphQL (rather than REST) for its developer API, allowing clients to query exactly the data they need. GraphQL is well-suited for a booking platform's complex relational data model (appointments → clients → staff → services → inventory). An AI-native platform building a rich integration layer should evaluate GraphQL as an alternative or complement to REST.

**Stripe API (Payment Processing)**
URL: https://stripe.com/docs/api
The most widely used payment infrastructure provider for salon software (GlossGenius, Booksy, Squire, and Timely all use Stripe under the hood). Key APIs: Payment Intents, Setup Intents (card-on-file), Terminal SDK (in-person payments), Connect (multi-party payments for marketplace models). Stripe's webhooks are the standard for real-time payment event notifications.

**Google Maps Booking API (Reserve with Google)**
URL: https://developers.google.com/maps-booking
Allows scheduling aggregators to surface availability and accept bookings directly from Google Search and Maps. The API uses REST/JSON with OAuth 2.0 service account authentication. The beauty vertical is explicitly supported, with service attributes like "Service Type" (Haircut, Colour, Style). Last updated March 2026; actively maintained. Quota: 1,500 queries per minute per Cloud Project.

---

### Security & Authentication Standards

**PCI DSS 4.0 — Payment Card Industry Data Security Standard**
URL: https://www.pcisecuritystandards.org/document_library/
Mandatory for any platform that processes, stores, or transmits cardholder data. Using tokenised payment processing via Stripe or a similar gateway reduces PCI DSS scope to SAQ A (the simplest tier). The platform must never store raw card numbers; all card data must be tokenised at the payment processor before reaching the application layer.

**OWASP Top 10 (2021)**
URL: https://owasp.org/www-project-top-ten/
The authoritative reference for web application security risks. Particularly relevant are: A01 Broken Access Control (multi-tenant data isolation between salon operators), A02 Cryptographic Failures (encrypting client PII at rest and in transit), and A07 Identification and Authentication Failures (securing staff login and API tokens).

**GDPR — General Data Protection Regulation (EU) 2016/679**
URL: https://gdpr.eu/
Applies to any platform serving EU-based operators or clients. Key implications: lawful basis for processing client appointment data, right to erasure (a client must be deletable from the system), data portability (client history export in machine-readable format), and 72-hour breach notification. Salon software platforms operating in Europe should maintain a Data Processing Agreement template for operator customers.

**CCPA — California Consumer Privacy Act**
URL: https://oag.ca.gov/privacy/ccpa
Grants California residents rights over their personal data. Similar in effect to GDPR for US businesses: right to know what data is collected, right to delete, right to opt out of data sale. An opt-out mechanism must be provided if client data is ever shared with third-party marketing services.

**SOC 2 Type II**
URL: https://www.aicpa.org/resources/landing/system-and-organization-controls-soc-suite-of-services
While not a regulatory requirement, SOC 2 Type II attestation has become a de facto procurement requirement for selling to enterprise and franchise operators. The five Trust Services Criteria most relevant are Security, Availability, and Confidentiality. Achieving SOC 2 Type II signals readiness for Zenoti-tier enterprise clients.

**OpenID Connect 1.0**
URL: https://openid.net/specs/openid-connect-core-1_0.html
Builds on OAuth 2.0 to provide identity layer for user authentication. Enables SSO integration with Google Workspace, Okta, and Microsoft Entra ID — increasingly required by multi-location salon chains managing staff access at scale. Boulevard's enterprise tier integrates Okta SSO using OpenID Connect.

---

### MCP Server Specifications

The Model Context Protocol (MCP) provides a standard interface for AI agents to interact with external systems. A barbershop/salon platform has several natural MCP surface areas:

**MCP Tool: appointment-lookup** — Retrieve upcoming and recent appointments for a named client or staff member; surface colour formulas and service notes in-context for an AI assistant.

**MCP Tool: availability-query** — Query open slots across staff members and locations for a given service and date range; useful for AI receptionist or voice-booking agents.

**MCP Tool: client-profile-read** — Read a client record including preferences, allergy flags, and last formula; enables context injection for AI-assisted consultations.

**MCP Tool: booking-create** — Create or update an appointment; required for a fully functional AI receptionist that can complete the booking without human handoff.

MCP documentation: https://modelcontextprotocol.io/docs

---

## Similar Products — Developer Documentation & APIs

### Boulevard

- **Description:** Business management platform for premium salons and spas; GraphQL API with webhooks is one of the most developer-friendly in the category.
- **API Documentation:** https://developers.joinblvd.com/2020-01/admin-api/overview
- **SDKs/Libraries:** JavaScript booking SDK — https://github.com/Boulevard/book-sdk (open source)
- **Developer Guide:** https://www.joinblvd.com/features/api
- **Standards:** GraphQL (June 2018 spec), OAuth 2.0, webhooks over HTTPS
- **Authentication:** OAuth 2.0 (API package required; contact support@blvd.co for credentials)

---

### Vagaro

- **Description:** Multi-vertical salon, spa, and fitness platform with built-in payroll and a consumer marketplace; REST API and webhook support available as paid add-ons.
- **API Documentation:** https://docs.vagaro.com/public/docs/introduction
- **SDKs/Libraries:** No official SDKs; REST/JSON over HTTPS
- **Developer Guide:** https://docs.vagaro.com — Webhooks: https://docs.vagaro.com/public/docs/webhook-events
- **Standards:** REST/JSON, OpenAPI, HTTPS POST for webhooks
- **Authentication:** API key (Enterprise agreement required); OAuth 2.0 for user-authorised flows

---

### Zenoti

- **Description:** Enterprise-grade salon and spa platform serving franchise chains including Sport Clips and European Wax Center; REST API with comprehensive endpoint coverage.
- **API Documentation:** https://docs.zenoti.com/docs/overview
- **SDKs/Libraries:** Postman collection — https://documenter.getpostman.com/view/16255247/2s8YmKSPwT; Apiary mirror — https://zenotiopenapi.docs.apiary.io/
- **Developer Guide:** https://docs.zenoti.com/docs/create-the-backend-app-and-generate-a-new-api-key
- **Standards:** REST/JSON, OpenAPI-compatible; JWT and API key authentication
- **Authentication:** API key (generated from Zenoti admin) or bearer token (OAuth 2.0 flow)

---

### Booksy

- **Description:** Consumer-first booking marketplace operating in 150+ countries; REST API with multiple authentication methods, actively documented for third-party developers.
- **API Documentation:** https://docs.booksy.com/
- **SDKs/Libraries:** Postman collection available via Postman API Network (search "Booksy")
- **Developer Guide:** https://docs.booksy.com/v01.html
- **Standards:** REST/JSON, RFC 7231 HTTP semantics, rate limiting (HTTP 429 on excess)
- **Authentication:** JWT Bearer tokens (10-hour access token, 24-hour refresh token); OAuth 2.0 password grant; RSA key-pair Basic Authorization

---

### Mindbody

- **Description:** The largest consumer wellness marketplace globally; powers fitness studios, spas, and salons; open developer portal with sandbox environment available to all registered developers.
- **API Documentation:** https://developers.mindbodyonline.com/
- **SDKs/Libraries:** Official REST clients documented in developer portal
- **Developer Guide:** Developer registration → sandbox access → live approval process via developer portal
- **Standards:** REST/JSON, OpenAPI, HTTPS
- **Authentication:** API key ("Source Credentials" system); OAuth 2.0 for user-authorised integrations

---

### Fresha

- **Description:** Zero-subscription salon and barbershop platform with a dual-sided marketplace; limited public API — primarily exposes data connectors for business intelligence rather than a full developer API.
- **API Documentation:** https://apitracker.io/a/fresha/apis (third-party tracker; no official public developer portal as of 2026)
- **SDKs/Libraries:** Internal tooling on GitHub at https://github.com/surgeventures — not a public integration SDK
- **Developer Guide:** Data Connector help article: https://www.fresha.com/help-center/knowledge-base/reports/479-available-data-connector-tools
- **Standards:** Internal; no publicly documented API standard
- **Authentication:** Not publicly documented; API access requires direct contact with Fresha partnerships team

---

### Google Maps Booking API (Reserve with Google)

- **Description:** Google's scheduling aggregator integration enabling bookings directly from Google Search and Maps; the beauty vertical is explicitly supported with service attribute types.
- **API Documentation:** https://developers.google.com/maps-booking/reference/maps-booking-api/rest
- **SDKs/Libraries:** REST/JSON via HTTPS; no language-specific SDK
- **Developer Guide:** End-to-end integration guide for beauty: https://developers.google.com/maps-booking/verticals/beauty/guides/end-to-end-integration/setup
- **Standards:** REST/JSON, OAuth 2.0 service account authentication, OpenAPI-compatible
- **Authentication:** OAuth 2.0 service account; 1,500 QPM quota per Cloud Project after enablement

---

### Stripe Terminal + Connect

- **Description:** In-person payment hardware SDK and multi-party payment infrastructure; underpins the payment layer of GlossGenius, Booksy, Squire, and Timely.
- **API Documentation:** https://stripe.com/docs/api — Terminal: https://stripe.com/docs/terminal — Connect: https://stripe.com/docs/connect
- **SDKs/Libraries:** JavaScript, Python, Ruby, PHP, Java, Go, .NET, iOS (Swift), Android (Kotlin/Java)
- **Developer Guide:** https://stripe.com/docs/payments/accept-a-payment
- **Standards:** REST/JSON; TLS 1.2+ enforced; webhooks over HTTPS; PCI DSS SAQ A compliant when used as recommended
- **Authentication:** API key (publishable and secret); Stripe-Signature HMAC verification for webhooks

---

## Notes

**WhatsApp Business API (Meta):** The most-requested missing integration across the salon software category. The Cloud API (https://developers.facebook.com/docs/whatsapp/cloud-api) allows sending appointment reminders and two-way messaging via WhatsApp without a dedicated business phone. Requires Meta Business verification. Given that no major salon platform has implemented this yet, early adoption would be a meaningful differentiator.

**Colour Formula Standards:** There is no universally adopted open standard for storing hair colour formulas. Platforms implement proprietary schemas. The closest community resources are vendor-specific formats from Vish (https://getvish.com) and Salon Intelligence (https://salonintelligence.org). A portable, open schema for colour formulas (containing developer volume, base shade, tone, timing, and application notes) represents an opportunity to establish a de-facto standard.

**Cosmetology Licence Data:** No public API or machine-readable feed exists for state cosmetology licensing board data in the US. Licence verification requires scraping or manual entry per state. The Cosmetology Compact (nine states as of 2026) could eventually provide a federated verification API, but this does not yet exist. Licence tracking in any platform is therefore dependent on manual data entry or operator self-reporting.

**Emerging: EU Digital Identity (EUDI Wallet):** Some European salon platforms are exploring digital identity verification for clients booking medical-aesthetic services. The EUDI Wallet framework may become relevant for age and identity verification by 2027-2028 but has not yet reached adoption in this vertical.
