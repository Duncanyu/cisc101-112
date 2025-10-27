Names: Duncan Yu, Brian, Noah Arega

### Task 1.1

| Test ID | Test Oracle                                                                                                                                   | Res. | Notes / Refinement Made                                                                             | Transcript Link(s)                                         |
| ------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| T1      | Output is a table with columns: Day, Museum + cost, Restaurant + cost, Park + cost, Totals. Table contains 4 rows, 1 for each day  + total.   | Fail | LLM gave an "unstructured"/messy response that you have to scroll to read. refined to suggest table | https://copilot.microsoft.com/shares/GvMQF17RL3t9Li61zCmAZ |
| T2      | Per-day coverage: each of the 3 days lists exactly 1 museum, 1 restaurant, 1 park no extra and no omissions.                                  | Fail | It's in a table now! Copilot did not explicitly give sections for cultural visits, places to eat... | https://copilot.microsoft.com/shares/No8r2SnEh4XJvZDj7XunV |
| T3      | Budget: numeric Total equals the arithmetic sum of all 9 costs and the Total is <= $750                                                       | Fail | Copilot correctly gave under $750 trip. Extra commentary and budget not fully utilized              | https://copilot.microsoft.com/shares/gcNtiQy3rCZodWy7v9cx2 |
| T4      | Inputs respected and scope controlled: budget fully utilized, no content outside the table (no extra unrelated commentary, tips, or emojiis). | Pass | Copilot fully utilized the given budget and did everything according to specifications.             | https://copilot.microsoft.com/shares/5vLRq2kUD4eHDDpb41ckT |

v1: Plan a short 3 day trip to Paris that balances culture, food, and outdoor experiences while staying reasonably budget mindful. Keep it clear and structured enough to be easy to follow.

v2: Create a 3 day plan for visiting Paris with organized daily activities that also include cultural visits, places to eat, and outdoor activities, keeping cost awareness in mind. Present it in a table format.

v3: Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Keeping cost awareness in mind. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything.

v4: Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant.

Refleciton:
TDD made me define oracles, test, then tightening specificity by trying to fix one issue at a time. Produced an excellent prompt.

###Task 2.1

| Test ID | Edge Case Test Oracle                    | Res. | Notes / Changes                                                                                     | Transcript Link(s)                                         |
| ------- | ---------------------------------------- | ---- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| T5      | Museum closed on trip day --> replace    | Fail | The Louvre is closed (Unique :)                                                                     | https://copilot.microsoft.com/shares/BthDDDFsepi6S9ecVEaB8 |
| T6      | Rainy weather --> swap outdoor to indoor | Pass | Copilot realized the the Louvre is shut down, and that it will be raining, so it swapped the events | https://copilot.microsoft.com/shares/E3dRqeSHNbCAjiV1wPJVX |

v1: Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant.

v2: Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant. After everything, verify with a web search to ensure all activities are available and open (October 27th, 2025), not only for hours but for special events, situations, and holidays. For example if the Louvre is closed, find a replacement, if it is raining, find a different activity that is indoors.

Reflextions:
The edge case testing showed failures from Copilot to verify. The prompt had to explicitly state instructions/steps to verify in order for Copilot to correctly return results. In the end, Copilot was able to do research and show real time results.


###Task 2.2:

| Test ID | Test Oracle | Pass/Fail | Notes / Changes | Transcript Link |
| ------- | ----------- | --------- | --------------- | --------------- |
| T7      | Table only lists real, open museums, restaurants, and parks for each day. | Fail | Still listing closed museums | https://copilot.microsoft.com/shares/f4c5RfPYotWV2sS9Fm4sR |
| T8      | Table only lists real, open museums, restaurants, and parks for each day. | Pass | Listed museums are all open  | https://copilot.microsoft.com/shares/dqChvpSXMv37gMLDvpuZe |

v1: Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant. After everything, verify with a web search to ensure all activities are available and open (October 27th, 2025), not only for hours but for special events, situations, and holidays. For example if the Louvre is closed, find a replacement, if it is raining, find a different activity that is indoors.

v2: [Query with Search on] Return just a table. Create a clearly organized 3 day Paris itinerary where each day has one cultural visit, one restaurant, and one outdoor spot. Include a price for each activity using a single dollar value. Utilize fully a budget of $750, but do not go over that. Present it in a table format with 5 columns, [Day | Museum + cost | Restaurant + cost | Park + cost | Totals] and a final total row underneath everything. Do NOT include ANY extra unrelated commentary or text, ONLY give the table and anything relevant. After everything, verify with a web search to ensure all activities are available and open (October 27th, 2025). Some museums could be permanently closed, undergoing renovation, or shut down due to security events, make sure to research via articles and current news to ensure availability. If a mueum is closed, find a replacement, if it is raining, find a different activity that is indoors.

Reflections:
After some work, the new prompt managed to get Copilot to do research, list references, and confirm availability, specifically the fact that the Louvre is currently shut down, thus, not listing as an activity.

Group reflection:
Writing these tests forced us to write precise specifications instead of just vague intetions. The failures from T1-T3 showed how easily AI can ramble/give commentary and unstructured text, unless constraints are explicitly stated. The edge case testing in Task 21. also showed another key thing, the model often confidently returns incorrect, outdated, and non-concurrent results unless we explicitly and really demand real-time verification. Task 2.2 continues on the idea of verification. Turning on Search mode and giving the LLM the ability to view contemporary information allowed for it to give correct and concurrent results. Future tests could help refine the prompt even more to prevent the use of nonexistent cities, missing or unrealistic budgets (too low, way too high) or im possible dates (9999, or february 30th).
