# Reader Profile — Advanced Marketing Background

> **How to use this file:** Paste the contents of this file into your AI assistant (Claude, ChatGPT, Gemini) **alongside** any monthly report from this repo before asking your questions. The AI will use it to tailor its answers to a reader with this background. This is one of two profile examples in `/profiles/` — the companion file is `limited-marketing-background.md`.

---

## Persona — Manny Facture, VP of Sales & Marketing, Prairie Ridge Manufacturing

<img src="./images/manny-facture.jpg" alt="Manny Facture, VP of Sales & Marketing at Prairie Ridge Manufacturing" width="280" align="right">

I'm Manny. I joined Prairie Ridge in 2024 after eleven years at John Deere on the OEM industrial supply marketing team. MBA from Iowa with a marketing concentration. I report directly to the owner (Dale) and I'm internally accountable for revenue growth, lead quality, and brand presence.

I evaluated four agencies before hiring Running Robots and I personally vetted the proposal. I read every monthly report cover-to-cover, and I pull the supporting CSVs into Looker for my own dashboards. I expect to be **the most marketing-literate person in the room** at Prairie Ridge — including with our agency partners.

---

## How I think about marketing

- B2B / industrial. Long sales cycles, low-volume / high-AOV deal flow, account-based motion overlaid on inbound.
- **Lead quality > lead volume.** Topline CPL doesn't impress me. CPL by closed-won cohort, segmented by ICP fit, does.
- I treat last-click as a useful approximation, not as gospel. I want multi-touch context when the spend question is non-trivial.
- I will push back on any recommendation that doesn't address obvious confounding variables. If you tell me CVR dropped, I expect you to have already ruled out (or named) the seasonality, traffic-mix, attribution-window, and tag-bloat explanations.
- I read industry research (LinkedIn B2B Institute, Marketing Week, Gartner). I'll reference frameworks: 95-5 rule, ICP-fit scoring, CAC payback, share-of-search, dark social. I expect fluency with all of them.

---

## How to talk to me

### Lead with data density. Reserve prose for interpretation I wouldn't reach on my own.

Open with the metric matrix. Don't tell me what the number means before I've seen the number. Don't summarize a table I'm about to read.

### Speak in our shared vocabulary. No translation needed.

INP · LCP · CLS · CrUX · ICP · MQL · SQL · last-click vs. linear vs. data-driven attribution · CPL · CAC · LTV · payback period · share-of-search · branded vs. non-branded · dark social · ABM · intent data · top/mid/bottom-funnel · 95-5 rule · view-through · assisted conversion · query-level intent classification — all fair game.

### Bring tradeoffs, not single-path recommendations.

> ❌ "Recommend pausing the Competitor — Tier-1 Fabricator campaign."

> ✅ "**Recommend pausing Competitor — Tier-1 Fabricator** ($542 CPL, 5.2% bounce-on-landing, intent mismatch confirmed by query-level review). Two viable reallocations:
> **(a)** Push the $1.2K/mo into 5-Axis CNC Launch — CPL trending toward $120 if April's curve holds, highest expected near-term ROI.
> **(b)** Hold the budget and stand up a new Industry — Food Processing campaign — weaker historical data but addresses our weakest vertical and aligns with the 2026 strategic plan.
> **(a)** is the higher-confidence move; **(b)** is the higher-strategic move. Defaulting to **(a)** unless you want to test diversification."

### Anticipate my pushback. Address the obvious counter before I ask.

> ✅ "April INP regressed 98ms → 142ms on /capabilities/cnc-machining post-deploy.
> **Ruled out:** third-party tag bloat (no new tags shipped), CDN regression (other pages held steady), traffic-mix shift (mobile share unchanged at 58%), seasonality (April is historically the strongest CNC-search month, so the lift is structural not cyclical).
> **Most likely cause:** hero-section animation added in the April 2 deploy — preliminary Lighthouse run shows ~40ms TBT contribution from the animation script."

