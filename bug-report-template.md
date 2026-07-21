# Bug Report Template

A structured format for logging bugs that a developer can actually act on. Paste the template below into Jira, Linear, GitHub Issues, Notion, or whatever your team uses — the structure travels.

The goal of this template is simple: **a developer should be able to reproduce the bug without asking the reporter a single follow-up question.** If your bug report doesn't clear that bar, it's not finished.

> A bug report is a handoff, not a vent. The person reading it has less context than you. Write for them.

---

## The template

Copy everything between the lines below into your tracker.

---

### Title
> One line, action + observed behaviour. "Workspace switcher returns 403 when switching from Pro to Free workspace" — not "Workspace switcher broken." Skip the word "bug" — the tracker already knows.

### Description

A short summary of what's actually happening. Don't pack in every detail — the fields below capture the specifics.

### Tracker metadata

Bug ID, reporter, and date reported are captured automatically by your bug tracker — Linear, Jira, GitHub Issues, Notion, or whatever you use. Don't duplicate them in the report body. If you're filing this somewhere without auto-population (a plain doc, a PDF for an external party), add them at the top manually.

### Environment

| Field | Value |
|---|---|
| Environment | `production` / `staging` / `pre-production` / `local` |
| App version / commit SHA | e.g. `v2.14.3` or `a1b2c3d` |
| Browser + version | e.g. `Chrome 124.0.6367.78` |
| OS | e.g. `macOS 14.4.1`, `Windows 11 23H2` |
| Device | e.g. `MacBook Pro M2`, `iPhone 15 Pro`, `Pixel 8` |
| Region / locale | e.g. `eu-west-1`, `en-GB` (only if relevant) |

> Commit SHA beats "version number" every time. Versions lie, SHAs don't. If your team ships continuously, `v2.14.3` could mean six different builds.

### Severity
`Critical` / `High` / `Medium` / `Low` — see definitions below.

### Priority
`P0` / `P1` / `P2` / `P3` — see definitions below.

### Steps to reproduce
Numbered, atomic, runnable by a stranger.

1. ...
2. ...
3. ...

> Steps to reproduce should be runnable by someone who has never seen the bug, on a fresh account, in a fresh browser. If your steps require tribal knowledge ("then do the thing we always do"), you haven't finished writing them.

### Expected result
What should have happened, in one or two sentences.

### Actual result
What actually happened. Be precise — "didn't work" is not a bug report. Include the exact error message, status code, or visible state.

### Reproduction rate
- `Always` — happens every time
- `Often` — happens most of the time (>50%)
- `Intermittent` — happens sometimes, no clear pattern
- `Once` — observed once, couldn't reproduce

> If you tick "Once," spend ten more minutes trying to reproduce before filing. Half of "once" bugs are reproducible with one more variable identified. The other half are race conditions worth flagging anyway — just say so.

### Evidence
Attach or link:

- Screenshots **with annotations** (circles, arrows, highlights)
- Screen recordings for interaction bugs (Loom, CleanShot, native screen capture)
- Log snippets — server logs, browser console, network tab
- Network traces — request method, URL, status code, response body, request ID
- Webhook event IDs, async job IDs, background task IDs
- Error tracking links (Sentry, Datadog, Rollbar)
- Relevant timestamps for log correlation

> Screenshots without annotations are 50% as useful. Circle the thing. Add an arrow. Two seconds in CleanShot or Skitch saves your developer five minutes of "wait, where am I supposed to be looking?"

### Workaround
If users can avoid the bug, describe how. If there's no workaround, write "None" — don't leave the field blank. "None" is a load-bearing signal for triage.

### Related bugs / linked tickets
- Similar or duplicate bugs: `#1823`, `#1791`
- Related PRs: `#4521`
- Related test cases or test runs
- Customer support tickets: `ZD-9821`
- Sentry issue: `https://...`

### Suggested area / component
Your best guess at the surface or service: `auth`, `billing`, `webhooks`, `workspace-switcher`, `api-gateway`, `frontend/settings`, etc. Don't agonise — triage will adjust. But a starting point speeds routing.

---

## Severity vs. priority — they are not the same thing

This is the single most-misused part of bug tracking. Read this twice.

- **Severity** describes **impact** — how bad is it when it happens?
- **Priority** describes **urgency** — how soon do we need to fix it?

> Don't use Severity and Priority interchangeably. Severity = impact. Priority = urgency. A Critical-severity bug affecting one user on Free tier might be P2. A Low-severity typo on the pricing page might be P0 if it's costing you signups.

### Severity definitions

| Level | Definition | Examples |
|---|---|---|
| **Critical** | Data loss, security breach, total outage, payment failures, auth completely broken. No workaround possible. | Users can't log in. Stripe webhooks failing silently. PII leaked across workspaces. Database writes silently dropped. |
| **High** | Major feature broken or significantly degraded. Workaround exists but is painful or non-obvious. | Search returns no results for half of queries. Export to CSV produces malformed files. Email notifications delayed by hours. |
| **Medium** | Feature partially broken. Reasonable workaround exists. | A filter ignores one of its inputs. Sort order resets on page refresh. Modal closes when it shouldn't. |
| **Low** | Cosmetic, edge case, or minor inconvenience. | Misaligned button on a settings page. Tooltip text truncates at 320px. Plural label says "1 items." |

### Priority definitions

| Level | Definition | When to use |
|---|---|---|
| **P0** | Drop everything. Fix now. | Production is on fire. Money is being lost. Trust is being damaged in real time. |
| **P1** | Fix in this sprint. | High-severity issue with workaround, or anything blocking a key release. |
| **P2** | Fix in the next 1–2 sprints. | Medium-impact issue. Schedule it, don't drop it. |
| **P3** | Backlog. Fix when convenient or batch with adjacent work. | Cosmetic, edge case, or low-value-to-fix. |

> "Severity inflation" is a real disease. If everything is High, nothing is. A team where 80% of bugs are filed as High has a culture problem, not a severity problem. Audit your last 50 tickets — if more than half are High or Critical, recalibrate.

---