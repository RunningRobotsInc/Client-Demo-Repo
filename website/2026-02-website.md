# Prairie Ridge Manufacturing — Website Performance

_Reporting period: February 1–28, 2026_
_Prepared: March 6, 2026 by Running Robots_
_Reviewed and approved by: Meegan Campbell_

---

## Summary (AI-generated)

February traffic was held back by an LCP regression on the homepage that landed with the **Feb 7 deploy**. Sessions still rose **6.1% MoM** to **10,418** — but the trajectory should have been stronger. The hero image on the homepage was oversized at 2.4MB, pushing LCP to **2.7s** (up from 2.0s in January). RFQ submissions softened **8.2% MoM** to **56**. Image was optimized and redeployed February 28; expect a meaningful rebound in March. Aside from the hero image issue, all other Core Web Vitals held steady.

---

## Top-line metrics

| Metric | February 2026 | January 2026 | MoM |
|---|---|---|---|
| Sessions | 10,418 | 9,820 | +6.1% |
| Users | 8,612 | 8,118 | +6.1% |
| RFQ submissions | 56 | 61 | -8.2% |
| RFQ conversion rate | 0.54% | 0.62% | -0.08 pts |

---

## Channel breakdown

| Channel | Sessions | MoM |
|---|---|---|
| Organic Search | 4,994 | +7.0% |
| Direct | 2,294 | +2.4% |
| Paid Search | 1,569 | +4.4% |
| Referral | 831 | +18.4% |
| Email | 533 | +9.0% |
| Social | 197 | -8.4% |

---

## Top pages by sessions

| Page | Sessions | Conv. Rate |
|---|---|---|
| `/capabilities/cnc-machining` | 3,488 | 1.4% |
| `/quote` | 1,422 | 21.0% |
| `/capabilities` | 1,318 | 1.8% |
| `/industries/agriculture` | 944 | 1.1% |
| `/capabilities/welding` | 814 | 1.4% |
| `/capabilities/press-brake` | 712 | 1.2% |
| `/case-studies/iowa-ag-oem-bracket-program` | 502 | 1.4% |
| `/about` | 488 | 0.7% |
| `/blog/dfm-checklist-for-ag-oems` | 388 | 2.3% |
| `/contact` | 311 | 12.2% |

---

## Core Web Vitals — incident detail

| Metric | February 2026 | January 2026 | Status |
|---|---|---|---|
| LCP (75th pct) | **2.7s** | 2.0s | Needs Improvement (regression) |
| INP (75th pct) | 102ms | 99ms | Good |
| CLS (75th pct) | 0.05 | 0.05 | Good |

**Incident:** Feb 7 deploy introduced an oversized homepage hero image (2.4MB unoptimized PNG). LCP for homepage and templated pages spiked from 1.8s to 3.1s overnight. Detected Feb 9 in our daily Screaming Frog audit. Fix shipped Feb 28 — image converted to WebP, resized, lazy-loaded below the fold.

Lesson: image-size pre-deploy check has been added to the Prairie Ridge deploy pipeline (March 1).

---

## What we recommended for March (and what shipped)

| Recommendation | Status |
|---|---|
| Optimize homepage hero image | Shipped Feb 28 |
| Add image-size check to deploy pipeline | Shipped Mar 1 |
| Continue 5-axis CNC launch readiness | On track for Mar 8 |

---

## Supporting documents

- `supporting/ga4-export-2026-02.csv`
- `supporting/screaming-frog-crawl-2026-02.csv`
- `supporting/incident-feb-7-lcp-regression.md`
