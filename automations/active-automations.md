# Prairie Ridge Manufacturing — Active Automations

_Last updated: May 1, 2026_
_Owner: Running Robots — Tiffany Voss (lead engineer)_

This file lists every scheduled or triggered workflow currently running for Prairie Ridge. Each automation has a clear trigger, a documented action, and an owner accountable for its output.

---

## Summary

| Automation | Trigger | Cadence | Owner | Status |
|---|---|---|---|---|
| Monthly MD file generation | Cron (1st business day of month) | Monthly | RR Department Heads | Active |
| Weekly site crawl | Cron (Sunday 02:00 CT) | Weekly | RR Engineering | Active |
| Daily GA4 anomaly check | Cron (06:00 CT) | Daily | RR Account Mgmt | Active |
| RFQ-to-CRM sync | Form submit (real-time) | On-event | Prairie Ridge IT | Active |
| Lead-routing notifications | Zoho CRM record creation | On-event | Prairie Ridge Sales | Active |
| Abandoned-RFQ follow-up | 48 hours post-form-start | On-event | Prairie Ridge Sales | Active |
| Newsletter scheduling | Editorial calendar (Zoho Projects task) | Bi-weekly | RR Content Team | Active |
| LinkedIn post publishing | Editorial calendar | 3x/week | RR Content Team | Active |
| Closed-won feedback loop | Zoho CRM stage change | On-event | RR Reporting Pipeline | Active |
| Quarterly business review prep | Cron (last Friday of quarter) | Quarterly | RR Account Mgmt | Active |

---

## Automation details

### 1. Monthly MD file generation

**Trigger:** First business day of each month, 04:00 CT.
**Action:** For each department (website, seo, content, ppc), the per-department pipeline runs:
1. Pull data from connected sources for the previous month.
2. Render the body of the MD file from API responses (no LLM in this step).
3. Send to Anthropic Claude API for summary generation only.
4. Save draft to `drafts/<dept>-<month>.md`.
5. Notify the department head via Zoho Cliq.
6. Department head reviews, edits if needed, and approves.
7. Approved file is committed to the client's GitHub repository.
8. Client account manager (Meegan) is tagged for final review and client communication.

**Owner:** RR Department Heads. Override-able by Adam.

**File:** [`monthly-report.md`](monthly-report.md)

---

### 2. Weekly site crawl

**Trigger:** Every Sunday at 02:00 CT.
**Action:** Screaming Frog crawl of `prairieridgemfg.com`, all subdomains, capped at 50K URLs. Compares against previous week's crawl. Flags:
- New 404s
- Status code regressions (200 → 5xx)
- Title/meta changes on top-50 pages
- Core Web Vitals deltas > 100ms LCP / 50ms INP

**Output:** Delta report posted to Zoho Cliq #prairie-ridge-engineering. Critical flags trigger pager alert to Tiffany.

---

### 3. Daily GA4 anomaly check

**Trigger:** Daily at 06:00 CT.
**Action:** Compare yesterday's metrics to trailing 28-day median. Flag anomalies > 3 std dev:
- Sessions per channel
- Conversions per top page
- Bounce rate per top-10 pages

**Output:** If anomaly detected, slack-style alert in Zoho Cliq #prairie-ridge-data with the data point and a link to the GA4 explore.

---

### 4. RFQ-to-CRM sync

**Trigger:** Form submission on `/quote`.
**Action:**
1. Form data hits HubSpot endpoint.
2. Webhook fires to Zoho CRM, creating a new Lead (or matching existing Account/Contact).
3. Deal record auto-created with Stage = "RFQ Received", Source = "Website".
4. Notification routed to assigned sales engineer (round-robin among 3 reps).
5. Sales engineer has 4 business hours SLA to acknowledge.

**Owner:** Prairie Ridge IT (webhook); Prairie Ridge Sales (SLA).

---

### 5. Lead-routing notifications

**Trigger:** New Lead record in Zoho CRM (any source).
**Action:** Routes to the appropriate sales engineer based on:
- Industry match (Ag → Alex Diaz, Food → Jordan Pham, Industrial → Sam Whitley)
- Capacity check (current open deals < 25)
- Round-robin tiebreaker

If unassigned after 30 minutes, escalates to Sales Manager (Mike Brennan).

**File:** [`lead-routing.md`](lead-routing.md)

---

### 6. Abandoned-RFQ follow-up

**Trigger:** 48 hours after form-start event without form-completion event.
**Action:** Sends a personalized email to the captured visitor email asking if they ran into trouble with the form. Email content is templated but includes:
- The capability page they were on when they started
- A direct calendar link to the assigned sales engineer
- A "respond to this email and I'll quote it manually" option

**Conversion rate (last 90 days):** 11.2% of recipients re-engage. Of those, 4.8% become an RFQ submission.

**Owner:** Prairie Ridge Sales. Email content reviewed quarterly by Running Robots.

**File:** [`abandoned-rfq-followup.md`](abandoned-rfq-followup.md)

---

### 7. Newsletter scheduling

**Trigger:** Editorial calendar task in Zoho Projects marked "Ready to schedule" by content team.
**Action:** Pulls approved content into Mailchimp draft, sets send time per editorial calendar, schedules. Sends to "Engineering Buyers" segment by default unless overridden.

---

### 8. LinkedIn post publishing

**Trigger:** Editorial calendar task in Zoho Projects marked "Approved for LinkedIn" with scheduled date.
**Action:** Pulls approved post copy + images, schedules post via LinkedIn Marketing API at the specified time.

**Cadence:** Mon / Wed / Fri at 09:30 CT typically.

---

### 9. Closed-won feedback loop

**Trigger:** Deal stage changes to "Closed Won" in Zoho CRM.
**Action:**
1. Capture the deal's first-touch and last-touch attribution.
2. Look up if the contact ever submitted an RFQ via website.
3. If yes, attribute the closed-won amount back to the original campaign / source.
4. Push the offline conversion to Google Ads (for ads-sourced deals only).
5. Update the trailing 90-day cohort attribution table used in PPC reports.

**Why:** This is what makes the "closed-won deals (90d)" line in PPC reports accurate. Without this loop, we'd be reporting on form-fills, not revenue.

---

### 10. Quarterly business review prep

**Trigger:** Last Friday of the quarter, 10:00 CT.
**Action:** Aggregates the 13-week rolling data across all four reporting departments into a single summary MD file (`quarterly-review-YYYY-Q?.md`). Preps an agenda for the QBR meeting with key questions for the Prairie Ridge leadership team.

**Output:** Draft delivered to Meegan for review on the Monday before the QBR.

---

## Adding or changing automations

Any new automation request flows through Zoho Projects under the "Prairie Ridge — Automation Backlog" task list. Department heads triage. Changes to active automations require change control: a documented diff, an owner sign-off, and a 7-day testing window before going live.
