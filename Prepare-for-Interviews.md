# Prepare for Interviews

Use `interview-brief` when the role is clear and interview preparation is needed.
An exact role identifier provides the strongest link to the archived job description.

## Process

1. Resolve the role identifier. Clarify ambiguous matches before the brief is created.
2. Use the archived job description as the primary role source.
3. Select the master CV and read career context.
4. Research the employer, recent developments, and relevant industry changes.
5. Reuse available role scores from the configured legacy score source, or calculate role scores when no match exists.
6. Map strengths, gaps, likely interview topics, and questions to explore.
7. Prepare source-supported stories and anticipated questions.
8. Convert the brief from Markdown to a self-contained HTML file.
9. Link the HTML brief to the matching tracker row through `log-cv-application`.

## Answer structure

Behavioral stories use Situation, Task, Action, and Result (STAR).
The story bank normally contains 5-6 stories with theme tags. Anticipated questions refer to those stories.
Gap and motivation questions use acknowledge, reframe, and forward instead of forced STAR answers.

Every result metric must appear in the master CV.
Mark unsupported situation or task detail with a confirmation marker. Do not invent clients, people, dates, or amounts.

## Output

The HTML brief includes employer research, industry context, alignment, strengths, gaps, likely topics, questions to explore, answers, and the job description.
The converter uses fixed Markdown sections to create the brief tabs.
Research gaps remain explicit. The workflow does not open the brief automatically unless the user requests that action.

## Current compatibility boundary

The interview skill can read a configured legacy CSV for prior scores.
The tracker skill writes the Markdown tracker and does not use that CSV.
The wiki describes this boundary as current behavior. The wiki does not claim that the two records synchronize automatically.

Process references: `interview-brief` instructions, `md_to_html.py`, and the tracker skill's brief handoff.
