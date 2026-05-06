# Barbershop & Beauty Salon Platform — Feature & Functionality Survey

> Candidate #333 · Researched: 2026-05-04

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Fresha | Cloud SaaS, dual-sided marketplace | Commercial — zero subscription, commission on payments | https://www.fresha.com |
| Mangomint | Cloud SaaS | Commercial — subscription from $165/mo | https://www.mangomint.com |
| Squire | Cloud SaaS, barber-native | Commercial — subscription | https://getsquire.com |
| Boulevard | Cloud SaaS, upscale focus | Commercial — subscription, enterprise tier | https://www.joinblvd.com |
| Vagaro | Cloud SaaS, multi-vertical | Commercial — subscription from $30/mo | https://www.vagaro.com |
| GlossGenius | Cloud SaaS, mobile-first | Commercial — subscription from $24/mo | https://glossgenius.com |
| Barberly | Cloud SaaS, barbershop-native | Commercial — subscription | https://www.barberly.com |
| Zenoti | Cloud SaaS, enterprise | Commercial — custom enterprise pricing | https://www.zenoti.com |
| Timely | Cloud SaaS | Commercial — subscription from $11/user/mo | https://www.gettimely.com |
| Mindbody | Cloud SaaS, wellness/fitness | Commercial — subscription, enterprise tier | https://www.mindbodyonline.com |

---

## Feature Analysis by Solution

### Fresha

**Core features**
- Appointment calendar with multi-staff and multi-location views
- Online booking via website widget, Instagram, Facebook, and Google Business Profile
- Integrated payment processing with card tokenisation and no-show deposit collection
- Unlimited free SMS and email appointment notifications to clients
- Two-way messaging hub (SMS, email, WhatsApp) unified in one inbox
- Product inventory management with supplier ordering and consumption tracking
- Team management: timesheets, clock-in/out, commission tracking
- Loyalty programme and referral campaigns
- Email and SMS marketing campaign builder with smart audience segments (birthday, lapsed client)
- Real-time analytics and financial reporting dashboard

**Differentiating features**
- Zero-subscription pricing model — revenue from payment processing only
- Consumer-facing marketplace with 450,000+ professionals across 120+ countries drives organic discovery
- Memberships with flexible perks, discounts, and exclusive benefits (major 2026 upgrade)
- AI Receptionist that answers client questions from custom FAQs, active outside business hours
- Service and product bundles/packages for treatment plans and gifting

**UX patterns**
- Single-page booking flow optimised for mobile conversion
- Onboarding wizard guides new businesses through service catalogue, staff, and payment setup
- Marketplace profile acts as both business listing and booking page
- Client-facing app for managing bookings and loyalty points

**Integration points**
- Social media booking: Instagram, Facebook, Google
- Payment processing: Fresha Payments (Stripe-backed)
- Data connectors for reporting (CSV, Google Sheets-compatible exports)
- Public API available but with limited third-party developer documentation

**Known gaps**
- Limited open API access for third-party developers
- Advanced payroll and HR features absent (not built for multi-employee enterprises)
- Reporting depth weaker than enterprise competitors
- No native HIPAA compliance for medspa use cases

**Licence / IP notes**
- Proprietary SaaS; no open-source components
- Marketplace network effect creates strong lock-in

---

### Mangomint

**Core features**
- Appointment calendar with colour-coded staff lanes and drag-and-drop rescheduling
- Online booking with customisable widget and optional pre-payment capture
- POS with inventory management and product sales
- Client profiles with visit history, formulas, notes, and photo documentation
- HIPAA-compliant intake forms, treatment charting, consent forms, and before/after photos
- Team management: permissions, payroll, commission tiers, time tracking
- Email and SMS automated campaigns

**Differentiating features**
- Express Booking™ — books multiple services with multiple providers in one optimised flow, eliminating back-and-forth slot hunting
- Virtual waiting room for walk-in management
- Highest user satisfaction rating on G2 and Capterra (4.9/5.0 as of 2026)
- HIPAA-compliant client charting — suitable for medspa and skincare clinic cross-over
- Mangomint Connect add-on: phone calls, texting, and web chat handled inside the platform

