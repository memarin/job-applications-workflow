# Skills Reference

Each skill owns a specific part of the workflow. Automatic handoffs connect document creation with the tracker.

| Skill | Purpose | Relevance |
| --- | --- | --- |
| `analyze-job` | Assess a role and recommend a CV variant | Focus effort on roles with supported fit |
| `cv-writer` | Create a tailored CV and evidence audit | Connect job requirements with supported career evidence |
| `log-cv-application` | Create and update tracker records | Keep document references and application status consistent |
| `job-applications` | Display and search tracker records | Find current application information without changes |
| `interview-brief` | Create a role-specific interview brief | Prepare evidence-based answers and questions |

## analyze-job

- **Trigger:** A user supplies a job posting URL or job description text.
- **Inputs:** Job description, private profile configuration, role-fit matrix, career context, and external research.
- **Steps:** Archive the description, research the role, assess eligibility and fit, and select a CV variant.
- **Outputs:** Archived description, fit summary, score, flags, and `DO APPLY` or `DO NOT APPLY`.
- **Handoff:** `DO APPLY` starts `cv-writer` with the exact role identifier.
- **Limit:** A blocked job page requires pasted text. Missing evidence remains visible.

See [Assess a Role](Assess-a-Role).

## cv-writer

- **Trigger:** A direct user request or an automatic handoff from `analyze-job`.
- **Inputs:** Job description, frozen requirements, selected master CV, private configuration, and CV rules.
- **Steps:** Map claims, draft content, render the PDF, inspect each page, obtain independent review, and calculate the audit.
- **Outputs:** Final PDF, evidence audit, and `READY`, `DRAFT`, or `BLOCKED` delivery status.
- **Handoff:** Delegate the tracker record to `log-cv-application` for delivered final CVs.
- **Limit:** A job requirement cannot establish candidate experience. The skill does not submit applications.

Final `DRAFT` and `BLOCKED` PDFs can still have tracker records. The tracker status does not replace the audit outcome.
Intermediate renders do not qualify for a final CV record.

See [Create a CV](Create-a-CV).

## log-cv-application

- **Trigger:** A completed CV, completed interview brief, requested field update, or requested stale-record scan.
- **Inputs:** Final document metadata, an exact role identifier, or a field and its new value.
- **Steps:** Validate input, match records, check conflicts, write the change, read the record again, and produce a receipt when applicable.
- **Outputs:** A confirmed tracker outcome, receipt when applicable, and local Git commit result when the tracker is in a repository.
- **Handoff:** None. This skill owns tracker writes for the workflow.
- **Limit:** Conflicts require resolution. A stale-record scan needs confirmation before status changes.

A tracker failure does not invalidate a completed CV or interview brief.

See [Track Applications](Track-Applications) and [Maintain the Tracker](Maintain-the-Tracker).

## job-applications

- **Trigger:** A user asks to show, list, find, or search applications.
- **Inputs:** An optional query and configured tracker source.
- **Steps:** Read the tracker and print matching or closely matching records.
- **Outputs:** Tracker rows in the terminal. No query returns all rows in tracker order.
- **Handoff:** None.
- **Limit:** The skill does not create or modify the tracker.

Programmatic count or JSON output is available when explicitly requested.

## interview-brief

- **Trigger:** A user requests preparation for an identified role.
- **Inputs:** A role identifier, archived description or supplied job text, master CV, career context, and employer research.
- **Steps:** Resolve the role, assess alignment, identify gaps, prepare stories and anticipated questions, and convert the brief to HTML.
- **Outputs:** A self-contained HTML brief with research, role alignment, answers, and the source job description.
- **Handoff:** Ask `log-cv-application` to link the brief to the existing tracker row.
- **Limit:** An ambiguous role needs clarification. Unsupported story details require explicit confirmation markers.

See [Prepare for Interviews](Prepare-for-Interviews).

Process references: each skill's `SKILL.md`; tracker validation and outcomes also follow `entry.py`.
