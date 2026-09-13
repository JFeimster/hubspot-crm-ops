# 42 - Applicant Outreach Sequence and State Machine

## Purpose

This document replaces the undead three-follow-up routine with a state-based operating system. Every applicant has a current state, a real trigger, a next action, a cadence, and an exit condition.

The state machine governs funding applicants and adapts to Giggle/BankBreezy routing. It does not override actual provider requirements, applicant instructions, or verified process status.

## Governing Rules

- Research the applicant before selecting the initial outreach angle.
- Record the actual state; do not infer a bank connection, link open, approval, or document submission without evidence.
- One active primary sequence at a time.
- Every task must be associated with the applicable contact and deal; associate a company when the relationship is confirmed.
- Stop or change the sequence immediately when the applicant responds, completes the action, opts out, is declined, or becomes ineligible for the current lane.
- Do not send a generic follow-up when the state calls for a targeted recovery action.

## State Model

```text
New Intake → Research Complete → Intent Selected → Active Outreach
                                              ↓
                           Giggle / BankBreezy Route (when applicable)
                                              ↓
           Email Missing | Started | Plaid Incomplete | Docs Missing | Submitted
                                              ↓
                         Provider Review / Outcome / Reactivation
```

## Core States and Actions

| State | Evidence/trigger | Immediate action | Default follow-up | Exit condition |
| --- | --- | --- | --- | --- |
| New intake | Form, email, referral, or call received | Search CRM/context; run public intelligence research | Same business day | Research complete |
| Research complete | Identity/business/context collected | Propose CRM changes; select intent and route | Same business day | Contact plan approved or executed |
| Initial outreach sent | Personalized first message delivered | Create next-day task; watch for reply | Next business day | Reply, action completed, or no response |
| No response — early | No reply after initial message | Send a different-angle follow-up, not a copy of message one | 48–72 hours later | Reply, opt-out, or escalation decision |
| No response — final active | No reply after meaningful attempts | Send a clean close-the-loop message | 5–7 days later | Reactivation, closed-lost, or future nurture |
| Giggle email expected | Applicant routed to Giggle | Tell applicant to locate the existing Giggle email; state what it enables | Next day if no confirmation | Applicant confirms receipt/action |
| Giggle email missing | Applicant says they did not receive it | Confirm email address and trigger the fastest appropriate resend/escalation path | Same day | Email resent/located or alternate route chosen |
| Application started | Applicant confirms entry into provider flow | Identify the exact remaining step | Within 24 hours | Plaid complete, docs requested, or submitted |
| Plaid/bank link incomplete | Provider status or applicant confirms no bank connection | Ask applicant to return to Giggle email and connect the primary operating account through Plaid | Next day; then 48 hours | Bank linked or applicant declines/cannot complete |
| Documents missing | Provider identifies missing statements/documents | Name the exact document and upload/reply path | Next day; then 48 hours | Documents submitted or alternate lane selected |
| Submitted/provider review | Application and required steps completed | Set expectation; avoid needless nudging | Check at provider SLA or 2 business days | Provider outcome/update |
| Provider requested more | Provider or BankBreezy requests a specific item | Convert request into one clear applicant action | Same day + next business day | Requested item provided |
| Provider declined/not advanced | Verified decline or non-advance | Determine alternative lane; communicate the practical next choice | Same business day | Alternate lane, pause, or closed-lost |
| Applicant says “not now” | Explicit timing objection | Record timing/reason; send respectful acknowledgment | Reactivate at agreed date; otherwise 30–90 days | New response or close |
| Reactivation | Prior applicant has a relevant reason to revisit | Research for current context; send a fresh, specific message | One follow-up after 3–5 days | Reply, new route, or archive |

## Cadence by Channel

Use the channel the applicant has actually engaged with. Do not turn every missed email into a five-channel siege.

| Moment | Email | Text/call | Task |
| --- | --- | --- | --- |
| Day 0 | Personalized initial message | Optional when mobile consent/context supports it | Create state task and owner |
| Day 1 | Targeted action reminder for provider/document states | Short text or call for time-sensitive, engaged applicants | Confirm status and response |
| Day 3 | New angle, clearer consequence, or obstacle removal | Optional second touch | Decide active vs. pause |
| Day 5–7 | Close-the-loop / choice message | Call only when value and relationship justify it | Move to reactivation or close |
| 30–90 days | Fresh research-backed reactivation | Optional | Create only if a real trigger exists |

## Giggle and BankBreezy Operating Details

- Giggle owns the applicant-facing email/link for its application and Plaid bank-connection step.
- Moonshine/DAC outreach should direct the applicant back to that existing Giggle email unless the provider or operational owner supplies a different route.
- Plaid is the bank-connection and verification mechanism; do not describe it as an unrelated document-upload alternative.
- BankBreezy alerts should be translated into the exact applicant action required: connect bank, submit named statements, provide a requested item, or confirm a missing-email problem.
- If the alert does not name the required action, do not improvise. Clarify internally or with the provider before telling the applicant what to do.

## Message Choice by State

| State | Message job | Primary CTA |
| --- | --- | --- |
| New/qualification | Turn incomplete intake into a useful conversation | Reply with the few facts that determine the lane |
| Giggle email expected | Get the applicant into the provider flow | Find/open the Giggle email |
| Plaid incomplete | Remove the bottleneck | Connect the primary operating account through Plaid |
| Documents missing | Make the request concrete | Submit the named document(s) |
| Provider review | Maintain confidence without noise | Confirm a requested change only if one exists |
| Declined/not advanced | Preserve momentum and reposition | Reply with the alternative-lane decision/input |
| No response | Give a simple choice | `ready`, `not now`, or a requested single reply |
| Reactivation | Reopen with fresh relevance | Confirm whether the current need still exists |

## Task Template Requirements

Every sequence task must include:

- A clear verb-led title: `Confirm Plaid connection — [Applicant]`
- Due date and time appropriate to the state
- Current state and evidence
- Exact next move
- Copy/paste message angle or provider instruction when useful
- Contact/deal/company associations
- Stop condition

Example:

```markdown
Title: Confirm Giggle Plaid completion — Marcus Bates
Due: Next business day, 10:00 AM local time
State: Plaid/bank link incomplete
Evidence: BankBreezy stall alert; Giggle route active
Next move: Confirm whether Marcus found the Giggle email and connected the primary operating account through Plaid.
Stop when: Applicant confirms completion, provider confirms link, applicant asks for help, or route changes.
Associations: Contact + active funding deal + Illinois United company only if confirmed.
```

## Close, Pause, and Reactivation Rules

Close or pause with clarity. Do not leave people buried in active tasks because nobody wanted to make a decision.

- **Closed—completed:** required action finished; move to provider review/outcome state.
- **Paused—timing:** applicant names a future timing window; create one dated reactivation task.
- **Closed—no response:** active cadence exhausted; retain notes and set no automatic new sequence unless a trigger appears.
- **Closed—provider outcome:** record verified result and the next applicable lane, if any.
- **Reactivation:** require a new reason: changed business context, new offer, applicant signal, seasonal need, or prior agreed timing.

