# Quality and Privacy

This wiki describes the method. Real candidate data and application records stay outside the wiki pages.

## Evidence authority

| Source | What the source can establish |
| --- | --- |
| Employer's job description | Role requirements and explicit constraints |
| Master CV | Candidate career claims and supported metrics |
| Private profile | Identity, configuration, and selection preferences |
| Employer research | Employer context and cited corrections from an authoritative posting for the exact role |
| Final PDF and audit | What the delivered CV says and which checks passed, failed, or did not run |
| Current tracker | Current application record and status |

Career claims need source support. A keyword in a job description cannot establish candidate experience.
Research about peer roles cannot establish this role's eligibility or authority.

## Visible uncertainty

CV evidence classes include `DIRECT`, `TRANSFERABLE`, `MENTION_ONLY`, `ABSENT`, and `UNKNOWN`.
Those classes distinguish demonstrated experience, adjacent evidence, labels, missing evidence, and unresolved ambiguity.
Checks use explicit outcomes such as `PASS`, `FAIL`, `NOT_RUN`, and `NOT_APPLICABLE`.
A high score does not erase failed checks or material gaps.

## Recovery

| Problem | Required response |
| --- | --- |
| Job page is blocked | Request the job description text |
| Role identifier is ambiguous | Clarify the role before the brief or update |
| CV evidence is missing | Mark the gap; do not invent a claim |
| Independent review is unavailable | Record the check as not run |
| PDF content changes | Render the PDF again and repeat affected checks |
| Tracker write is uncertain | Retry once with the same input and check the current row |
| Tracker records conflict | Report the conflict without automatic repair |
| Tracker or viewer step fails | Preserve completed documents and report the failed step separately |

## Wiki privacy

This wiki is public. The wiki contains method documentation only.
The application repository and its records remain private and separate.

Publish process descriptions, generic filenames, and fictional examples only.
Exclude candidate names, contact details, real employers from career history, real application rows, private links, internal paths, and screenshots of records.
Check page text, diagrams, links, filenames, images, and commit metadata before publication.

GitHub wiki access follows repository access. A private repository wiki is visible only to people with access to that repository.
GitHub does not provide a separate private wiki for an otherwise public repository.
Private repository wikis require an eligible GitHub plan.

Source: [GitHub: About wikis](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis).

Process references: the five skill definitions and CV audit rules described in [Sources and Instructions](Sources-and-Instructions.md).
