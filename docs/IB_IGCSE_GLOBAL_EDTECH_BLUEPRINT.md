# IB + IGCSE Global AI EdTech Platform Blueprint (Deployment-Ready)

## 0) Product Positioning (North Star)

**Positioning statement:**
A globally localized, AI-personalized learning platform for IB and IGCSE students that combines premium tutoring, adaptive practice, and execution-grade study planning in one seamless system.

**Primary business goals:**
- Increase trial-to-paid conversion via high-intent homepage journeys.
- Improve learning outcomes (test score uplift, completion rates).
- Enable scalable international expansion without SEO dilution.
- Maintain enterprise-grade reliability for schools/parents.

**Primary user segments:**
- Students (IB DP/MYP, IGCSE, age 12–19)
- Parents (decision makers)
- Tutors (supply side)
- Schools / institutional buyers (B2B2C)

---

## 1) Homepage System (Primary Focus)

### 1.1 Homepage Objectives
- **Acquire**: rank for country/city + subject + exam intent.
- **Convert**: tutor booking + AI test start + consultation CTA.
- **Qualify**: show local relevance (city/country curriculum mapping).
- **Trust**: prove outcomes, tutor quality, and global operations.

### 1.2 SEO-first Semantic Information Architecture
Use semantic blocks in this order for crawl + conversion:

1. `<header>` global nav + location switcher
2. `<main>`
   - `<section>` Hero (`h1`)
   - `<section>` Outcomes + trust proofs (`h2`)
   - `<section>` Tutor discovery (`h2`)
   - `<section>` AI tools (`h2`)
   - `<section>` Courses and pathways (`h2`)
   - `<section>` City-level proof + FAQs (`h2`)
   - `<section>` CTA strip (`h2` hidden for accessibility)
3. `<footer>` localized links, schema-backed NAP/contacts

### 1.3 Conversion Architecture (Above-the-fold)
**Hero layout (Blinkit-like space utilization):**
- Left 60%: personalized proposition + quick actions.
- Right 40%: compact interactive card stack (Book tutor, Generate test, Plan week).
- Sticky top utility row: location, curriculum (IB/IGCSE), grade, subject.

**Hero content logic:**
- Dynamic headline: “Top IB Math Tutors in {City} + AI Study Plan in 2 Minutes”
- Primary CTA: `Book a Tutor`
- Secondary CTA: `Generate Free AI Test`
- Tertiary CTA: `View {City} Results`

**Why this works:**
- Reduces decision latency with 3 high-intent actions.
- Uses progressive disclosure (don’t show all options immediately).
- Emulates high-density commerce UX while preserving academic credibility.

### 1.4 Recommended Homepage Blocks
1. **Hero with personalization inputs** (grade, board, exam date)
2. **Trust bar** (students taught, average score uplift, countries, response SLA)
3. **Tutor discovery rail** (cards with availability, price, ratings, language)
4. **AI tools showcase**
   - AI Test Generator
   - Weekly Study Planner
   - Weak-topic detection
5. **Program pathways** (IB HL/SL, IGCSE subjects)
6. **Location intelligence** (city-specific timings, tutor density, parent reviews)
7. **Case studies** (before/after outcomes)
8. **FAQ + schema**
9. **Final CTA cluster** (book consult, free diagnostic, view plans)

### 1.5 SEO Technical Pattern
- Pre-render static city landing pages for top cities.
- ISR/SSR for long-tail city pages and real-time tutor availability.
- JSON-LD: `Organization`, `Course`, `FAQPage`, `Review`, `LocalBusiness`.
- Internal links: country > city > subject > tutor.
- Canonicalized param handling (avoid indexation of filtered duplicates).

---

## 2) UI/UX Style System (Figma-ready)

### 2.1 Visual Language Principles
- **Premium utility**: dense but breathable interfaces.
- **Subtle glassmorphism** only on high-value containers (hero cards, modals, command palette).
- **Enterprise greys** for trust and focus.
- **High-contrast accents** only for actions.

### 2.2 Color Tokens

#### Neutrals (core trust system)
- `Gray/950 #0B1220` (deep background)
- `Gray/900 #111827` (primary nav)
- `Gray/800 #1F2937` (card elevated)
- `Gray/700 #374151` (borders dark)
- `Gray/500 #6B7280` (secondary text)
- `Gray/200 #E5E7EB` (light borders)
- `Gray/50 #F9FAFB` (light background)

