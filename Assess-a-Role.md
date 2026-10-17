# Assess a Role

Use `analyze-job` to assess a job URL or pasted job description.

## Process

1. Get readable job text. If the page is blocked, request pasted text.
2. Create a unique role identifier, such as the fictional `Example-Product-a1b2`.
3. Archive the employer's description as `job_description.md` before the fit assessment.
4. Research the employer and role context. Mark unavailable research explicitly.
5. Reconcile location, seniority, and domain claims against the available evidence.
6. Apply the role-fit matrix and record confidence for each criterion.
7. Report the apply recommendation and the selected CV variant.
8. Start `cv-writer` automatically when the recommendation is `DO APPLY`.

## Evidence rules

The job description supplies role requirements. A current employer-controlled posting for the exact role can resolve a conflict when its authority is clear.
Employer facts and peer vacancies provide context. Those sources cannot establish this role's authority, responsibilities, or eligibility.

Record eligibility as `eligible`, `ineligible`, or `unknown`.
Missing location terms remain unknown. Missing seniority scope remains provisional rather than proof of a junior role.

## Decision

The skill applies explicit disqualifiers before the apply recommendation.
Those disqualifiers include a score below 50, ineligibility, supported junior scope, and the specified combinations of weak criteria.
An unknown condition must remain visible in the fit summary.

`DO NOT APPLY` stops automatic CV creation. A later direct CV request remains a separate user instruction.

## Outputs

The compact result contains the total, verdict, CV variant, flag counts, fit summary, and archived description reference.
The role-fit score is separate from the later CV quality audit.

Next: [Create a CV](Create-a-CV.md).

Process references: `analyze-job` instructions, role-fit matrix, and `create_role_dir.py`.
