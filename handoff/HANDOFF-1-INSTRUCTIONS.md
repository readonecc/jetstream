# Jetstream Pressure Washing AU — Developer Handoff: Instructions & Shared Content

This document covers everything you need to build the site structure, global elements, and reusable sections. Read this first before touching any content files.

---

## Table of Contents

1. [Business Details & Quick Reference](#1-business-details--quick-reference)
2. [Global Changes — Do These First](#2-global-changes--do-these-first)
3. [Site Menu Bar — Full Structure & Implementation](#3-site-menu-bar--full-structure--implementation)
4. [Quote Form — Simple One-Step Form](#4-quote-form--simple-one-step-form)
5. [Hero USP Cards — Where They Appear](#5-hero-usp-cards--where-they-appear)
6. [Shared Blocks — Build Once as Bricks Templates](#6-shared-blocks--build-once-as-bricks-templates)
7. [Service Page Template — 16-Section Layout](#7-service-page-template--16-section-layout)
8. [Category Page Template — How It Differs](#8-category-page-template--how-it-differs)
9. [Full Page List — All 49 Pages](#9-full-page-list--all-49-pages)
10. [How to Read the Content Files](#10-how-to-read-the-content-files)
11. [What to Remove From the Live Site](#11-what-to-remove-from-the-live-site)

---

## 1. Business Details & Quick Reference

| Detail | Value |
|--------|-------|
| **Business Name** | Jetstream Pressure Washing AU |
| **Phone (display)** | 0491 016 876 |
| **Phone (link)** | `tel:+61491016876` |
| **Email** | support@jetstreampressurewashing.au |
| **Email (link)** | `mailto:support@jetstreampressurewashing.au` |
| **Service Area** | Brisbane, QLD (no physical address — service area business) |
| **Copyright** | © 2026 Jetstream Pressure Washing AU. All Rights Reserved. |
| **Payment Methods** | Visa, Mastercard, Bank Transfer (show icons) |
| **Social Media** | Facebook, Instagram, YouTube, LinkedIn (link to actual profiles) |

**Brand Logos (6 — used in Brand Logos Bar):**
BAR Group, Softwash Australia, Karcher, Honda, NWC Softwash, Southside Pressure Washing Gear

> **Important:** Dulux is NOT a supplier — do not include their logo anywhere.

**Verified Claims (safe to display on site):**
- 100% Money-Back Guarantee
- $20 million public liability insurance
- 10% Seniors & Pensioners Discount
- $59 Off Roof & House Washing
- $119 Off Sealing & Painting
- Free Clean when you Seal or Paint
- Free same-day quotes
- Payment on completion only

**Do NOT use anywhere on the site:**
- Specific review counts (use dynamic Google widget or "hundreds of 5-star reviews")
- "Best", "#1", "cheapest" or similar superlatives
- Any pricing in service page body copy (quotes are custom)
- "House cleaning" — always "house washing" (different industry)
- American English — use Australian English (mould not mold, colour not color, specialised not specialized, aluminium not aluminum)

---

## 2. Global Changes — Do These First

These affect every page on the site. Complete them before building individual pages.

### 2.1 Phone Number
- **Display format:** `0491 016 876`
- **Link format:** `tel:+61491016876`
- The current live site shows `(04) 9101 6876` — update this everywhere (header, footer, hero sections, CTA buttons, "Reach Out" sections, etc.)

### 2.2 CTA Buttons (used site-wide, identical on every page)
Every page has two CTA buttons. They always do the same thing:

| Button | Text | Action |
|--------|------|--------|
| **Quote Button** | Get Your Free Quote | Scrolls to / opens the quote form |
| **Call Button** | Call Us Now / 0491 016 876 | Links to `tel:+61491016876` |

The call button displays on two lines:
- Line 1: `Call Us Now`
- Line 2: `0491 016 876`

### 2.3 Top Bar
- **Phone:** 0491 016 876 (link: `tel:+61491016876`)
- **Email:** support@jetstreampressurewashing.au
- **Service Area Text:** Servicing All of Brisbane

### 2.4 Footer
Build this once as a Bricks template. Used on every page.

**Company Blurb:** Jetstream Pressure Washing AU provides professional exterior cleaning and pressure washing services across Brisbane. Fully licensed, insured, and backed by a 100% money-back guarantee.

**Payment Methods:** Visa, Mastercard, Bank Transfer (show payment icons)

**Column 1 — Quick Links:**
- About Us → `/about-us/`
- Our Work → `/our-work/`
- Services → `/services/`
- Contact Us → `/contact-us/`
- Privacy Policy → `/privacy-policy/`

**Column 2 — Our Services:**
- House Washing → `/house-washing/`
- Roof Cleaning → `/roof-cleaning/`
- Pressure Cleaning → `/pressure-cleaning/`
- Gutter Cleaning → `/gutter-cleaning/`
- Commercial Services → `/commercial-services/`
- Sealing & Painting → `/sealing-painting/`

> **Note:** These link to **category pages**, not individual service pages.

**Column 3 — Contact Information:**
- Phone: 0491 016 876 (link: `tel:+61491016876`)
- Email: support@jetstreampressurewashing.au (link: `mailto:support@jetstreampressurewashing.au`)
- Service Area: Brisbane, QLD

**Google Rating Badge:** ★★★★★ 4.9/5.0 Google Reviews (pull dynamically from widget)

**Social Media Icons:** Facebook, Instagram, YouTube, LinkedIn (link to actual profiles)

**Copyright:** © 2026 Jetstream Pressure Washing AU. All Rights Reserved.

---

## 3. Site Menu Bar — Full Structure & Implementation

### 3.1 Header Layout

```
[Logo]                    [Menu Items]                    [CTA Button]
Jetstream Pressure        Home | Our Work | About Us |    Call 0491 016 876
Washing AU                Services ▾ | Contact Us         tel:+61491016876
```

### 3.2 Menu Items (Top Level)

| Position | Label | URL | Type |
|----------|-------|-----|------|
| 1 | Home | `/` | Simple link |
| 2 | Our Work | `/our-work/` | Simple link |
| 3 | About Us | `/about-us/` | Simple link |
| 4 | Services | `/services/` | Mega menu trigger (also clickable — links to `/services/`) |
| 5 | Contact Us | `/contact-us/` | Simple link |

**Header CTA Button:** `Call 0491 016 876` → links to `tel:+61491016876`

### 3.3 Services Mega Menu — Full Structure

When the user hovers or clicks "Services", display a dropdown/mega menu with **6 columns** — one per service category. Each column header is a clickable link to the category page.

**Recommended implementation:** Build as a Bricks mega menu with 6 columns. Each column has a bold header (the category name, linked to the category URL) followed by the child service links below it.

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│  HOUSE WASHING     ROOF CLEANING      PRESSURE CLEANING    GUTTER CLEANING     │
│  /house-washing/   /roof-cleaning/    /pressure-cleaning/  /gutter-cleaning/   │
│                                                                                 │
│  House Soft        Roof Soft          Driveway Cleaning    (no children —       │
│   Washing           Washing           Pathway Cleaning      single service)     │
│  House Pressure    Roof Pressure      Patio Cleaning                            │
│   Washing           Washing           Deck Cleaning        SEALING & PAINTING   │
│                    Biocide Roof       Pool Area Cleaning   /sealing-painting/   │
│  COMMERCIAL         Treatment         Concrete Cleaning                         │
│  SERVICES                             Retaining Wall       Concrete Sealing     │
│  /commercial-                          Cleaning            Concrete Painting    │
│   services/                           Fence Cleaning       Driveway Sealing     │
│                                       Window Cleaning      Walkway Sealing      │
│  Commercial                           Solar Panel          Driveway Painting    │
│   Building Washing                     Cleaning            Walkway Painting     │
│  Warehouse                                                 Driveway Anti-Slip   │
│   Cleaning                                                  Coating             │
│  Loading Dock                                                                   │
│   Cleaning                                                                      │
│  Car Park Cleaning                                                              │
│  Bin Area Cleaning                                                              │
│  Shopfront                                                                      │
│   Cleaning                                                                      │
│  Shopfront Window                                                               │
│   Cleaning                                                                      │
│  Graffiti Removal                                                               │
│  Body Corporate                                                                 │
│   Cleaning                                                                      │
│  Body Corporate                                                                 │
│   Exterior                                                                      │
│  Body Corporate                                                                 │
│   Walkway                                                                       │
│  Body Corporate                                                                 │
│   Car Park                                                                      │
│  Body Corporate                                                                 │
│   Entryway                                                                      │
│  Body Corporate                                                                 │
│   Bin Area                                                                      │
│  Retirement                                                                     │
│   Village                                                                       │
└─────────────────────────────────────────────────────────────────────────────────┘
```

### 3.4 Complete Link Table for Services Mega Menu

**Column 1 — House Washing** (header links to `/house-washing/`)

| Menu Label | URL |
|------------|-----|
| House Soft Washing | `/house-soft-washing/` |
| House Pressure Washing | `/house-pressure-washing/` |

**Column 2 — Roof Cleaning** (header links to `/roof-cleaning/`)

| Menu Label | URL |
|------------|-----|
| Roof Soft Washing | `/roof-soft-washing/` |
| Roof Pressure Washing | `/roof-pressure-washing/` |
| Biocide Roof Treatment | `/biocide-roof-treatment/` |

**Column 3 — Pressure Cleaning** (header links to `/pressure-cleaning/`)

| Menu Label | URL |
|------------|-----|
| Driveway Cleaning | `/driveway-pressure-cleaning/` |
| Pathway Cleaning | `/pathway-pressure-cleaning/` |
| Patio Cleaning | `/patio-pressure-cleaning/` |
| Deck Cleaning | `/deck-pressure-cleaning/` |
| Pool Area Cleaning | `/pool-area-pressure-cleaning/` |
| Concrete Cleaning | `/concrete-cleaning/` |
| Retaining Wall Cleaning | `/retaining-wall-cleaning/` |
| Fence Cleaning | `/fence-cleaning/` |
| Window Cleaning | `/exterior-window-cleaning/` |
| Solar Panel Cleaning | `/solar-panel-cleaning/` |

**Column 4 — Gutter Cleaning** (header links to `/gutter-cleaning/`)

No child items — this is a single-service category. The header link goes directly to the gutter cleaning page.

**Column 5 — Commercial Services** (header links to `/commercial-services/`)

| Menu Label | URL |
|------------|-----|
| Commercial Building Washing | `/commercial-building-washing/` |
| Warehouse Cleaning | `/warehouse-pressure-cleaning/` |
| Loading Dock Cleaning | `/loading-dock-pressure-cleaning/` |
| Car Park Cleaning | `/car-park-pressure-cleaning/` |
| Bin Area Cleaning | `/bin-pad-cleaning/` |
| Shopfront Cleaning | `/retail-shopfront-cleaning/` |
| Shopfront Window Cleaning | `/retail-shopfront-window-cleaning/` |
| Graffiti Removal | `/graffiti-removal/` |
| Body Corporate Cleaning | `/body-corporate-pressure-cleaning/` |
| Body Corporate Exterior | `/body-corporate-exterior-cleaning/` |
| Body Corporate Walkway | `/body-corporate-walkway-cleaning/` |
| Body Corporate Car Park | `/body-corporate-car-park-cleaning/` |
| Body Corporate Entryway | `/body-corporate-entryway-cleaning/` |
| Body Corporate Bin Area | `/body-corporate-bin-area-cleaning/` |
| Retirement Village | `/retirement-village-pressure-cleaning/` |

**Column 6 — Sealing & Painting** (header links to `/sealing-painting/`)

| Menu Label | URL |
|------------|-----|
| Concrete Sealing | `/concrete-sealing/` |
| Concrete Painting | `/concrete-painting/` |
| Driveway Sealing | `/driveway-clear-coat-sealing/` |
| Walkway Sealing | `/walkway-clear-coat-sealing/` |
| Driveway Painting | `/driveway-painting-coating/` |
| Walkway Painting | `/walkway-painting-coating/` |
| Driveway Anti-Slip Coating | `/driveway-anti-slip-coating/` |

### 3.5 Mobile Menu

On mobile, the menu should collapse into a hamburger. "Services" expands to show categories, and each category expands to show its child services. Same links as above — just nested accordion/expandable style.

---

## 4. Quote Form — Simple One-Step Form

**Replace the current multi-step form** (which has service dropdown, date picker, ZIP code, multi-step wizard) with this simple 4-field form. Build once as a Bricks template — it's used on the homepage, every service page, every category page, Contact Us, About Us, and Our Work.

| # | Field Label | Placeholder | Required |
|---|-------------|-------------|----------|
| 1 | Name | Your full name | Yes |
| 2 | Email | Your email address | Yes |
| 3 | Phone | Your phone number | Yes |
| 4 | Message | Tell us about your job | No |

- **Form Title:** Get Your Free Quote
- **Form Subtitle:** Fill in the form and we'll get back to you with a free, no-obligation quote.
- **Submit Button:** Get My Free Quote
- **Trust Line (below submit button):** Your information is 100% safe and secure.
- **On submit:** Redirect to `/thank-you/`

> **Important:** No service dropdown. No date picker. No ZIP code. No multi-step wizard. Just 4 fields and a submit button.

---

## 5. Hero USP Cards — Where They Appear

These are 3 trust/USP cards that sit inside the hero section, between the H1/subtitle and the quote form. **Build once as a reusable Bricks template.**

**Card 1 — Licensed & Insured:**
- **Icon:** Shield
- **Title:** Licensed & Insured
- **Description:** All of our specialists are highly experienced, appropriately licensed and insured with $20 million public liability, so you're always covered.

**Card 2 — 100% Money-Back Guarantee:**
- **Icon:** Guarantee badge
- **Title:** 100% Money-Back Guarantee
- **Description:** Your satisfaction is guaranteed. Not happy? We'll come back and fix it. Still not satisfied? You get a full refund. That's our promise.

**Card 3 — 10% Seniors Discount:**
- **Icon:** Percentage / Discount
- **Title:** 10% Seniors Discount
- **Description:** Seniors and pensioners save 10% on every service. Quality exterior cleaning at an affordable price.

### Where these cards appear:

| Page Type | Show USP Cards? |
|-----------|----------------|
| Homepage | YES |
| Category pages (6) | YES |
| Service pages (37) | YES |
| About Us | NO |
| Contact Us | NO |
| Our Work | NO |
| Thank You | NO |
| Services Archive | NO |

---

## 6. Shared Blocks — Build Once as Bricks Templates

These sections appear identically on multiple pages. Build each one once as a reusable Bricks template, then insert where indicated in the content files.

### 6.1 "We Set a New Standard in Exterior Cleaning" Section

**Used on:** Homepage + all service pages + all category pages

- **Kicker:** WHO WE ARE
- **H2:** We Set a New Standard in Exterior Cleaning
- **Body:** Jetstream Pressure Washing AU has been delivering quality exterior cleaning across Brisbane at an affordable price. Whether it's your home, your roof, your driveway, or a commercial property — we bring the right equipment, the right experience, and a genuine care for the result. No hassles, no shortcuts. Just a reliable, quality-focused service you can count on.

**Feature 1:**
- **Icon:** Shield
- **Title:** Complete Peace of Mind
- **Description:** We provide all insurance and licensing details upfront with every quote. $20 million public liability, fully licensed, and completely transparent. Your peace of mind is guaranteed.

**Feature 2:**
- **Icon:** Star / Results
- **Title:** Unmatched Results
- **Description:** As a family-owned business, we deliver exceptional results without the hefty price tag. Professional-grade equipment, trained specialists, and a 100% money-back guarantee on every job.

**Feature 3:**
- **Icon:** Gear / Equipment
- **Title:** State-of-the-Art Equipment
- **Description:** Our team is equipped with professional soft wash setups, turbo nozzles, surface cleaners, and on-board water tanks. We arrive fully prepared for any job, no matter the size.

**Trust Badge:** ★★★★★ Rated 4.9/5 on Google (pull dynamically from widget)

---

### 6.2 Service Cards Grid (Top 6 Services)

**Used on:** Homepage (Section 3) + all service pages (Section 16) + all category pages (Section 16)

- **Kicker:** OUR SERVICES
- **H2:** Professional Exterior Cleaning & Pressure Washing Solutions
- **Subtitle:** Whatever your property needs, chances are we have you covered. From residential homes to large commercial sites — we deliver results across Brisbane.

| Card | H3 | Description | Link URL |
|------|----|-------------|----------|
| 1 | House Washing | Remove mould, dirt, and grime from your home's exterior with our professional soft wash and pressure washing service. Safe for all surfaces. | `/house-washing/` |
| 2 | Roof Cleaning | Restore your roof's appearance and extend its lifespan. We remove mould, lichen, moss, and years of buildup safely and effectively. | `/roof-cleaning/` |
| 3 | Driveway Cleaning | Oil stains, tyre marks, mould, and grime — gone. Our surface cleaning equipment restores driveways to their original condition. | `/driveway-pressure-cleaning/` |
| 4 | Gutter Cleaning | Blocked gutters cause water damage. We clear interior debris and clean exterior gutter faces to keep your property protected and looking sharp. | `/gutter-cleaning/` |
| 5 | Pressure Cleaning | Patios, pathways, decks, pool areas, fences, and retaining walls. If it's dirty, we clean it — with the right pressure for every surface. | `/pressure-cleaning/` |
| 6 | Sealing & Painting | Protect your driveway or walkway with professional clear coat sealing, coloured coatings, or anti-slip systems. Clean, seal, and protect in one visit. | `/sealing-painting/` |

**Button below cards:** See All Services → `/services/`

Each card link text: `View Service →`

---

### 6.3 Trust Credentials Strip (3 items)

**Used on:** All service pages (Section 6) + all category pages (Section 6)

**Item 1:**
- **Icon:** Shield / Insurance
- **Title:** Fully Licensed & Insured
- **Description:** Every job is backed by $20 million in public liability insurance. We provide all licensing and insurance details upfront with every quote — no surprises.

**Item 2:**
- **Icon:** Guarantee badge
- **Title:** 100% Money-Back Guarantee
- **Description:** Not happy? We'll come back and fix it at no extra charge. Still not satisfied? You get a full refund. That's our promise.

**Item 3:**
- **Icon:** Percentage / Discount
- **Title:** 10% Seniors Discount
- **Description:** We believe quality exterior cleaning should be affordable for everyone. Seniors and pensioners save 10% on every service.

---

### 6.4 "How We Work With You" Section (3 Steps)

**Used on:** Homepage + all service pages + all category pages

> **Important:** The current live site shows 4 steps. Change to 3 steps.

- **Kicker:** SIMPLE & STRESS-FREE
- **H2:** How We Work With You
- **Subtitle:** Getting your property cleaned shouldn't be complicated. Here's how we make it easy.

**Step 1:**
- **Number:** 01
- **Title:** Get Your Free Quote
- **Description:** Call us or fill in the form. Tell us what you need cleaned and we'll send you a free, no-obligation quote — usually within the same day.

**Step 2:**
- **Number:** 02
- **Title:** We Get to Work
- **Description:** Our team arrives on time with professional-grade equipment. We clean your property thoroughly and treat every job like it's our own home.

**Step 3:**
- **Number:** 03
- **Title:** You're 100% Happy
- **Description:** We walk you through the results before we leave. If anything isn't right, we fix it on the spot. Payment is only on completion.

---

### 6.5 CTA Banner

**Used on:** All service pages (Section 8) + all category pages (Section 8)

- **H2:** Ready to Get Your Property Looking Its Best?
- **CTA Button:** Get Your Free Quote

---

### 6.6 Brand Logos Bar

**Used on:** Homepage + all service pages + all category pages

- **Kicker:** TRUSTED PRODUCTS
- **H2:** Trusted Brands We Use Every Day
- **Subtitle:** We only use professional-grade products and equipment from brands trusted across the industry.

**Brands:** BAR Group, Softwash Australia, Karcher, Honda, NWC Softwash, Southside Pressure Washing Gear

> **Important:** Dulux is NOT a supplier — do not include.

---

### 6.7 Testimonials Section

**Used on:** Homepage + all service pages + all category pages

- **Kicker:** REAL REVIEWS
- **H2:** What Our Clients Are Saying
- **Subtitle:** Don't just take our word for it. See what hundreds of Brisbane homeowners and businesses have to say about our work.

> Reviews pulled from Google review widget. No hardcoded testimonials needed.

---

### 6.8 "Reach Out to Us Today" Section

**Used on:** Homepage, About Us, Contact Us, Our Work, Services Archive + all service pages + all category pages

- **Kicker:** LET'S WORK TOGETHER
- **H2:** Reach Out to Us Today
- **Phone Label:** Call us today
- **Phone Number:** 0491 016 876 (link: `tel:+61491016876`)
- **Email Label:** Send us an email
- **Email:** support@jetstreampressurewashing.au (link: `mailto:support@jetstreampressurewashing.au`)

This section is paired with the Quote Form (Section 4 above) wherever it appears.

---

## 7. Service Page Template — 16-Section Layout

Every service page follows this exact layout from top to bottom. The sections marked "SHARED" are the same Bricks templates on every page. The sections marked "UNIQUE" have content specific to that page (found in the page's content file).

| # | Section | Content Source | Type |
|---|---------|---------------|------|
| 1 | Breadcrumb | Page's content file | UNIQUE |
| 2 | Hero (H1 + subtitle + CTAs + quote form + USP cards) | Page's content file + shared quote form + shared USP cards | UNIQUE + SHARED |
| 3 | "We Set a New Standard" block | Shared block 6.1 | SHARED |
| 4 | 2 Related Service Cards | Page's content file | UNIQUE |
| 5 | Service Details Accordion (4 items) | Page's content file | UNIQUE |
| 6 | Trust Credentials Strip | Shared block 6.3 | SHARED |
| 7 | Before/After Gallery | Page's content file (text only — images separate) | UNIQUE |
| 8 | CTA Banner | Shared block 6.5 | SHARED |
| 9 | Brand Logos Bar | Shared block 6.6 | SHARED |
| 10 | Full-Width Selling Point (H2 + paragraph) | Page's content file | UNIQUE |
| 11 | "How We Work With You" (3 steps) | Shared block 6.4 | SHARED |
| 12 | Testimonials / Reviews | Shared block 6.7 | SHARED |
| 13 | "Reach Out to Us Today" + Quote Form | Shared block 6.8 + Quote Form | SHARED |
| 14 | FAQ Section (5 unique Q&As) | Page's content file | UNIQUE |
| 15 | Footer | Shared block (footer) | SHARED |
| 16 | Top 6 Service Cards | Shared block 6.2 | SHARED |

**Unique sections per service page:** 1, 2 (hero text), 4, 5, 7 (text), 10, 14

**Shared sections (build once):** 3, 6, 8, 9, 11, 12, 13, 15, 16

---

## 8. Category Page Template — How It Differs

Category pages (house-washing, roof-cleaning, pressure-cleaning, gutter-cleaning, commercial-services, sealing-painting) use the same 16-section template as service pages, with two differences:

**Section 4 — Instead of 2 related service cards:**
Shows **cards for ALL child services** in that category. For example, the Pressure Cleaning category page shows cards for all 10 child services (Driveway, Pathway, Patio, Deck, Pool Area, Concrete, Retaining Wall, Fence, Window, Solar Panel).

**Section 5 — Instead of a 4-item accordion:**
Shows a **long-form category overview** (paragraph content describing the category). Not collapsible — just a standard content section.

See each category page's content file in the `services/` folder for the exact content.

---

## 9. Full Page List — All 49 Pages

### Core Pages (6)

| Page | URL | Content Doc |
|------|-----|-------------|
| Homepage | `/` | HANDOFF-2-CORE-PAGES.md |
| About Us | `/about-us/` | HANDOFF-2-CORE-PAGES.md |
| Contact Us | `/contact-us/` | HANDOFF-2-CORE-PAGES.md |
| Our Work | `/our-work/` | HANDOFF-2-CORE-PAGES.md |
| Services Archive | `/services/` | HANDOFF-2-CORE-PAGES.md |
| Thank You | `/thank-you/` | HANDOFF-2-CORE-PAGES.md |

### Category Pages (6) — NEW, need creating

| Page | URL | Content Doc |
|------|-----|-------------|
| House Washing | `/house-washing/` | `services/house-washing/house-washing.md` |
| Roof Cleaning | `/roof-cleaning/` | `services/roof-cleaning/roof-cleaning.md` |
| Pressure Cleaning | `/pressure-cleaning/` | `services/pressure-cleaning/pressure-cleaning.md` |
| Gutter Cleaning | `/gutter-cleaning/` | `services/gutter-cleaning/gutter-cleaning.md` |
| Commercial Services | `/commercial-services/` | `services/commercial/commercial-services.md` |
| Sealing & Painting | `/sealing-painting/` | `services/sealing-painting/sealing-painting.md` |

### Service Pages (37) — 3 new + 34 existing (update content)

**House Washing (2 existing):**

| Page | URL | Content File |
|------|-----|-------------|
| House Soft Washing | `/house-soft-washing/` | `services/house-washing/house-soft-washing.md` |
| House Pressure Washing | `/house-pressure-washing/` | `services/house-washing/house-pressure-washing.md` |

**Roof Cleaning (3 existing):**

| Page | URL | Content File |
|------|-----|-------------|
| Roof Soft Washing | `/roof-soft-washing/` | `services/roof-cleaning/roof-soft-washing.md` |
| Roof Pressure Washing | `/roof-pressure-washing/` | `services/roof-cleaning/roof-pressure-washing.md` |
| Biocide Roof Treatment | `/biocide-roof-treatment/` | `services/roof-cleaning/biocide-roof-treatment.md` |

**Pressure Cleaning (10 — 1 new + 9 existing):**

| Page | URL | Content File | Status |
|------|-----|-------------|--------|
| Driveway Cleaning | `/driveway-pressure-cleaning/` | `services/pressure-cleaning/driveway-pressure-cleaning.md` | Existing |
| Pathway Cleaning | `/pathway-pressure-cleaning/` | `services/pressure-cleaning/pathway-pressure-cleaning.md` | Existing |
| Patio Cleaning | `/patio-pressure-cleaning/` | `services/pressure-cleaning/patio-pressure-cleaning.md` | Existing |
| Deck Cleaning | `/deck-pressure-cleaning/` | `services/pressure-cleaning/deck-pressure-cleaning.md` | Existing |
| Pool Area Cleaning | `/pool-area-pressure-cleaning/` | `services/pressure-cleaning/pool-area-pressure-cleaning.md` | Existing |
| Concrete Cleaning | `/concrete-cleaning/` | `services/pressure-cleaning/concrete-cleaning.md` | **NEW** |
| Retaining Wall Cleaning | `/retaining-wall-cleaning/` | `services/pressure-cleaning/retaining-wall-cleaning.md` | Existing |
| Fence Cleaning | `/fence-cleaning/` | `services/pressure-cleaning/fence-cleaning.md` | Existing |
| Window Cleaning | `/exterior-window-cleaning/` | `services/pressure-cleaning/exterior-window-cleaning.md` | Existing |
| Solar Panel Cleaning | `/solar-panel-cleaning/` | `services/pressure-cleaning/solar-panel-cleaning.md` | Existing |

**Gutter Cleaning (0 additional — category page IS the service page)**

**Commercial Services (15 existing):**

| Page | URL | Content File |
|------|-----|-------------|
| Commercial Building Washing | `/commercial-building-washing/` | `services/commercial/commercial-building-washing.md` |
| Warehouse Cleaning | `/warehouse-pressure-cleaning/` | `services/commercial/warehouse-pressure-cleaning.md` |
| Loading Dock Cleaning | `/loading-dock-pressure-cleaning/` | `services/commercial/loading-dock-pressure-cleaning.md` |
| Car Park Cleaning | `/car-park-pressure-cleaning/` | `services/commercial/car-park-pressure-cleaning.md` |
| Bin Area Cleaning | `/bin-pad-cleaning/` | `services/commercial/bin-pad-waste-area-cleaning.md` |
| Shopfront Cleaning | `/retail-shopfront-cleaning/` | `services/commercial/retail-shopfront-exterior-cleaning.md` |
| Shopfront Window Cleaning | `/retail-shopfront-window-cleaning/` | `services/commercial/retail-shopfront-window-cleaning.md` |
| Graffiti Removal | `/graffiti-removal/` | `services/commercial/graffiti-removal.md` |
| Body Corporate Cleaning | `/body-corporate-pressure-cleaning/` | `services/commercial/body-corporate-pressure-cleaning.md` |
| Body Corporate Exterior | `/body-corporate-exterior-cleaning/` | `services/commercial/body-corporate-exterior-cleaning.md` |
| Body Corporate Walkway | `/body-corporate-walkway-cleaning/` | `services/commercial/body-corporate-walkway-cleaning.md` |
| Body Corporate Car Park | `/body-corporate-car-park-cleaning/` | `services/commercial/body-corporate-car-park-cleaning.md` |
| Body Corporate Entryway | `/body-corporate-entryway-cleaning/` | `services/commercial/body-corporate-entryway-cleaning.md` |
| Body Corporate Bin Area | `/body-corporate-bin-area-cleaning/` | `services/commercial/body-corporate-bin-area-cleaning.md` |
| Retirement Village | `/retirement-village-pressure-cleaning/` | `services/commercial/retirement-village-pressure-cleaning.md` |

**Sealing & Painting (7 — 2 new + 5 existing):**

| Page | URL | Content File | Status |
|------|-----|-------------|--------|
| Concrete Sealing | `/concrete-sealing/` | `services/sealing-painting/concrete-sealing.md` | **NEW** |
| Concrete Painting | `/concrete-painting/` | `services/sealing-painting/concrete-painting.md` | **NEW** |
| Driveway Sealing | `/driveway-clear-coat-sealing/` | `services/sealing-painting/driveway-clear-coat-sealing.md` | Existing |
| Walkway Sealing | `/walkway-clear-coat-sealing/` | `services/sealing-painting/walkway-clear-coat-sealing.md` | Existing |
| Driveway Painting | `/driveway-painting-coating/` | `services/sealing-painting/driveway-painting-coating.md` | Existing |
| Walkway Painting | `/walkway-painting-coating/` | `services/sealing-painting/walkway-painting-coating.md` | Existing |
| Driveway Anti-Slip Coating | `/driveway-anti-slip-coating/` | `services/sealing-painting/driveway-anti-slip-coating.md` | Existing |

---

## 10. How to Read the Content Files

Each page's content is in `HANDOFF-2-CORE-PAGES.md` (for core pages) or in the individual `.md` files in the `services/` folder (for service & category pages).

**At the top of every page's content** is an SEO block:
```
Page Title: Driveway Cleaning Brisbane | Jetstream AU     ← goes in <title> tag
Meta Description: Professional driveway cleaning in...     ← goes in meta description
Primary Keyword: driveway cleaning brisbane                ← for reference only (don't display)
URL Slug: /driveway-pressure-cleaning/                     ← the page URL
```

**Section numbers** match the template layout (Section 1 = top of page, working down).

**When you see this:**
```
→ See shared-blocks.md > "We Set a New Standard in Exterior Cleaning" Section
```
It means: insert the corresponding shared block from **Section 6 of this document** (HANDOFF-1-INSTRUCTIONS.md). It's the same content on every page — just insert the Bricks template.

**Accordion items** = collapsible sections (click to expand).

---

## 11. What to Remove From the Live Site

The current live site has placeholder content that must be removed or replaced. Here's exactly what to look for:

| Current Placeholder | Action |
|---------------------|--------|
| "John Doe / Founder CEO" | **Remove entirely** |
| "+30 Years Of Experience" / "+26 Years" | **Remove** (business is 3 years old) |
| "100+ Clients" | **Remove** (unverified) |
| "Greater Sydney" | **Replace** with Brisbane content from content files |
| "Coastal NSW" | **Replace** with Brisbane content from content files |
| "Parramatta, North Sydney, Blacktown, Surry Hills" | **Remove** (Sydney suburbs — wrong city) |
| "Brisbane, QLD 4000" | **Change to** "Brisbane, QLD" (no postcode — service area business) |
| "We are online 24/7" | **Remove** (not verified) |
| "250+ Google Reviews" | **Replace** with dynamic count from Google widget, or just show star rating |
| `(04) 9101 6876` | **Replace** with `0491 016 876` everywhere |
| Multi-step quote form | **Replace** with simple 4-field form (see Section 4) |
| 4-step "How We Work" process | **Replace** with 3-step version (see Section 6.4) |
| Generic service card descriptions | **Replace** with content from Section 6.2 |
| Dulux logo in brand bar | **Remove** (not a supplier) |

---

*End of Document 1. See HANDOFF-2-CORE-PAGES.md for core page content and the `services/` folder for all service & category page content (one file per page).*
