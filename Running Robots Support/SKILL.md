---
name: rr-customer-support
description: >
  Use this skill whenever a Running Robots client needs help with their website, has a question about how something on their site works, wants to report an issue, or needs to engage support in any way. Covers how to reach support (email support@therunningrobots.com), the self-service knowledge base, how to use this repo's `website/` folder to investigate site behavior before escalating, the team (Larissa, Alex, Tif), reply patterns (pending / resolved / escalation), what to include when reporting an issue, what to expect on response time and follow-up, and how escalations flow. Trigger on terms like "support ticket," "Zoho Desk," "site issue," "site is down," "how do I," "the form isn't working," "page is broken," "client support," "escalate," "Larissa," "Alex," "Tif," or any request that involves opening, following up on, or asking about a support request to Running Robots — and on any question about using or troubleshooting the client's website.
---

# Running Robots Customer Support

This skill describes how Running Robots support works and how to engage it cleanly. It is modeled on the live workflow of Running Robots' Support Specialist — the same team, tools, templates, and cadences used with real clients.

---

## How to reach us

**Email:** [`support@therunningrobots.com`](mailto:support@therunningrobots.com) — this is the single front door. Every email creates or updates a Zoho Desk ticket and routes to Larissa for triage.

**Self-service knowledge base:** [support.therunningrobots.com/portal/en/kb/website-articles](https://support.therunningrobots.com/portal/en/kb/website-articles) — searchable articles on common website questions (forms, plugins, hosting, edits). Worth a quick look first; if the answer isn't there, email us.

**This repo's `website/` folder** — for clients reading this in their own demo or live repo: the [`website/`](../website/) folder contains your monthly site performance reports, page-level performance detail, Screaming Frog crawls, and incident write-ups. Before asking "is this normal?" or "did something change on my site?" — point your AI assistant at the most recent `website/YYYY-MM-website.md` file. It will often answer the question directly using your own site's data (Core Web Vitals, deploy history, page-level conversion rate, traffic by channel). If you still need a human or a fix, email support.

---

## The team

| Role | Person | Owns |
|---|---|---|
| Support Specialist | **Larissa Simbro** | Client communication on every ticket. First responder. Owns the relationship in the inbox. |
| Technical Fix | **Alex** | The actual work — code, configuration, debugging, integrations, hosting. Larissa hands tickets to Alex when work is needed; Alex hands them back when the work is done. |
| Escalations & Relationship | **Tif** | Billing, scope, contract questions, and anything beyond a standard support reply. Looped in whenever a ticket needs more than a fix. |

**Where to send things:** `support@therunningrobots.com`
**Where tickets live:** Zoho Desk

---

## How a ticket flows

1. **Intake.** Client emails `support@therunningrobots.com` or replies on an existing thread. A Zoho Desk ticket is created automatically.
2. **Triage.** Larissa reviews and routes — fix it directly, hand off to Alex for technical work, or escalate to Tif if it's a relationship-level issue.
3. **Acknowledgment.** Client gets a reply confirming we've seen it, what's happening next, and when to expect a follow-up. (See `Templates/Pending Ticket.md`.)
4. **Fix.** The work happens — usually Alex, sometimes Larissa for non-technical items. Larissa stays as the client-facing point of contact throughout.
5. **Resolution.** Larissa replies with a plain-English summary of what was done and what it means for the client's day-to-day. Ticket is closed. (See `Templates/Resolved Ticket.md`.)
6. **Escalation (when needed).** If the ticket grows beyond a support reply, Tif is looped in and reaches out directly. (See `Templates/Escalation Notice.md`.)

---

## What to include when reporting an issue

To help us help you quickly:

- **What you're seeing** — what's broken, missing, or different than expected
- **Where** — the page URL, the form, the order number, the email subject line
- **When it started** — was this happening before today? After a specific event (a deploy, a plugin update, a new product launch)?
- **Who else has noticed** — only you, multiple customers, internal staff
- **Screenshots if helpful** — but never required

No need for technical diagnosis. Plain English is best — translating tech is our job.

---

## What you can expect from us

- **Acknowledgment** — same business day for incoming tickets during standard hours.
- **No jargon.** We translate everything to plain business English. We explain what happened and what it means for you, not the technical mechanics.
- **A clear next step at the end of every reply.** You should never finish reading wondering what happens next.
- **Status over silence.** If a fix takes longer than a day, we'll send a status update before you have to ask.
- **Honesty about uncertainty.** If we don't know yet, we'll say so directly and tell you how we'll find out — not guess.
- **Drafts before sends.** Internally, every client-facing reply is drafted, reviewed, and approved before it goes out. You're not seeing first thoughts.

---

## Our reply patterns

We standardize on three reply patterns so communication is predictable.

### Pending — when work is in progress
Acknowledge the issue, reassure that the team is on it, set a timeframe (or commit to a follow-up). Tone: calm, reassuring. Never speculates on cause.
→ [`Templates/Pending Ticket.md`](./Templates/Pending%20Ticket.md)

### Resolved — when the fix is done
Skip the acknowledgment — lead with what was done and what it means for the client. Invite follow-up. Tone: warm, matter-of-fact.
→ [`Templates/Resolved Ticket.md`](./Templates/Resolved%20Ticket.md)

### Escalation — when Tif needs to be looped in
Confirm we've looked into it. Reassure that it's being escalated to the right person, not dismissed. Avoid blame language (ours or yours).
→ [`Templates/Escalation Notice.md`](./Templates/Escalation%20Notice.md)

---

## When we escalate to Tif automatically

- Conversation is about billing, scope, or contract
- Relationship is at risk — frustration, a repeat issue, a missed expectation
- Decision is beyond a standard support reply (e.g., "should we change hosts?", "do we still need this plugin?")
- Client specifically asks to talk to her

You can also request Tif directly any time.

---

## How we handle noise

Automated alerts (vendor newsletters, security scans, backup confirmations, hosting status pings) are auto-routed and closed without bothering you unless they represent a real issue requiring action. If you got a "your ticket has been received" auto-reply, that's just the system — no action needed from you.

---

## Hours and response windows

- **Standard hours:** Monday–Friday, 8a–5p Central
- **Intake response:** same business day during standard hours
- **In-flight tickets:** same-day or next-business-day follow-up
- **Urgent / site-down:** put `URGENT` or `SITE DOWN` in the subject line — Tif gets looped in immediately, and we'll start triage outside standard hours if needed

---

## Working rules we hold ourselves to

These are the rules our support specialist operates under internally. Surfacing them so you know what to expect.

- **Draft first, refine after.** Every client reply starts as a draft, gets refined, and gets approved before sending. No first-thoughts going to clients.
- **Confirm before sending.** Nothing is posted, sent, or submitted on a client's behalf without explicit approval from the relationship owner.
- **Flag escalations proactively.** If a ticket warrants more than a reply, the support specialist flags it for Tif — they don't wait to be asked.
- **No jargon in client replies.** Technical detail stays in our internal notes. Client-facing communication is translated to plain business English.
- **Match the client's tone.** Default is warm and non-technical. We calibrate from your prior communication style.
- **Never guess.** If the answer isn't known or can't be verified, we say so directly. We do not fill gaps with assumptions presented as fact.

---

## When to use this skill

Paste this skill into your AI assistant (Claude, ChatGPT, Gemini) when you want help:

- **Answering "is this normal?"** for something on your website — the AI should check the most recent `website/YYYY-MM-website.md` report for context (traffic trends, Core Web Vitals, deploy notes, page-level performance) before guessing.
- **Answering "how do I…" questions** about your website — the AI should suggest the [knowledge base](https://support.therunningrobots.com/portal/en/kb/website-articles) first; if the answer isn't there, draft a support email to `support@therunningrobots.com`.
- **Drafting a clear support request** to send to Running Robots — the AI will use the "What to include when reporting an issue" checklist above.
- **Understanding what stage a ticket is in** based on the reply you received (pending / resolved / escalation).
- **Figuring out whether something is normal noise or worth flagging.**
- **Knowing when to ask for Tif specifically.**
- **Setting realistic expectations on response time.**

The AI will use the structure, team roles, templates, and your `website/` data to give you support-aware guidance — and will direct you to email `support@therunningrobots.com` whenever a human needs to be in the loop.

---

*This is a public demo artifact in the Running Robots Client Demo Repo. The workflow described here mirrors the actual support setup we use with clients. Specific ticket numbers, client names, and internal queue contents have been omitted.*