#### Primary accent (recommended)
- `Cobalt/600 #2563EB` (primary CTA)
- `Cobalt/500 #3B82F6` (hover)
- Rationale: trustworthy + educational + globally neutral.

#### Success / warning / error
- `Green/600 #16A34A`
- `Amber/500 #F59E0B`
- `Red/600 #DC2626`

#### Optional conversion accent
- `Violet/500 #8B5CF6` for AI features only (not universal CTA) to signify intelligence.

### 2.3 Glassmorphism Rules
- Background fill: `rgba(255,255,255,0.08)` (dark UI) or `rgba(255,255,255,0.65)` (light).
- Border: `1px solid rgba(255,255,255,0.22)`
- Blur: 12–20 px max.
- Never stack more than 2 blurred layers in viewport.

### 2.4 Typography Scale
- Font stack: `Inter` (UI), `Manrope` (headings optional), `JetBrains Mono` (analytics).
- Scale (8pt grid aligned):
  - Display: 56/64
  - H1: 44/52
  - H2: 36/44
  - H3: 28/36
  - H4: 22/30
  - Body L: 18/28
  - Body M: 16/24
  - Body S: 14/20
  - Caption: 12/16

### 2.5 Spacing & Radius
- Spacing tokens: `4, 8, 12, 16, 24, 32, 40, 48, 64, 80`
- Radius tokens: `8, 12, 16, 24`
- Container widths: `1280 desktop`, `960 tablet`, fluid mobile.

### 2.6 Core Component Library
- Buttons: Primary / Secondary / Ghost / Destructive / AI-tagged.
- Inputs: search, select, date-time, curriculum picker.
- Cards: tutor card, AI tool card, metric card, testimonial card.
- Scheduling widgets: availability heatmap, timezone chip, slot chooser.
- Tables: admin data grid with filters + bulk actions.
- Dashboards: modular tile system with drag-and-drop.

---

## 3) Global Localization System

### 3.1 URL Strategy
- `example.com/{country}/{city}`
- Optional leafs:
  - `/{country}/{city}/ib-math-tutors`
  - `/{country}/{city}/igcse-physics`
  - `/{country}/{city}/ai-test-generator`

### 3.2 Rendering Strategy
- **Static generation** for top markets (high-traffic country/city pages).
- **ISR** every 12–24h for semi-dynamic data blocks.
- **Edge SSR** for user-personalized elements (local time slots, inventory).
- **Client hydration** for interactive filters.

### 3.3 Content Differentiation (avoid thin/duplicate pages)
Each localized page must vary in:
- Tutor supply data (local tutors + languages)
- Pricing/currency and payment methods
- Country exam calendars and school terms
- City-specific outcomes, reviews, case studies
- Transportation/offline class availability
- Region-specific FAQs and policy notes

### 3.4 SEO Integrity Controls
- Canonical to most representative URL.
- `hreflang` country/language mappings.
- Noindex low-value faceted URLs.
- Programmatic content templates + human editorial blocks.
- Distinct metadata, schema, and intro copy per location.

---

## 4) Seven-Layer Architecture (System Design)

### Layer 1: Presentation Layer (UI)
- Web app, mobile web, native shells.
- Figma token-driven components.
- Accessible, responsive, low-latency interface.

### Layer 2: Experience Layer (UX Logic)
- Personalization orchestration (student profile, goals, region).
- Funnel rules (CTA prioritization by intent score).
- Journey state machine (discover → diagnose → plan → book → learn).

### Layer 3: Application Layer
- Tutoring marketplace (search, compare, book, pay).
- Group class operations.
- Lesson planning workflows.
- Assignment/test distribution.
- Notifications and communication center.

### Layer 4: AI Layer
- Recommendation engine (next topic, tutor match, schedule).
- AI test generation by board/topic/difficulty.
- Rubric-based feedback + weak-area detection.
- LLM safety + moderation and explainability service.

### Layer 5: Data Layer
- User graph (student, tutor, parent, admin).
- Learning event store (attempts, scores, session logs).
- Content repository (curriculum-mapped assets).
- Analytics warehouse + experimentation events.

