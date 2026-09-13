# 17 - BankBreezy and Giggle Link Routing Reference

## BankBreezy and Giggle Link Routing Reference  
### Moonshine Capital HubSpot CRM Operations Source Document

---

## 1. Purpose

This document defines how to handle BankBreezy and Giggle routing inside Moonshine Capital’s HubSpot, Gmail, and follow-up workflows.

Use this guide when deciding:

- Which funding link/context to send
- When BankBreezy dashboard language is appropriate
- When Giggle routing should be recommended
- How to log link-sent status
- How to create follow-up tasks after sending a link
- How to avoid approval/funding guarantee language
- How to preserve routing context in HubSpot

The goal is to move applicants into the right review path without overpromising or losing context.

---

## 2. Core Routing Rule

BankBreezy and Giggle routing should be treated as **review paths**, not approval decisions.

Acceptable:

```text
Based on what you shared, this appears worth reviewing through the BankBreezy dashboard.
```

Not acceptable:

```text
You qualify for same-day funding.
```

Do not guarantee:

- Approval
- Specific funding amount
- Specific terms
- Same-day funding
- Next-day funding
- Underwriting outcome

---

## 3. Known BankBreezy Dashboard Link

Default BankBreezy dashboard link when provided/approved:

```text
https://bankbreezy.com/funding/jason
```

Use only when the applicant should be routed to Jason’s BankBreezy dashboard.

Do not invent alternate links.

If a different link is provided for a specific partner/broker/campaign, use that exact link and preserve it in the note.

---

## 4. BankBreezy Routing Signals

BankBreezy may be appropriate when:

- Applicant has a business bank account
- Applicant has established business revenue
- Applicant requested larger business funding
- Applicant wants same-day business funding review
- Applicant is delayed with another provider
- Applicant needs a faster alternative lane
- Applicant has enough business activity to justify review
- Applicant is looking for working capital, expansion, equipment, or business funding

Use BankBreezy language when the goal is to get the applicant into a business funding dashboard/review path. BankBreezy alerts must be translated into the exact missing applicant action (connect bank, submit named statements, etc.) per `42 - Applicant Outreach Sequence and State Machine.md`.

---

## 5. Giggle Routing Signals

Giggle may be appropriate when:

- Applicant uses a personal bank account
- Applicant has $3k+ monthly revenue/activity
- Applicant has 4+ months activity
- Applicant is self-employed, gig worker, contractor, or sole operator
- Applicant is not a clean fit for business-bank-account funding
- Applicant needs smaller/fast funding review
- BankBreezy path appears less suitable because of banking setup

Use Giggle language when the applicant’s profile appears better suited for micro/same-day style review based on activity and account setup.

---

## 6. Parallel Lane Routing Signals

Use a parallel lane when:

- Applicant requested a larger amount
- Applicant is stuck with another provider
- BankBreezy could review larger opportunity
- Giggle could be useful as a fast first step
- Applicant may need staged funding
- Applicant has urgent timing but incomplete fit for one lane

Parallel lane note language:

```markdown
Applicant may benefit from a parallel funding review approach. Giggle-style review may be useful for fast/smaller funding based on bank/revenue profile, while BankBreezy/business funding may remain relevant for larger funding review. No approval, amount, terms, or timeline guaranteed.
```

---

## 7. Route-Event Logging Rules

Log the verified route event—not a generic “link sent.” Giggle and BankBreezy must remain distinct.

### BankBreezy dashboard route

Record:

- Exact approved dashboard link sent
- Date and sender
- Routing reason
- Applicant state and route-specific follow-up task

### Giggle route

Record:

- Giggle route active / applicant advanced, when verified
- Giggle email expected, located, or missing
- Plaid/bank connection state
- Any specifically requested statement or document and its verified submission path
- Route-specific follow-up task

Do not record or invent a Moonshine/DAC/Giggle URL when Giggle’s own email owns the applicant action.

Recommended note:

```markdown
## Provider Route Event Note

Applicant: [Name]  
Provider route: [BankBreezy dashboard / Giggle / Other]  
Route event: [BankBreezy dashboard link sent / Giggle email expected / Plaid incomplete / named documents requested]  
Date: [Date]  
Handled by: [Jason / Moonshine Capital / Other]

Routing reason:
[Explain why this path was recommended.]

Verified next action:
[Exact provider-owned action and follow-up timing.]

No-guarantee note:
Route is for review/application purposes only. No approval, funding amount, terms, or timeline guaranteed.
```

---

## 8. BankBreezy Email Language

Use this for applicants who should start with the BankBreezy dashboard.

```text
Given what you’re looking for and the timing, I’d suggest starting with the BankBreezy dashboard to see what may be available. It gives you a faster way to get your information reviewed instead of waiting around on a slower process.

You can start here:

https://bankbreezy.com/funding/jason

No approval, amount, terms, or timeline is guaranteed, but this gets the review moving.
```

