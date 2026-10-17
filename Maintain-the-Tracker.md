# Maintain the Tracker

Use `job-applications` for queries. Use `log-cv-application` for changes.

## Find records

Ask to list all applications or search for a role or employer.
The query skill prints matching records without changes. An empty query returns all rows in tracker order.
Count and JSON modes serve explicit programmatic requests.

The display includes the date, role identifier, employer, role, CV reference, status, result, last update, and interview brief.
The display excludes source URL columns.

## Change a field

Supply an exact role identifier and one field with its new value.
For example, use the fictional identifier `Example-Product-a1b2` with `Status: application sent`.
The tracker skill updates a row only when exactly one row matches.

| Outcome | Meaning |
| --- | --- |
| `updated` | The requested change was written and checked |
| `already_updated` | The row already contains the requested value |
| `not_found` | No row matches the identifier |
| `conflict` | Several rows match or the record is inconsistent |
| `failed` | The operation did not complete successfully |

If the field or value is unclear, clarify the request before a write.
The helper updates `Last updated` when that column exists.

## Review stale records

1. Request a stale-application scan with `ghosted`.
2. Review candidate rows whose `Last updated` date is at least 14 days old.
3. Exclude rows already marked ghosted and rows with final rejected, accepted, or ghosted results.
4. Confirm the proposed changes before the helper writes any status.
5. Check the resulting status and date updates.

The scan uses the helper's configured UTC+8 calendar date.
A stale date identifies a candidate for review. A stale date does not prove that an employer stopped contact.

## Local commits

When the tracker belongs to a Git repository, the helper commits only the tracker and applicable receipts that the helper touched.
A local commit is separate from a remote push. A tracker change does not imply that the user submitted an application.

Process references: `job-applications` instructions, `search_tracker.py`, `log-cv-application` instructions, and `entry.py`.
