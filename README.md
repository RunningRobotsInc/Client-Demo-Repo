# Client Demo Repo — Prairie Ridge Manufacturing

This repository is a public, sanitized example of the kind of structured data Running Robots delivers to its clients.

It demonstrates the file structure, naming conventions, and content style of a real Running Robots client repository. The data inside represents a fictional client — **Prairie Ridge Manufacturing**, a mid-sized Iowa manufacturer of custom metal brackets, guards, and small welded assemblies — but the format, cadence, and curation choices are identical to what every Running Robots client receives.

> **Note:** Real Running Robots clients receive their own private repository. Prairie Ridge is a stand-in built specifically for this public demo so anyone can see the artifact format without violating client confidentiality.

---

## How this repository works

Every client gets a private GitHub repository shared exclusively with them. Each major service area lives in its own folder, and each folder contains:

1. **One Markdown file per reporting period** (named `YYYY-MM-<department>.md`).
2. **A `supporting/` folder** with the raw exports, transcripts, and source pulls that fed the MD file.

The MD files are designed to be readable by humans *and* easy for an AI assistant to query directly. Drop any MD file into your AI assistant of choice and ask it questions in plain English.

---

## Folder map

| Folder | What lives there |
|---|---|
| [`website/`](website/) | Traffic, behavior, page performance, Core Web Vitals |
| [`seo/`](seo/) | Search Console, rankings, on-page audits, backlinks |
| [`content/`](content/) | Blog, newsletter, gated assets, editorial calendar |
| [`ppc/`](ppc/) | Google Ads campaigns, keywords, search terms, spend |
| [`integrations/`](integrations/) | What's connected, where data flows, how it's authed |
| [`automations/`](automations/) | Scheduled and triggered workflows running for this client |
| [`transcripts/`](transcripts/) | Meeting notes and call summaries |

---

## How each MD file is built

1. **A per-client data pipeline** pulls fresh data from the connected sources (Google Analytics, Google Search Console, Search Atlas, Screaming Frog, Google Ads, Google Drive, Zoho CRM, Zoho Projects, meeting transcripts).
2. **The body of the file is built directly from clean API responses** — no LLM rewrites, no interpretation. Tables, numbers, and rankings come straight from source.
3. **AI writes one section only**: the short summary at the top of every report, comparing the current period to the trailing four months and flagging anomalies.
4. **A Running Robots team member reviews the file** before it ships. Approval is required before anything is committed to the client's repo.
5. **Once approved, the file is committed** to the client's private GitHub repository (or this public demo, in this case).

This split — clean API data in the body, AI only in the summary, human accountable for approval — is a deliberate trust and accuracy decision. It's covered in detail in our CIRAS AI Summit talk.

---

## Try it yourself

The fastest way to see why we deliver data this way is to:

1. Clone or download this repo.
2. Open any MD file in your AI assistant (Claude, ChatGPT, Gemini, whatever you use).
3. Ask it a question. Examples:
   - "Which capability page lost the most traffic month-over-month in April?"
   - "What's our worst-performing PPC campaign this quarter?"
   - "Summarize the conversation from the March quarterly review."
   - "What ag-equipment search terms should we be ranking for but aren't?"

The whole point of this format is that the data travels with you — into your tools, your workflows, your decisions — instead of staying trapped in a dashboard.

---

## About the demo client

**Prairie Ridge Manufacturing** is a fictional mid-sized Iowa manufacturer of custom metal brackets, guards, and small welded assemblies. They serve agriculture, food processing, and industrial equipment OEMs, primarily in the Midwest.

**Profile**
- Headquarters: Cedar Rapids, Iowa
- Founded: 1986
- Employees: ~85
- Annual revenue: ~$18M
- Facility: 52,000 sq ft
- Certifications: ISO 9001:2015, AWS D1.1 (welding), food-safe finishing capability

**Capabilities**
- Fiber laser cutting (up to 1" carbon steel, 1/2" stainless, 1/2" aluminum)
- CNC machining (3-axis and 5-axis, the 5-axis cell came online March 2026)
- Press brake forming (up to 350-ton)
- MIG, TIG, and robotic welding
- In-house powder coating
- CMM-based quality inspection
- Engineering / DFM consultation

**Customer mix**
- Agriculture equipment OEMs (largest segment)
- Food processing equipment manufacturers
- Industrial equipment / heavy machinery

**Sales motion**
- RFQ-driven (Request for Quote)
- Quote turnaround: 3–5 business days
- Typical project: $5K–$200K
- ~25% close rate on RFQs
- Repeat business via purchase orders dominates revenue

Reporting period: monthly. Cadence: file delivered first business week of the following month, after Running Robots review.

---

## About Running Robots

Running Robots is an AI-first marketing partner. We redesigned our company around AI rather than bolting it onto old workflows, and this repository is one of the artifacts our clients walk away with every month.

Learn more: [therunningrobots.com](https://therunningrobots.com)

Talk to us: [hello@therunningrobots.com](mailto:hello@therunningrobots.com)