---

## 9. Giggle Link Ownership & Email Language

### 9.1 Non-Negotiable Link Ownership Rule
- **Giggle Link Ownership:** Giggle owns the applicant-facing email/link for its application and Plaid bank-connection flow. DAC/Moonshine applicant outreach must direct the applicant to locate their existing Giggle email.
- **Do Not Invent Links:** Never invent a separate Moonshine, DAC, or generic application link for the Giggle path.
- **Plaid Connection Mechanism:** In the Giggle route, Plaid connects and verifies the applicant’s primary operating account and supplies the account data used for review. If the provider requests named statements or documents, state that exact request and use its verified path; do not replace it with generic instructions.

### 9.2 Giggle Outreach Copy (Jason Voice)
```text
Hi [First Name],

You are already in the Giggle queue. The next move is simple: open the email Giggle sent you, and connect your primary operating account through Plaid.

That gives underwriting what it needs to evaluate the lane. Leaving it half-finished is letting an administrative bottleneck hold up your momentum.

Handle that step today, then reply "done" here. If the Giggle email got swallowed by your spam folder, reply "resend" and we will get you pointed back to the right place.

Jason
```

---

## 10. Provider Delay Language

Use when applicant is stuck with another provider/platform.

```text
Since you’re already running into delays with your current application, I’d recommend opening a backup review lane now. That does not mean abandoning the other option. It just means we stop letting one slow process control the whole board.
```

Add:

```text
No approval or specific funding timeline is guaranteed.
```

---

## 11. Task Rules After Link Sent

Create task immediately after sending/recommending a link.

| Link/Event | Task |
|---|---|
| BankBreezy dashboard sent | `Follow up — [Name] — confirm BankBreezy quote started` |
| Giggle route active / provider email expected | `Follow up — [Name] — confirm Giggle email located` |
| Giggle email missing | `Follow up — [Name] — confirm Giggle resend/escalation` |
| BankBreezy dashboard link fails | `Follow up — [Name] — verify BankBreezy dashboard action path` |
| Giggle applicant starts application | `Check status — [Name] — confirm Plaid/bank connection` |
| No response after link | `48-hour follow-up — [Name] — no response after funding link` |
| Larger request with fast need | `Follow up — [Name] — review parallel business funding options` |

Default due timing:

- Next business day after link sent
- Same day if applicant is urgent and active
- 48 hours for no-response follow-up

---

## 12. HubSpot Deal Stage Guidance

If a deal exists:

| Routing Event | Suggested Stage |
|---|---|
| BankBreezy link sent | Contract Sent |
| Giggle route active / provider email expected | Contract Sent or the closest existing live stage + precise state note |
| Applicant appears eligible but no link sent | Qualified To Buy |
| Applicant started application | Decision Maker Bought-In |
| Bank link pending | Contract Sent or Decision Maker Bought-In + note |
| Underwriting pending | Decision Maker Bought-In |
| Funded | Closed Won |
| Declined/withdrawn | Closed Lost |

Always preserve the exact routing status in a note because current deal stages are generic.

---

## 13. Required Routing Details to Preserve

Always preserve:

- Funding requested
- Funding purpose
- Bank account type
- Monthly revenue
- Lowest monthly revenue
- Time in business
- Link sent
- Whether BankBreezy dashboard was sent
- Whether Giggle was recommended
- Whether applicant was advanced to Giggle Finance
- Whether bank account was linked
- Whether application was started
- Next follow-up task
- No-guarantee compliance note

---

## 14. Routing Decision Table

| Applicant Profile | Likely Routing | CRM Action |
|---|---|---|
| Personal bank + $3k+ monthly revenue | Giggle-style review | Note + Giggle follow-up task |
| Business bank + strong revenue | BankBreezy/business funding | Note + BankBreezy link/task |
| Larger request + provider delay | BankBreezy backup lane | Email + note + task |
| Personal bank + larger request | Parallel lane | Note both paths carefully |
| Missing bank/revenue details | Needs more info | Task/email for missing info |
| No clear funding request | Contact/note only | Do not create deal unless intent clear |

---

## 15. What Not To Do

Do not:

- Send a link without logging it
- Send unapproved/invented links
- Guarantee same-day funding
- Say applicant qualifies
- Treat link sent as approval
- Forget the follow-up task
- Use BankBreezy and Giggle interchangeably without context
- Create company if no real entity exists
- Create duplicate deals for each link/follow-up
- Bury bank account type in email only

---

## 16. Operational Standard

Every BankBreezy/Giggle routed applicant should make clear:

- Why this path was recommended
- Which link was sent
- When it was sent
- What applicant needs to do next
- What Moonshine Capital must follow up on
- What is not guaranteed

Routing should create motion, not confusion.