**UX patterns**
- Fastest, most polished interface in the category (repeatedly cited in reviews)
- Progressive disclosure: basic booking up front, advanced features behind secondary menus
- Role-based staff accounts so front-desk sees only what they need

**Integration points**
- Zapier for workflow automation
- Payroll integrations (Gusto, ADP compatible via export)
- REST API for enterprise customers
- Payment processing via integrated Mangomint Payments

**Known gaps**
- Premium price point ($165–$375/mo) excludes solo practitioners and micro-businesses
- No consumer marketplace — relies entirely on operator-driven booking
- Limited open developer API access

**Licence / IP notes**
- Proprietary SaaS; Express Booking™ is a branded and potentially protectable UX patent candidate
- No open-source components

---

### Squire

**Core features**
- Appointment scheduling and online booking with embeddable website widget
- Walk-in queue management with real-time wait estimation
- Integrated POS: chip, swipe, Apple Pay, Google Pay
- Commission management and staff timeclock
- Inventory tracking and product sales
- Loyalty programme and client messaging
- Multi-location management
- Custom analytics and reporting by metric

**Differentiating features**
- Built exclusively for barbershops — walk-in queue is a first-class feature, not an afterthought
- Barber marketplace visible to consumers for discovery
- Live queue board display for in-shop TV
- Financial services layer: business banking, instant payouts, and barber-specific payroll (via Bond partnership)
- Tip management built into checkout flow

**UX patterns**
- Consumer app with barber discovery and live queue join
- Staff app for managing queue and appointments on mobile
- Front-desk tablet mode for kiosk check-in

**Integration points**
- Square (payments), QuickBooks (accounting), Google Calendar, Stripe
- Zapier automation
- REST API with webhooks, OpenAPI/Swagger spec, sandbox environment

**Known gaps**
- Desktop web interface significantly less functional than mobile (frequently cited user complaint)
- No barcode scanning or unit-of-measure for inventory (gap for product-heavy shops)
- Limited reporting compared to Mangomint or Zenoti
- Customer support rated below average in multiple 2026 reviews

**Licence / IP notes**
- Proprietary SaaS
- Fintech layer (business banking, payroll) creates regulatory complexity for open-source replication

---

### Boulevard

**Core features**
- Appointment calendar with smart scheduling logic and double-booking prevention
- Online booking with mobile-optimised widget
- POS with integrated contactless and card payments
- Client profiles: SOAP notes, treatment history, photo gallery, average spend tracking, product history
- HIPAA-compliant client data management
- Email and SMS marketing automation linked to live CRM segments
- Inventory management
- Multi-location management and reporting
- Staff commissions, payroll exports, and permissions

**Differentiating features**
- Precision Scheduling™ logic minimises gaps and maximises revenue per chair
- "Offset" pricing model — optionally passes credit card processing fees to clients (3% client / 1% business)
- Enterprise-tier open API and webhooks for custom integrations
- HIPAA compliance positions it for medspa adjacency
- Dedicated developer portal with booking SDK (open source JavaScript SDK on GitHub)

**UX patterns**
- Upscale visual language reflecting premium salon brand positioning
- Contactless self-checkout flow reduces front-desk friction at end of visit
- Client-facing booking page with service menu, pricing, and stylist profiles

**Integration points**
- Shopify (retail), Zapier, Extole (referral), custom apps via open API
- Boulevard booking SDK: `github.com/Boulevard/book-sdk` (MIT-like open licence)
- Developer portal at `developers.joinblvd.com` with sandbox

**Known gaps**
- US-only; no international payment rails or multi-currency support
- Higher pricing than competitors at comparable feature set
- API access gated to Enterprise tier only

**Licence / IP notes**
- Proprietary SaaS platform; booking SDK is open source (GitHub: Boulevard/book-sdk)
- No known patent filings on scheduling logic but branding of "Precision Scheduling" noted

---

### Vagaro

**Core features**
- Appointment scheduling and online booking with marketplace exposure
- POS with product sales and inventory management
- Payroll processing (built-in, not an add-on)
- Bookkeeping integration
- Email and text campaign marketing
- Customisable business website builder
- Membership and package management
- Client database with visit history and preferences
- Multi-location management