### Layer 6: Localization Layer
- Geo/context service (country/city/language/currency).
- Content variant management.
- Locale-specific legal/compliance policies.
- Translation memory + QA workflow.

### Layer 7: Infrastructure Layer
- Edge CDN, regional compute, queue workers.
- Observability stack (logs, traces, product analytics).
- CI/CD, feature flags, canary deployments.
- Security: encryption, RBAC, audit logs.

### Layer Interaction (request lifecycle)
1. UI request enters at edge.
2. Localization resolves country/city.
3. Experience layer chooses layout/content order.
4. Application layer fetches tutoring/test/planner modules.
5. AI layer computes recommendations/tests.
6. Data layer persists events and outcomes.
7. Infrastructure scales and caches response.

---

## 5) Core Platform Modules & UX Flows

### 5.1 Student Dashboard
**Widgets:**
- Today’s plan, upcoming classes, weak-topic radar, AI test quick start, progress trends.

**Flow:**
- Login → diagnostic snapshot → recommended action cards → one-click booking or test.

### 5.2 Tutor Dashboard
**Widgets:**
- Availability manager, student pipelines, session prep AI brief, earnings, feedback.

**Flow:**
- Open dashboard → review today’s learners → launch lesson plan template → conduct/record outcome.

### 5.3 Admin Panel
**Capabilities:**
- Supply-demand heatmap by city.
- Tutor quality SLA and intervention workflows.
- Content localization control center.
- Revenue, churn, and cohort intelligence.

### 5.4 AI Test Generator
**UX steps:**
1. Select board, grade, subject, duration.
2. Choose difficulty profile.
3. Generate + preview blueprint.
4. Attempt mode (timed/adaptive).
5. Report with skill-level diagnostics.

### 5.5 Lesson Planner
- Inputs: syllabus timeline, exam date, weak areas, weekly availability.
- Outputs: week-by-week plan with effort load balancing.
- Integration: auto-sync with tutor and calendar.

### 5.6 Booking System (1:1 + Group)
- Unified calendar with timezone-safe slots.
- Filters by mode: online/offline/hybrid.
- Real-time seat management for groups.
- Smart rescheduling with conflict detection.

### 5.7 Hybrid Online/Offline Scheduling
- Geo radius selection for in-person lessons.
- Commute-aware slot recommendations.
- Safety checks: verified tutor IDs, venue profiles.

---

## 6) Navigation Structure (Scalable)

### 6.1 Global Navigation
- Learn
- Tutors
- AI Tools
- Results
- Pricing
- For Schools
- Location switcher
- Login / Get Started

### 6.2 Country/City Navigation
- Local tutors
- Subjects
- Group classes
- Exam timelines
- Parent stories
- FAQs

### 6.3 Role-based Navigation
**Student:** Dashboard, Planner, Tests, Classes, Progress, Messages.

**Tutor:** Dashboard, Schedule, Students, Content, Earnings, Support.

**Admin:** Ops overview, Tutors, Learners, Content, Localization, Revenue, Risk.

### 6.4 IA Rules
- Maximum nav depth: 3 levels.
- Persistent breadcrumbs for localized routes.
- Command palette (`⌘K`) for power navigation.

---

## 7) Frontend Experience (Next-gen)

### 7.1 Recommended Stack
- **Framework:** Next.js (App Router)
- **UI:** React + TypeScript + Tailwind + Headless UI/Radix
- **State/data:** React Query + server actions
- **Search:** Typesense/Algolia for tutor discovery
- **CMS:** headless CMS (localized blocks)

### 7.2 Rendering Strategy
- SSG for evergreen pages.
- ISR for city listings.
- Edge SSR for personalized homepage units.
- Streaming SSR for above-the-fold first paint.

### 7.3 AI-driven Personalization
- Intent model ranks homepage cards by conversion probability.
- Dynamic CTA labels based on funnel stage.
- Study planner adapts by behavior and missed deadlines.

### 7.4 Micro-interactions
- Slot selection magnetism (snap + conflict hints).
- AI generation progress with pedagogical transparency.
- Mastery rings animate on score improvements.

### 7.5 Performance Targets
- LCP < 2.0s (top markets)
- INP < 150ms
- CLS < 0.05
- JS budget: < 180KB route-critical
- Image strategy: AVIF/WebP + art direction by breakpoint

