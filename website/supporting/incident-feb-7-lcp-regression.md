# Incident: February 7, 2026 — Homepage LCP Regression

_Severity: Medium — converted to Low after fix_
_Detected: February 9, 2026 (Sunday automated crawl)_
_Resolved: February 28, 2026 (re-deploy)_
_Owner: Tiffany Voss (Running Robots Engineering)_

---

## Timeline

| When | What |
|---|---|
| 2026-02-07 15:00 CT | Routine deploy went live including new homepage hero image (2.4MB unoptimized PNG) |
| 2026-02-08 02:00 CT | Sunday Screaming Frog crawl ran |
| 2026-02-09 09:00 CT | Tiffany flagged LCP jump from 1.9s → 3.1s in delta report |
| 2026-02-09 11:00 CT | Incident call with Sarah (see `transcripts/2026-02-incident-response.md`) |
| 2026-02-12 EOD | Image converted to WebP, resized to < 200KB |
| 2026-02-14 EOD | Lazy-loading implemented below the fold |
| 2026-02-21 EOD | QA on staging completed |
| 2026-02-28 14:00 CT | Re-deployed to production |
| 2026-03-01 09:00 CT | Image-size check added to deploy pipeline |
| 2026-03-03 EOD | Post-incident review documented |

---

## Root cause

A 2.4MB unoptimized PNG was committed to the homepage hero asset directory and pushed to production without size validation. The deploy pipeline at the time did not check image dimensions or file size before publishing.

---

## Impact

- LCP on `/` and templated pages spiked from 1.9s to 3.1s for ~21 days
- Estimated 8–12% drop in landing-page conversion rate during the window
- February RFQ submissions came in at 56 — modeled estimate without the regression: 64–66
- ~10 RFQs lost over the incident window

---

## Resolution

- Hero image converted to WebP, resized to viewport-appropriate dimensions, lazy-loaded
- Deploy pipeline now runs an image-size check that blocks deploys with images > 500KB unless explicitly overridden
- Override requires a documented reason and approval from RR Engineering lead

---

## Lessons learned

1. **Daily automated crawl works.** Detection happened 30 hours after deploy — well within our SLA. Without the automation, this would have been caught much later (probably by a client noticing slowness).
2. **Pre-deploy validation matters more than post-deploy detection.** The fix prevents the next occurrence rather than relying on detection.
3. **Communication scope should include the client immediately.** Sarah was looped in on Day 1, not after the fix was deployed. This kept the relationship transparent.

---

## Related files

- [`transcripts/2026-02-incident-response.md`](../../transcripts/2026-02-incident-response.md)
- [`website/2026-02-website.md`](../2026-02-website.md)
- [`website/2026-03-website.md`](../2026-03-website.md)