**Differentiating features**
- Consumer-facing marketplace drives organic discovery at no extra charge
- Built-in payroll — no third-party integration required
- Most feature-complete platform at the lowest price point ($30–$90/mo for any team size)
- AI-powered content creation for marketing copy
- Broad vertical coverage: salons, spas, barbershops, fitness, health

**UX patterns**
- Slightly dated interface compared to Mangomint or Boulevard but comprehensive
- Feature density can overwhelm new users; relies on knowledge base and support

**Integration points**
- Xero and QuickBooks for accounting
- Zoom for virtual consultations
- Public API and webhooks (paid add-on at $10/mo); developer docs at `docs.vagaro.com`
- Zapier for automation

**Known gaps**
- Interface dated compared to newer competitors
- Checkout flow and scheduling have usability friction reported by multiple reviewers
- Occasional downtime and reliability concerns
- Webhook access costs extra and is limited to paid tiers

**Licence / IP notes**
- Proprietary SaaS; no open-source components

---

### GlossGenius

**Core features**
- Online booking without requiring client app download or account creation
- Appointment scheduling and calendar
- Integrated payment processing with custom card readers
- Client profiles with automatic update and appointment history
- Email and SMS marketing campaigns
- Review management and social media post templates
- Waitlist management
- Time tracking and payroll (Gold plan)
- Membership and package management

**Differentiating features**
- Highest aesthetic quality in the category — Instagram-worthy booking pages and receipts
- Free card reader included with subscription
- No-show protection with deposit and cancellation fee collection
- Frictionless client booking: zero app download, zero account creation
- Designed around solo practitioners and small teams (intentionally lean feature set)

**UX patterns**
- Mobile-first design throughout
- Opinionated simplicity: deliberately excludes complex features to reduce cognitive load
- Elegant branded booking page acts as a lightweight landing page for practitioners

**Integration points**
- Google Reviews integration
- Payment processing: GlossGenius Payments
- Limited third-party integrations; no public API documented

**Known gaps**
- No inventory management
- No advanced reporting beyond basics
- No open API or developer access
- Intentionally excludes features needed by multi-staff operations (limited team scheduling)
- US-only

**Licence / IP notes**
- Proprietary SaaS; no open-source components

---

### Barberly

**Core features**
- Appointment scheduling with online booking widget
- Branded mobile app (white-label) for the barbershop
- Custom barbershop website with booking integration
- Self-check-in kiosk running on iOS or Android tablet
- TV appointment board — real-time queue and appointment timeline on any browser-connected display
- QR code posters for walk-in booking
- Client notifications (SMS, email, push)
- Loyalty programme and CRM
- POS with product sales

**Differentiating features**
- Self-check-in kiosk is the most fully featured in the category — clients self-select service and barber
- TV appointment board with customisable layout and timeline length for different screen sizes
- Branded white-label mobile app per barbershop — not a shared marketplace app
- QR code physical marketing collateral integrated directly with booking

**UX patterns**
- Walk-in-first design philosophy: kiosk and queue board are primary interfaces, not secondary add-ons
- TV board designed for clients in the waiting area to track their own position

**Integration points**
- Social media booking links
- POS payment processing
- No public API documented; integration surface limited

**Known gaps**
- Limited third-party integrations compared to Vagaro or Boulevard
- No open API for developers
- Payroll and accounting features thin
- Analytics and reporting limited

**Licence / IP notes**
- Proprietary SaaS
- White-label app model may involve Apple/Google Developer account requirements for each client

---

### Zenoti

**Core features**
- Multi-location enterprise scheduling and calendar management
- Online booking with smart slot optimisation
- POS with multi-currency and multi-outlet support
- Full membership lifecycle management (sell, manage, auto-renew)
- Marketing automation on live CRM data (segmented campaigns)
- Inventory management across locations
- Payroll, commissions, and HR management
- Resort PMS integration for hotel spa operations
- Comprehensive multi-location analytics and financial reporting
- Franchise management tools