### 7.6 “Beyond Typical EdTech” Ideas
- Explainable AI feedback with citation to syllabus objectives.
- Parent confidence mode (weekly digest + risk alerts).
- City-level learning communities (moderated cohorts).
- Tutor copilots (auto prep kits from student history).

---

## 8) Figma Delivery Package

### 8.1 Low-fidelity Wireframes (must create)
- Homepage (desktop/mobile)
- Student dashboard
- Tutor dashboard
- Booking flow
- AI test flow
- Localization selector modal

### 8.2 High-fidelity Screens
- Hero variants by intent segment.
- Tutor discovery page with dense filters.
- AI planner and test report pages.
- Admin analytics cockpit.

### 8.3 Figma Page Structure
1. `00 Foundations`
2. `01 Components`
3. `02 Patterns`
4. `03 Templates`
5. `04 Screens - Marketing`
6. `05 Screens - App`
7. `06 Prototypes`
8. `07 Handoff`

### 8.4 Design Tokens (sample)
- `color.bg.surface.primary = #111827`
- `color.text.primary = #F9FAFB`
- `space.4 = 16`
- `radius.md = 12`
- `shadow.glass = 0 8 24 rgba(0,0,0,.18)`

### 8.5 Auto-layout Rules
- Parent frame uses vertical auto-layout with section spacing token.
- Reusable section wrappers (`max-width`, gutters, breakpoint variants).
- All cards built with nested auto-layout + min/max constraints.
- Component properties for state (`default/hover/loading/disabled`).

---

## 9) Deployment-level Product Architecture (Execution)

### 9.1 Services (minimum viable enterprise)
- Identity service (SSO, OAuth, parental controls)
- Tutor marketplace service
- Scheduling service
- Payments + invoicing service
- AI orchestration service
- Content and curriculum service
- Localization/content delivery service
- Analytics and experimentation service

### 9.2 Data & Event Model
- Event bus topics:
  - `booking.created`
  - `test.generated`
  - `session.completed`
  - `risk.student_low_progress`
- Warehouse marts:
  - acquisition funnel
  - learning outcomes
  - tutor quality
  - localization performance

### 9.3 Security & Compliance
- GDPR/UK GDPR-aligned controls.
- COPPA-aware minors data treatment by region.
- Data residency strategy for sensitive regions.
- Role-based access + immutable audit trails.

### 9.4 Observability & Reliability
- SLOs:
  - Booking API 99.95%
  - AI generation API 99.5%
  - Dashboard availability 99.9%
- Alerting: latency, error budget burn, queue lag.

### 9.5 Release & Experimentation
- Feature flags per country/city.
- Experiment framework by audience segment.
- Canary rollouts by region.

---

## 10) Risks & Corrections to Current Approach

### 10.1 Risks
- Over-personalization can harm clarity and SEO.
- Thin city pages can trigger ranking suppression.
- Complex dashboards may overwhelm teens on mobile.
- AI output inconsistency can reduce parent trust.

### 10.2 Corrections
- Keep first-screen choices capped at 3 primary actions.
- Enforce localization content quality thresholds.
- Default student dashboard to “Today view” simplicity.
- Add human-reviewed QA for generated tests initially.

### 10.3 Differentiators to Win Globally
- Outcome-backed tutor matching (not just rating-based).
- Curriculum-objective-level mastery graph.
- Parent + student dual-mode interface.
- Offline tutoring logistics integrated natively.

---

## 11) Implementation Roadmap (90 Days)

### Phase 1 (Weeks 1–4)
- Foundations: design system + IA + localization framework.
- Build SEO homepage + tutor discovery MVP.

### Phase 2 (Weeks 5–8)
- Student/tutor dashboards + booking engine + AI test v1.
- Instrument analytics events + experimentation.

### Phase 3 (Weeks 9–12)
- Admin cockpit + localization scale-out.
- Performance hardening + reliability + launch prep.

---

## 12) Definition of Done (Launch Gate)
- Core journeys complete in ≤3 clicks from homepage.
- City landing pages pass uniqueness and schema checks.
- Accessibility AA conformance for key pages.
- Core web vitals targets met for top geos.
- Tutor booking + AI test generation production-stable.

