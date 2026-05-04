# Prairie Ridge Manufacturing — Active Integrations

_Last updated: May 1, 2026_
_Owner: Running Robots — Tiffany Voss (lead engineer)_

This file lists every system Prairie Ridge has connected to the Running Robots data pipeline, what data flows from it, who owns the auth, and how to refresh credentials when they expire.

---

## Summary

| System | Type | Purpose | Auth | Data Owner | Refresh cadence |
|---|---|---|---|---|---|
| Google Analytics 4 | Read | Traffic, behavior, conversion data | OAuth (Google Service Account) | RR Engineering | Token: 60-day rolling |
| Google Search Console | Read | Search queries, pages, indexing status | OAuth (Google Service Account) | RR Engineering | Token: 60-day rolling |
| Search Atlas | Read | Rankings, audits, AEO/LLM visibility | API key | RR Engineering | Quarterly |
| Screaming Frog (cloud) | Read | Site crawls, technical health | API key | RR Engineering | Quarterly |
| Google Ads | Read | Spend, campaigns, keywords, search terms | OAuth (Google Service Account) | RR Engineering | Token: 60-day rolling |
| Google Drive | Read | Quote logs, sales spreadsheets, design files | OAuth (Google Service Account) | RR Engineering | Token: 60-day rolling |
| Mailchimp | Read | Newsletter sends, opens, clicks, unsubscribes | API key | RR Engineering | Quarterly |
| Zoho CRM | Read | Accounts, contacts, deals, RFQ pipeline | OAuth (refresh token) | Prairie Ridge IT | 12-month rolling |
| Zoho Projects | Read | Tasks, milestones, project status | OAuth (shared with CRM) | Prairie Ridge IT | 12-month rolling |
| Avoma | Read | Meeting recordings, transcripts | API key | RR Engineering | Quarterly |
| LinkedIn Company Page | Read | Posts, impressions, engagements, followers | OAuth (Marketing Developer Platform) | RR Engineering | 60-day rolling |
| HubSpot Forms | Read | Form submissions on gated assets | API key | RR Engineering | Annual |

---

## GA4 configuration

- Property ID: `properties/472019283` (sanitized)
- Default channel grouping: GA4 default (Q1 2026 onward — matches the consolidated channel taxonomy used in `website/*.md` reports).
- Custom events tracked:
  - `rfq_submission` — fires on /quote success page
  - `gated_asset_download` — fires on PDF download success
  - `phone_click` — fires on tel: link
  - `email_click` — fires on mailto: link

GA4 to Zoho CRM identity stitching is performed via email match on RFQ submission; client_id is also captured for multi-touch attribution analysis.

---

## Google Search Console

- Property: `https://prairieridgemfg.com/` (URL-prefix property)
- Performance data pulled daily for the rolling 16-month window.

---

## Search Atlas

- Project: Prairie Ridge Manufacturing (Project ID: 88241)
- Tracked keywords: 200 (refreshed quarterly with the SEO team)
- Audit cadence: monthly full crawl + weekly delta crawl
- LLM Visibility tracking: 50 priority queries across 4 engines (Google AI Overviews, ChatGPT Search, Perplexity, Claude Search)

---

## Google Ads

- MCC account: linked to Running Robots master account
- Customer ID: `XXX-XXX-1842` (sanitized)
- Active campaigns (April 2026): 6
- Conversion tracking: GA4 imported conversions + offline conversion upload (closed-won deals from Zoho)

---

## Zoho CRM & Projects

- Org ID: `848019283` (sanitized)
- CRM modules in scope: Accounts, Contacts, Deals (RFQ pipeline), Quotes
- Projects in scope: All client-facing project work (deliverables, milestones, status)
- Closed-won attribution: deals with Stage = "Closed Won" and Source = "Website" (RFQ form match)

---

## Avoma

- Workspace: Prairie Ridge Manufacturing
- Recording targets: All Running Robots–led calls (monthly check-ins, strategy sessions, ad-hoc working sessions)
- Transcript export: weekly batch into `transcripts/`

---

## Authentication & Security

- All OAuth tokens stored in 1Password (Running Robots — Prairie Ridge vault). Two team members have read access: lead engineer + account manager.
- API keys are rotated annually unless flagged for security incident.
- No production database access; all reads are via vendor-provided APIs only.
- Audit log of all access requests is maintained in Zoho Projects under the "Prairie Ridge — Integration Audit" task list.

---

## What this means for reporting

These integrations are what make every MD file in this repo possible. When a department head pulls together a monthly report, they're querying these sources directly. The pipelines are configured per-client by department heads at Running Robots — not a generic template.