**Differentiating features**
- AI Workforce: nine purpose-built AI agents for revenue-critical tasks — AI Receptionist (24/7 call answering and booking), AI Scribe (consultation transcription and auto-fill charting), smart churn prediction, chargeback management
- Generated over $1 billion in incremental customer revenue in 2026 through AI recommendations
- True multi-location architecture — not bolted-on from single-location base
- Resort PMS integration for hospitality group spas
- HIPAA compliance for medspa and medical aesthetics crossover

**UX patterns**
- Enterprise onboarding with dedicated implementation team ($5,000–$20,000 setup)
- Role-based access for franchise owners, location managers, front desk, and stylists
- Custom-branded client app per chain

**Integration points**
- REST API at `docs.zenoti.com` / `developer.zenoti.com` with API key and JWT authentication
- Postman collection and Apiary documentation available
- PMS integrations for hotel/resort operators
- Restricted to existing clients and authorised third-party developers — not open to general public

**Known gaps**
- Enterprise-only pricing (no published rates; custom quotes required)
- Overkill complexity for independent operators
- Implementation cost and timeline too high for small businesses
- API access not open to general third-party developers

**Licence / IP notes**
- Proprietary SaaS; no open-source components
- AI Workforce branding likely trademark-protected

---

### Timely

**Core features**
- Appointment calendar with staff lanes and colour coding
- Online client self-booking with 24/7 availability
- SMS and email automated appointment reminders
- Smart rebooking prompts at checkout
- Deposit and prepayment collection
- Integrated POS payments with fast payouts
- 40+ analytics and reporting templates
- Team, room, and equipment management
- Multi-location management

**Differentiating features**
- Per-user pricing model (not per-location) — unusually affordable for multi-staff shops
- Frequent product updates included at no extra cost
- Strong rebooking automation: prompts at checkout and post-appointment follow-up
- New Zealand origin with strong Asia-Pacific user base and AU/NZ compliance

**UX patterns**
- Clean, minimal interface with fast onboarding
- Self-booking flow requires no client account creation
- Mobile app for staff schedule management

**Integration points**
- Xero (accounting)
- Google Calendar two-way sync
- Stripe for payment processing
- Zapier for automation
- No public API documented; REST webhooks available on higher plans

**Known gaps**
- Data export difficult to customise (user complaint)
- Multi-location setup complex for large chains
- No consumer marketplace for organic discovery
- Limited third-party developer access

**Licence / IP notes**
- Proprietary SaaS; no open-source components

---

### Mindbody

**Core features**
- Appointment and class scheduling for wellness businesses
- Online booking with consumer-facing marketplace (Mindbody app with large user base)
- POS with retail product management
- Staff management: payroll, commissions, certifications tracking
- Client membership and package management
- Email and SMS marketing automation
- Mobile check-in and branded app
- Multi-location and franchise management
- Reporting and business analytics

**Differentiating features**
- Largest consumer wellness marketplace in the world — drives organic discovery for fitness, yoga, spas
- AI-powered revenue tools (Messenger[ai] for automated client communications)
- Integrations ecosystem with hundreds of certified third-party apps
- Robust public REST API with sandbox environment open to all developers

**UX patterns**
- Consumer-first marketplace app with location search and instant booking
- Business dashboard designed for studio managers with class and appointment hybrid scheduling

**Integration points**
- Official REST API at `developers.mindbodyonline.com` — open developer portal with free sandbox
- Supports GET, POST, DELETE over HTTPS returning JSON
- Source credentials system: developers register, receive sandbox access, go through live approval process
- Hundreds of certified partner integrations (marketing, analytics, payments, wearables)

**Known gaps**
- Bloated UX for barbershop/hair salon use cases; built for fitness and yoga studios first
- Customer support quality has declined as company scaled
- Pricing complex and expensive for small operators
- Not purpose-built for walk-in queue management

