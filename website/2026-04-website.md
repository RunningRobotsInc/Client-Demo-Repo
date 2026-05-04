# Prairie Ridge Manufacturing — Website Performance

_Reporting period: April 1–30, 2026_
_Prepared: May 4, 2026 by Running Robots_
_Reviewed and approved by: Meegan Campbell_

---

## Summary (AI-generated)

April was the strongest traffic month of the trailing five-month window. Total sessions reached **14,082**, up **18.4% MoM** and **31.2% YoY**, driven primarily by organic growth on the new **5-axis CNC machining** capability pages launched March 8. RFQ submissions held flat at **78** despite the lift in sessions — the conversion rate softened from 0.79% in March to **0.55%** in April. The most likely cause is a **9-point bounce-rate increase on `/capabilities/cnc-machining`** following the April 2 deploy, which appears to have introduced an INP regression (April INP: **142ms**, vs. March INP: **98ms**). Core Web Vitals on every other page held steady. Recommend prioritizing the INP fix on the CNC machining page in May.

---

## Top-line metrics

| Metric | April 2026 | March 2026 | MoM | YoY |
|---|---|---|---|---|
| Sessions | 14,082 | 11,895 | +18.4% | +31.2% |
| Users | 11,326 | 9,704 | +16.7% | +28.4% |
| New users | 8,790 | 7,512 | +17.0% | +29.1% |
| Pageviews | 38,447 | 33,118 | +16.1% | +24.7% |
| Avg. engagement time | 1m 52s | 2m 01s | -7.5% | +3.2% |
| Bounce rate | 41.2% | 38.6% | +2.6 pts | -1.4 pts |
| RFQ submissions | 78 | 78 | 0.0% | +13.0% |
| RFQ conversion rate | 0.55% | 0.66% | -0.11 pts | -0.06 pts |

Source: GA4 export `supporting/ga4-export-2026-04.csv`

---

## Channel breakdown

| Channel | Sessions | Share | MoM | RFQ Conv. Rate |
|---|---|---|---|---|
| Organic Search | 7,318 | 52.0% | +24.1% | 0.68% |
| Direct | 2,535 | 18.0% | +6.2% | 1.18% |
| Paid Search | 1,930 | 13.7% | +12.4% | 0.41% |
| Referral | 1,127 | 8.0% | +21.0% | 0.62% |
| Email | 718 | 5.1% | +9.8% | 1.95% |
| Social | 309 | 2.2% | +18.0% | 0.32% |
| Other | 145 | 1.0% | -3.1% | 0.00% |

Direct traffic continues to convert at nearly 2x organic — consistent with our hypothesis that Direct is dominated by repeat customers and referred prospects who already know the brand.

Source: GA4 acquisition report (default channel grouping).

---

## Top pages by sessions

| Page | Sessions | RFQ Conv. Rate | Avg. Engagement |
|---|---|---|---|
| `/capabilities/cnc-machining` | 4,210 | 1.4% | 1m 38s |
| `/capabilities/laser-cutting` | 2,114 | 1.9% | 2m 47s |
| `/quote` | 1,855 | 18.6% | 0m 59s |
| `/capabilities` | 1,602 | 1.7% | 1m 51s |
| `/industries/agriculture` | 1,288 | 0.9% | 3m 22s |
| `/capabilities/welding` | 1,041 | 1.4% | 2m 14s |
| `/capabilities/press-brake` | 902 | 1.2% | 2m 02s |
| `/case-studies/iowa-ag-oem-bracket-program` | 811 | 1.8% | 4m 11s |
| `/resources/dfm-checklist` | 759 | 0.5% | 0m 48s |
| `/about` | 644 | 0.6% | 1m 12s |

Source: `supporting/page-performance-detail-2026-04.csv` (top 50 pages included in export).

---

## Core Web Vitals

| Metric | April 2026 | March 2026 | Threshold | Status |
|---|---|---|---|---|
| LCP (75th pct) | 2.1s | 2.0s | < 2.5s | Good |
| INP (75th pct) | **142ms** | 98ms | < 200ms | Needs Improvement |
| CLS (75th pct) | 0.04 | 0.05 | < 0.1 | Good |
| TTFB (75th pct) | 0.42s | 0.44s | < 0.8s | Good |
| FCP (75th pct) | 1.3s | 1.3s | < 1.8s | Good |

INP regression is isolated to `/capabilities/cnc-machining`. All other pages held within 95–105ms.

Source: Chrome UX Report (CrUX) + Screaming Frog crawl `supporting/screaming-frog-crawl-2026-04.csv`.

---

## Conversion paths (assisted)

Top three conversion-assisting paths to RFQ submission (multi-touch attribution, 30-day window):

1. Organic → Direct → RFQ (24 conversions, 31% of total)
2. Organic → Email → RFQ (13 conversions, 17%)
3. Paid → Organic → RFQ (10 conversions, 13%)

Engineers tend to research a capability page first, leave, and return via Direct or a CRM-triggered email before submitting. Median path length: **3.2 sessions**, median window: **9 days**.

Source: GA4 path-exploration report.

---

## Site health flags

- **INP regression** on `/capabilities/cnc-machining` — first detected April 5, traced to a third-party tolerance-comparison widget added in the April 2 deploy.
- **404 spike** on `/capabilities/3-axis-cnc-machining` — 412 hits in April (zero in March). Old URL referenced in an Iowa Manufacturing Today article. Recommend a 301 redirect to `/capabilities/cnc-machining`.
- **Sitemap drift** — 4 new capability pages live but not yet in `sitemap.xml`. Auto-regenerated April 28, awaiting next crawl.

Source: Screaming Frog April 28 crawl (`supporting/screaming-frog-crawl-2026-04.csv`).

---

## What we recommend for May

1. **Fix INP regression on `/capabilities/cnc-machining`** — defer the third-party tolerance-comparison widget below the fold or replace with a server-rendered component.
2. **301 redirect `/capabilities/3-axis-cnc-machining` → `/capabilities/cnc-machining`** to recover lost traffic from the Iowa Manufacturing Today reference.
3. **A/B test the `/quote` form** — current 18.6% conversion rate is healthy for an RFQ form, but consolidating the "Drawing upload" and "Project description" fields could capture more value from the April session lift.

---

## Supporting documents

- `supporting/ga4-export-2026-04.csv` — full GA4 export (sessions, users, behavior by page).
- `supporting/page-performance-detail-2026-04.csv` — top 50 pages with engagement and conversion metrics.
- `supporting/screaming-frog-crawl-2026-04.csv` — site crawl, status codes, Core Web Vitals per page.
- `supporting/conversion-paths-2026-04.csv` — multi-touch attribution paths.
