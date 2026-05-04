# Incident Response Call — Feb 7 LCP Regression

_Date: February 9, 2026_
_Duration: 22 minutes_
_Source: Avoma recording, transcribed and summarized by Running Robots_

---

## Attendees

**Prairie Ridge Manufacturing**
- Sarah Linder — Marketing Manager

**Running Robots**
- Tiffany Voss — Lead Engineer
- Meegan Campbell — Account Manager

---

## Summary (AI-generated)

Quick incident call after the Feb 7 deploy introduced a homepage LCP regression. Tiffany flagged the issue from the daily Screaming Frog run on Feb 8. Root cause: an unoptimized 2.4MB hero image. Tiffany's team will optimize and re-deploy by Feb 28. Sarah confirmed leadership awareness. New automation will be added to the deploy pipeline to catch oversized image regressions before they reach production.

---

## What happened

Tiffany: "Feb 7 deploy went out at 3 PM. By 6 PM the daily LCP across the homepage had jumped from 1.9s to 3.1s. We caught it in the Sunday automated crawl. The culprit is the new hero image — it's 2.4MB and it's not optimized at all. Looks like the source PNG got pushed straight into production."

Sarah: "Who pushed it?"

Tiffany: "Web team — looks like a routine deploy, no malicious intent. They didn't have an automated check on image size. We can fix it on our side by adding the check to the deploy pipeline."

Sarah: "Okay. What's the impact?"

Meegan: "Estimated 8–12% drop in landing-page conversion until we fix it. We're seeing it in the GA4 numbers already — Saturday and Sunday were softer than expected."

---

## Resolution plan

| # | Step | Owner | Done by |
|---|---|---|---|
| 1 | Convert hero image to WebP, target < 200KB | RR Engineering | Feb 12 |
| 2 | Implement lazy-loading below the fold | RR Engineering | Feb 14 |
| 3 | QA on staging | RR + Sarah | Feb 21 |
| 4 | Re-deploy to production | RR Engineering | Feb 28 |
| 5 | Add image-size check to deploy pipeline | RR Engineering | Mar 1 |
| 6 | Document learning in `incident-feb-7-lcp-regression.md` | RR Engineering | Mar 3 |

---

## Communication

- Sarah will brief Mike Brennan internally; no client-facing communication needed.
- Will be referenced in February's website report.
- Daily LCP monitoring continues; Tiffany will flag if numbers don't recover by March 7.

---

## Action items

| # | Item | Owner |
|---|---|---|
| 1 | Image optimization and re-deploy | Tiffany |
| 2 | Pipeline check addition | Tiffany |
| 3 | Internal Prairie Ridge briefing | Sarah |
| 4 | February website report annotation | Meegan |

---

## Next meeting

Regular monthly check-in: Feb 25, 2026, 10:00 CT.