**Licence / IP notes**
- Proprietary SaaS; consumer app and marketplace are proprietary assets

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Online 24/7 self-booking (website widget, social media links, Google Business)
- Automated SMS/email appointment reminders and confirmations
- Integrated POS with card payments (chip, tap, mobile wallet)
- Client profiles with visit history and service notes
- Staff calendar management with colour-coded lanes
- No-show and late-cancellation protection via deposit or prepayment
- Multi-staff and basic multi-location support
- Basic marketing campaigns (birthday messages, lapsed-client reactivation)

### Differentiating Features
- Consumer marketplace for organic discovery (Fresha, Vagaro, Mindbody)
- Walk-in queue management with live wait-time display (Squire, Barberly)
- AI agents for automated call answering and booking outside business hours (Zenoti, Fresha)
- HIPAA-compliant client charting and intake forms (Mangomint, Boulevard, Zenoti)
- Express multi-service multi-provider booking optimisation (Mangomint Express Booking™)
- In-shop TV appointment/queue board (Barberly, Squire)
- Self-check-in kiosk on tablet (Barberly)
- Built-in payroll without third-party integration (Vagaro)
- Zero-subscription marketplace monetisation model (Fresha)
- Per-user pricing model for affordability at scale (Timely)

### Underserved Areas / Opportunities
- AI-powered client style memory: persistent formulas, cut notes, and product preferences surfaced at check-in across any staff member
- Dynamic demand-aware pricing for time slots (no platform executes this well today)
- Proactive smart rebooking prediction before lapse rather than reactive reactivation campaigns
- Licence and compliance tracking for multi-jurisdiction staff licence expiry management
- Chemical inventory and safety compliance linked to OSHA SDS records
- Open API ecosystem for third-party app builders (most platforms restrict or charge for API access)
- Cross-platform mobile parity: most platforms have significant mobile/desktop feature gaps
- Unified two-way messaging across SMS, email, and WhatsApp in one inbox (only Fresha does this today)

### AI-Augmentation Candidates
- Appointment scheduling optimisation to fill gaps and minimise chair downtime
- Client churn prediction and automated win-back messaging at optimal timing
- AI receptionist: answering calls, booking appointments, and responding to FAQs 24/7
- Dynamic pricing based on demand patterns, stylist popularity, and time-slot fill rates
- Client style and formula memory: auto-surface historical notes and product used at check-in
- Staff licence expiry monitoring across multi-state operations
- Marketing copy generation for campaigns (Vagaro already offers this)
- Consultation transcription and charting auto-fill (Zenoti AI Scribe)

---

## Legal & IP Summary

All ten platforms analysed are proprietary commercial SaaS products with no open-source core. Fresha's booking SDK and Boulevard's `book-sdk` (GitHub: Boulevard/book-sdk) are the only publicly accessible open components. Mangomint's Express Booking™ is a branded feature that may represent a protectable UX innovation but no patent filings were found in public searches. Zenoti's "AI Workforce" suite is branded but no specific patents were identified. No copyright or licensing conflicts were found in the research materials; all feature descriptions are derived from publicly available product documentation, review platforms, and vendor websites. An open-source implementation of similar features would not infringe known IP, though care should be taken around any patented scheduling optimisation algorithms if they exist.

---

## Recommended Feature Scope

**Must-have (MVP)**
- Appointment calendar with multi-staff lanes and drag-and-drop management
- Online self-booking via embeddable widget and shareable link
- Automated SMS/email reminders and confirmations
- Integrated POS with card payments and no-show deposit protection
- Client profiles with visit history, service notes, and formula memory
- Walk-in queue management with live wait-time display

**Should-have (v1.1)**
- Consumer-facing discovery marketplace or Google/social booking integration
- AI receptionist for after-hours booking and FAQ responses
- Multi-location management and unified reporting
- Loyalty programme and basic marketing campaign automation
- Self-check-in kiosk and TV appointment/queue board
- Staff licence expiry tracking and compliance alerts

**Nice-to-have (backlog)**
- Dynamic demand-aware pricing by time slot and stylist
- HIPAA-compliant intake forms and charting for medspa adjacency
- Chemical inventory management linked to OSHA SDS records
- Built-in payroll processing
- Open REST API and webhook ecosystem for third-party integrations
- Two-way unified messaging hub (SMS, email, WhatsApp)
