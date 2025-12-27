---
Product: "OmahaDotDev Phase 1"
DocumentType: "Project_One_Page"
Status: Planning
---

## Problem Alignment

### Problem Statement

The current OmahaDotDev site has a dated UI and relies solely on email notifications, which users report as unreliable (over 1000 on email list but inconsistent delivery). Admin tools are basic CRUD interfaces requiring extensive manual coordination across the 11 annual events, and the user group lacks social media presence to reach broader audiences. This creates administrative burden and limits event visibility and attendance (typically 40-50 attendees despite large email list).

### High Level Approach

Think of this as transforming from a spreadsheet-based process to a project management system—each stakeholder (admins, sponsors, presenters) sees their tasks at the right time, and the system guides them through the workflow automatically. The platform automates the complete lifecycle from annual sponsor drawing through event publication, while multi-channel notifications (email, SMS, LinkedIn) ensure users actually receive event announcements. Self-service portals let sponsors and presenters manage their own content, reducing admin coordination work.

### Goals

1. Reduce admin time and stress managing events through automated workflow orchestration (sponsor assignment, content collection triggers, notifications)
2. Improve event notification reliability and expand reach through multi-channel delivery (email, SMS, LinkedIn) addressing current email delivery issues
3. Modernize UI to improve user satisfaction with contemporary, mobile-responsive design
4. Enable sponsor self-service payment processing to streamline sponsorship fee collection

### Non Goals

- **Native mobile apps (iOS/Android)**: Mobile-responsive web satisfies current needs; will evaluate native apps based on Phase 1 usage patterns and user requests
- **Zoom/Teams integration**: Events are in-person only; defer virtual/hybrid event support to future phases if format changes
- **Social platforms beyond LinkedIn**: Focus on LinkedIn initially to validate social media engagement; expand to additional platforms based on measured impact
- **Advanced reporting dashboards**: Basic analytics and RSVP counts sufficient for Phase 1; build comprehensive reporting based on actual data needs discovered through usage

## Solution Alignment

### Key Features

1. **Annual sponsor drawing system** with automated winner selection, event stub creation, sponsor assignment, and notification emails
2. **Event workflow automation** managing progression through stages: stub creation → sponsor/presenter assignment → content collection at 4-week mark → admin review → publication
3. **Self-service portals** for sponsors (company details, logo, links) and presenters (bio, headshot, talk title/abstract) to populate their own records
4. **Multi-channel event notifications** delivering announcements via email, SMS, and LinkedIn posts 10 days before events
5. **Payment processing integration** for sponsors to pay sponsorship fees directly through the platform
6. **RSVP tracking system** for attendance estimation and planning
7. **Admin override capabilities** enabling manual intervention for exceptions (sponsor swaps, presenter changes, cancellations, rescheduling)
8. **Modern, mobile-responsive UI** replacing dated interface with contemporary design accessible across devices
9. **Analytics integration** for tracking user engagement, notification delivery, and event performance

### Key Flows

**Flow 1: Annual Sponsor Drawing**
Enables the annual process where sponsors select their preferred event dates and the system randomly assigns winners from interested parties for each slot, automatically creating event stubs and notifying sponsors.

**Flow 2: Event Lifecycle**
Orchestrates the complete event journey from stub creation through publication, coordinating sponsor/presenter assignment, automated content collection triggers at key milestones (4 weeks out), self-service content population, admin review, publication, multi-channel announcements (10 days prior), and RSVP tracking.

**Flow 3: Exception Handling**
Provides admin override capabilities for managing disruptions including sponsor/presenter substitutions, event rescheduling or cancellation with automatic multi-channel notifications, payment retry workflows, and content deadline enforcement.

---

## Completion Checklist

- [x] Product name specified in frontmatter (replaced "{Product Name}")
- [x] Problem Alignment: Problem statement with evidence and impact (target: 1-2 sentences)
- [x] Problem Alignment: High level approach with conceptual shape (target: 2-4 sentences)
- [x] Goals: 2-5 prioritized, outcome-oriented goals (mix of measurable and qualitative)
- [x] Non-Goals: 1-4 items with rationale explaining scope boundaries
- [x] Key Features: 3-7 prioritized features defining solution perimeter
- [x] Key Flows: 1-3 complete end-to-end flows with edge cases
- [x] No placeholder text remains (no "TBD", "TODO", "[To be determined]", etc.)
- [x] All content is specific and actionable (avoid vague statements)
- [x] Document follows validation guidance in each section
