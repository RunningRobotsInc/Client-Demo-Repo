# Prairie Ridge Manufacturing — Website Performance

_Reporting period: March 1–31, 2026_
_Prepared: April 6, 2026 by Running Robots_
_Reviewed and approved by: Meegan Campbell_

---

## Summary (AI-generated)

March marked a clear rebound from February's site-speed drag. Sessions grew **14.2% MoM** to **11,895**, recovering most of what the LCP regression cost us. The **5-axis CNC capability launch (March 8)** was the month's headline event — within 23 days the new capability pages drove **2,114 sessions** and contributed to **27 RFQ submissions**. Core Web Vitals stabilized after the February incident: LCP held at 2.0s, INP at 98ms. RFQ conversion rate of **0.66%** is the best monthly figure since November 2025. Recommend continuing investment in 5-axis CNC promotion through Q2.

---

## Top-line metrics

| Metric | March 2026 | February 2026 | MoM |
|---|---|---|---|
| Sessions | 11,895 | 10,418 | +14.2% |
| Users | 9,704 | 8,612 | +12.7% |
| New users | 7,512 | 6,602 | +13.8% |
| Pageviews | 33,118 | 28,902 | +14.6% |
| Avg. engagement time | 2m 01s | 1m 48s | +12.0% |
| Bounce rate | 38.6% | 42.1% | -3.5 pts |
| RFQ submissions | 78 | 56 | +39.3% |
| RFQ conversion rate | 0.66% | 0.54% | +0.12 pts |

---

## Channel breakdown

| Channel | Sessions | Share | MoM |
|---|---|---|---|
| Organic Search | 5,894 | 49.6% | +18.0% |
| Direct | 2,388 | 20.1% | +4.1% |
| Paid Search | 1,718 | 14.4% | +9.5% |
| Referral | 932 | 7.8% | +12.2% |
| Email | 654 | 5.5% | +22.8% |
| Social | 262 | 2.2% | +9.6% |
| Other | 47 | 0.4% | -50.0% |

---

## Top pages by sessions

| Page | Sessions | Conv. Rate |
|---|---|---|
| `/capabilities/cnc-machining` | 3,802 | 1.7% |
| `/capabilities/laser-cutting` | 1,114 | 1.9% (5-axis announcement linked here) |
| `/quote` | 1,602 | 22.1% |
| `/capabilities` | 1,488 | 2.2% |
| `/industries/agriculture` | 1,002 | 1.1% |
| `/capabilities/welding` | 902 | 1.4% |
| `/capabilities/press-brake` | 814 | 1.2% |
| `/case-studies/iowa-ag-oem-bracket-program` | 612 | 1.7% |
| `/about` | 588 | 0.7% |
| `/blog/5-axis-cnc-launch` | 502 | 5.4% |

---

## Core Web Vitals

| Metric | March 2026 | February 2026 | Status |
|---|---|---|---|
| LCP (75th pct) | 2.0s | 2.7s | Good (recovered) |
| INP (75th pct) | 98ms | 102ms | Good |
| CLS (75th pct) | 0.05 | 0.05 | Good |
| TTFB (75th pct) | 0.44s | 0.46s | Good |
| FCP (75th pct) | 1.3s | 1.4s | Good |

The February LCP regression was traced to an oversized hero image on the homepage (deployed Feb 7). Image was optimized and re-deployed Feb 28; March numbers reflect the recovery.

---

## Site health flags

- **5-axis CNC pages** indexed within 5 days of launch — ahead of typical timeline.
- **0 critical 404s** for the month.
- **1 sitemap update** required after launch — auto-handled by the deploy pipeline.

---

## What we recommended for April (and what shipped)

| Recommendation | Status |
|---|---|
| Promote 5-axis CNC through paid + organic | Shipped (5-Axis CNC Launch campaign live Mar 14) |
| Refresh tolerance stack-up content | Shipped (Apr 19) |
| Add internal links from /resources to 5-axis CNC | Shipped Mar 22 |

---

## Supporting documents

- `supporting/ga4-export-2026-03.csv`
- `supporting/page-performance-detail-2026-03.csv`
- `supporting/screaming-frog-crawl-2026-03.csv`
