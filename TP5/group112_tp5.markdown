Names: Duncan Yu

### Task 1.1

| Test ID | Test Oracle                                                                                                                                   | Res. | Notes / Refinement Made                                                                             | Transcript Link(s)                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| T1      | Output is a table with columns: Day, Activity, Cost. Table contains 9 activity rows (3*3) plus a Total row.                                   | Fail | LLM gave an "unstructured"/messy response that you have to scroll to read. refined to suggest table | https://copilot.microsoft.com/shares/GvMQF17RL3t9Li61zCmAZ |
| T2      | Per-day coverage: each of the 3 days lists exactly 1 museum, 1 restaurant, 1 park no extra and no omissions.                                  | Fail | It's in a table now! Copilot did not explicitly give sections for cultural visits, places to eat... | https://copilot.microsoft.com/shares/No8r2SnEh4XJvZDj7XunV |
| T3      | Budget: numeric Total equals the arithmetic sum of all 9 costs and the Total is <= $750                                                       | Fail | Copilot correctly gave under $750 trip. Extra commentary and budget not fully utilized              | https://copilot.microsoft.com/shares/gcNtiQy3rCZodWy7v9cx2 |
| T4      | Inputs respected and scope controlled: budget fully utilized, no content outside the table (no extra unrelated commentary, tips, or emojiis). | Pass | Copilot fully utilized the given budget and did everything according to specifications.             | https://copilot.microsoft.com/shares/5vLRq2kUD4eHDDpb41ckT |

[insert refined prompts]
v1: Plan a short 3 day trip to Paris that balances culture, food, and outdoor experiences while staying reasonably budget mindful. Keep it clear and structured enough to be easy to follow.

v2: Create a 3 day plan for visiting Paris with organized daily activities that also include cultural visits, places to eat, and outdoor activities, keeping cost awareness in mind. Present it in a table format.

v3: Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Keeping cost awareness in mind. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything.

v4: Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant.

Refleciton:
TDD made me define oracles, test, then tightening specificity by trying to fix one issue at a time. Produced an excellent prompt.

###Task 2.1

| Test ID | Edge Case Test Oracle | Pass/Fail | Notes / Changes | Transcript Link(s) |
| ------- | --------------------- | --------- | --------------- | ------------------ |
| T5      | Edge Case #1          |           |                 |                    |
| T6      | Edge Case #2          |           |                 |                    |

[insert refined prompts]

[v1:...]

[v2:...]

[insert 25-word reflection]



###Task 2.2:

| Test ID | Test Oracle | Pass/Fail | Notes / Changes | Transcript Link |
| ------- | ----------- | --------- | --------------- | --------------- |
| T7      |             |           |                 |                 |

[insert refined prompt]

[v1:...]

[insert 25-word reflection]

Group reflection:

[insert 100-word reflection]

**Deliverables**: Markdown file (`week8_reflection.md`) with all task outputs, transcript links, and 100-word reflection.
