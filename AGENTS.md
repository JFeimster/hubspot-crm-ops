# AGENTS.md — HubSpot CRM Ops Source Library

## Repository purpose

This repository is the canonical Markdown source library for Moonshine Capital’s HubSpot CRM Ops knowledge base.

It contains:

- Existing source documents `01–39`
- Applicant intelligence, voice, sequence, prompt, and example modules `40–44`

This repository is documentation and operating-system source material. It does not contain application code, credentials, deployment configuration, or live CRM data.

## Editing rules

- Preserve existing source-file paths, filenames, and numbering.
- Do not rename, renumber, delete, merge, or split source documents unless Jason explicitly requests it.
- Do not create alternate source-of-truth files, overlay directives, duplicate playbooks, or replacement systems.
- Update documents in place and preserve useful existing material.
- Keep Markdown clear, operational, and copy/paste ready.
- Fix affected cross-references whenever a source document changes.
- Do not create external records or modify Google Drive, HubSpot, Gmail, Notion, Wix, n8n, or GitHub settings unless explicitly authorized.

## Operating standards to preserve

- Search before CRM creation or update.
- Prevent duplicates.
- Use structured HubSpot fields only when there is a clean schema match.
- Keep nuanced context, research, routing logic, and inference in notes.
- Create companies only for real, relevant, supportable entities.
- Do not invent applicant facts, funding amounts, provider outcomes, approvals, terms, or pipeline stages.
- Preserve HubSpot Free custom-property constraints.
- Distinguish applicant-provided facts, existing CRM data, public research, clues, and inference.

## Current governing modules

Treat these files as the detailed authority for their domains:

- `40 - Applicant Public Intelligence and Web Research SOP.md`
- `41 - Jason Voice and Applicant Outreach Style Guide.md`
- `42 - Applicant Outreach Sequence and State Machine.md`
- `43 - Google CC-Style Applicant Review and Outreach Prompt.md`
- `44 - Gold-Standard Applicant Outreach Examples.md`

When older files conflict with these modules, revise the older files to align. Do not weaken the research-first workflow or dilute Jason’s voice into generic lender copy.

## Live-skill alignment

The following external Moonshine skills are related execution layers, not files to duplicate into this repository:

- `moonshine-crm-intake`
- `moonshine-funding-follow-up`
- `moonshine-crm-schema-steward`
- `moonshine-crm-data-hygiene`
- `moonshine-crm-reconciler`

Do not copy or edit those skills from this repository task. Instead, identify any post-revision alignment needed in the final PR summary.

## Verification

Before completing documentation work:

1. Review all affected cross-references.
2. Check for contradictory Giggle/BankBreezy/Plaid guidance.
3. Check that applicant add/update workflows require public research.
4. Check that task and outreach guidance follows the state-machine model.
5. Report changed files, intentionally unchanged files, and unresolved ambiguities.
