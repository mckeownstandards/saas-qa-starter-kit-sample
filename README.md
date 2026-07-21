# SaaS QA Starter Kit — Free Sample

Two ready-to-use QA documents for engineering-led SaaS teams: a **bug report template** and the **defect lifecycle workflow** that goes with it. Both in plain Markdown — drop them into GitHub, Linear, Jira, or Notion and use them today.

This is a free sample from the full [SaaS QA Starter Kit](https://mckeownstandards.gumroad.com/l/qa-starter-kit). These two documents are complete and usable on their own — no sign-up, no email wall. Fork the repo, take what's useful, ignore the rest.

---

## Who this is for

Early-stage, engineering-led SaaS teams — roughly 10–60 people. Big enough that quality is starting to slip, too small to have hired a dedicated QA person yet. If you're a founder or head of engineering who can feel bugs getting away from you but isn't ready to hire QA, this is built for you.

It's the rigour of regulated, medical-device-grade QA, stripped down to exactly what a fast-moving SaaS team needs — none of the compliance overhead.

---

## What's in this sample

### `bug-report-template.md`
A structured bug report format that works whether you track issues in Linear, Jira, GitHub Issues, or Notion. It covers the fields that actually get a bug fixed — environment, user context, reproduction steps, severity, priority, evidence — with guidance on each, plus a fully worked example based on a real-feeling SaaS bug.

The template takes a clear stance on the thing most teams get wrong: **severity describes impact, priority describes urgency.** They're different fields, and conflating them is why bug triage turns into an argument.

### `defect-lifecycle-workflow.md`
How a bug moves from "someone noticed something's wrong" to "the fix is shipped and verified" — the stages, the branching states (cannot reproduce, duplicate, reopened), sensible SLA guidelines by severity, and the anti-patterns that quietly break teams (developers closing their own bugs, everything marked "critical," bugs sitting in triage for a week).

Together, these two documents are a complete bug-handling workflow. Adopt them as-is, or adapt them to how your team already works.

---

## How to use it

1. Clone or download the repo, or just copy the Markdown straight out of the two files.
2. Drop the bug report template wherever you file bugs. In GitHub, it works as an issue template (`.github/ISSUE_TEMPLATE/bug.md`).
3. Read the defect lifecycle once as a team, and agree on your severity and priority definitions.
4. Adjust anything that doesn't fit — the structure is a starting point, not a straitjacket.

---

## The full kit

If these two documents are useful, the complete **SaaS QA Starter Kit** contains nine documents covering the whole QA workflow a startup needs from day one:

- A **128-case test case library** — real SaaS scenarios (auth, billing, permissions, API, webhooks, and more), written in single-arc Gherkin
- **Test case** and **test report** templates
- The full **bug report template** (included here) with its worked example
- The **defect lifecycle workflow** (included here)
- A **test plan template** with a complete worked example
- A **README** that ties it all together

It's the same philosophy as this sample, extended across every part of the process — so a team with no QA function can have a real testing process in an afternoon.

👉 **Get the full kit:** [SaaS QA Starter Kit](https://mckeownstandards.gumroad.com/l/qa-starter-kit)

---

## Feedback welcome

Found these useful? Spotted something that could be better? Open an issue or get in touch — this kit improves through real teams using it.

Built by Niall McKeown — verification engineer, four years in regulated medical-device QA.