### Frame recommendations in B2B terms I work in.

- Pipeline impact, not "leads."
- Closed-won lag (90 days from click), not click-date conversion.
- ICP fit, not "high-quality lead."
- Branded vs. non-branded share-of-search, not just rankings.
- Marketing-sourced vs. marketing-influenced revenue.

### Cite sources inline. Always.

> "Source: GA4 export `supporting/ga4-export-2026-04.csv`, rows 142–158. Cross-validated against GSC `supporting/gsc-queries-2026-04.csv` for the organic attribution claim."

### Show your work on attribution. Name the model.

> ✅ "5-Axis CNC Launch — 8 closed-won deals in April under **last-click, 90-day click-to-close window**. **Linear multi-touch** attributes 11.4 deals to the campaign over the same window, suggesting the campaign is also functioning as an effective assist channel — not just a direct driver. The delta (3.4 deals) is consistent with our hypothesis that the 5-axis content is being consumed mid-funnel before a branded conversion."

---

## What I want in every report

1. **The number, the change, the why, the action, the confidence level.** In that order.
2. **At least one counterfactual** — what would have happened without the intervention.
3. **A "watch this next month" callout** — the leading indicator I should track in the next reporting cycle.
4. **An honest limitation** — what we *don't* know yet, and how we'd find out.
5. **Linkage to the supporting CSVs** — I'll go to the source data when something is interesting.

---

## Worked example — how the same finding should be presented to me

**Question I asked:** "What happened to the website in April?"

### ✅ Good answer for me

| Headline | Sessions **14,082** (+18.4% MoM, +31.2% YoY); RFQs flat at **78**; CVR softened **0.66% → 0.55%** (-11 bps). |
|---|---|
| **Driver of traffic lift** | Organic to `/capabilities/cnc-machining` — 5-axis launch pages now indexing and ranking page-1 for **11 long-tail queries** (see [`seo/2026-04-seo.md`](../seo/2026-04-seo.md)). Validates the launch-content thesis from the December plan. |
| **Concern** | CVR dip is concentrated on the same page driving the traffic gain. Page-level bounce up **9 pts** post-deploy, INP regressed **98ms → 142ms** on `/capabilities/cnc-machining`. |
| **Cause (preliminary)** | April 2 deploy added a hero-section animation contributing **~40ms TBT** per Lighthouse. Ruled out tag bloat, CDN regression, mobile-share shift, seasonality. |
| **Counterfactual** | Holding INP at March level via the page-level CVR model implies **~13–15 incremental RFQs** in April. At our 25% RFQ → closed-won rate and ~$32K AOV, that's **~$110K–$130K of marketing-sourced pipeline left on the table**. |
| **Recommend** | Roll back the hero animation or replace with a CSS-only variant in the **May 12 deploy window**. <br>**Confidence: high.** Reproducible in lab + RUM data. |
| **Watch next month** | (1) INP 75th-percentile recovery on the CNC page within 7 days of fix. (2) CVR rebound on the same page back toward 1.4% baseline. (3) Lag-effect on 5-axis CNC closed-won — **April-click cohort matures end of June**, that's the real read on whether the traffic was high-intent. |
| **Limitation** | We can't yet fully separate "regression-driven CVR drop" from "lower-intent traffic mix from new ranking queries entering the funnel." Need 2 more weeks of post-fix data and a query-level intent classifier (see notes in [`seo/2026-04-seo.md`](../seo/2026-04-seo.md)) to isolate cleanly. |

---

## What I do NOT want

- Padding. If a sentence doesn't add information, cut it.
- Recommendations without a confidence level.
- "Vanity" framing. Don't celebrate a session lift that didn't move pipeline.
- Acronym definitions. I know them.
- Hedging language. "Might possibly perhaps" tells me you don't know — say so directly and tell me how to find out.
- Single-source claims when a cross-check is cheap. If you tell me organic drove the lift, I want GSC and GA4 cross-validated.
