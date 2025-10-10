# Week 6 Group Reflection

## Group Members
- Brian Xu, Noah Arega, Duncan Yu

---

## Set 1: Zero-Shot Prompting

### Task 1.1: Zero-Shot Prompt and Comparison

Transcript link (zero-shot prompt) - https://copilot.microsoft.com/shares/9GKWhsrZH7AHP2g5Yu2DH
Transcript link (few-shot prompt) - https://copilot.microsoft.com/shares/UcL6sW9NQzpfbwoGSeQ7t

Analysis - When the prompt was zero-shot (No example prompting) was formatted, specificity was out the window: the emphisis of the output was nowhere to be seen, and the output was spread to thin. By comparison, with few shot prompting (Yes example prompting), the output was concise, listing of only four lines: cost, restaurant, museum, and park.

---

## Set 2: Self-Consistency

### Task 2.1: Self-Consistency Assumption Analysis

**Transcript Links:**
https://copilot.microsoft.com/shares/URCosj4bxVPFiZj9JJDSn 

https://copilot.microsoft.com/shares/Q5yVviHbTYdnFr8vw59wt

https://copilot.microsoft.com/shares/Gx1mRW5hosnyyEHSdVuzH

**Comparison Notes:**
- **Strengths:** [Concise information, accurate limitation on budgetary demands]
- **Weaknesses:** [Too varied without any specific actions, benefits do not apply to a large variety]
- **Differences:** [Emphasis on each activity differs (Activity itself or surrounding impact done by activity), or very jutted outputs with little correlation between them]

**Selected Itinerary:**
[(https://copilot.microsoft.com/shares/Q5yVviHbTYdnFr8vw59wt)]

**Justification:**
This version is best suited for the client based on the existing requirements for neatness, while accounting for all additional needs by the client. On other prompts and especially on prompt output one, activities and thoughts were very split apart.

**Analysis (25 words):**
The benefit of self-consistency is that it allows for improving the accuracy of each prompt output not by repeatedly scrutinizing each prompt element, but by allowing the Large Language Model to do most of the heavy lifting on fixing the prompt to fit the needs of each user

---

## Set 3: Spec-Based Development

### Task 3.1: Designing Specifications

**Specifications for “Daily Budget Breakdown” Feature:**
- **Inputs:** Total daily budget and currency, itinerary (destinations, dates, available activities), group size
- **Outputs:** Daily budget breakdown that lists each day's activities and costs, calculated total daily cost with comparison again user's budget, remaining amount or if it exceeds the user budget, summary displaying trip cost, average daily spending, and any days over budget
- **Constraints:** Total daily cost must not exceed the user's specificed daily budget, format must be concise yet include enough context to maintain visual clarity, emphasis on budgeting time and money.

---

### Task 3.2: Writing and Testing a Prompt

**Final Prompt:**
Please generate a Daily Budget Breakdown for a user’s trip. The user will provide their total daily budget and preferred currency. You will have access to the full itinerary, including destinations, dates, available activities, and group size.

Using this information, list each day’s activities along with their individual costs, calculate the total daily cost, and compare it against the user’s specified daily budget. Indicate how much of the budget remains or, if the total exceeds the budget, clearly display an alert. At the end, provide a short summary showing the total trip cost, average daily spending, and any days that went over budget.

Ensure that the total daily cost never exceeds the user’s specified daily budget. All prices must be displayed in the user’s chosen currency, rounded to two decimal places. The output format should be concise, visually clear.

**Transcript Link:**
https://copilot.microsoft.com/shares/GtyB6xULU4BwfsTeKgaCC

**Evaluation:**
- **Met specifications?** Yes
- **Successes:** The LLM correctly followed all specified inputs, outputs, and constraints which included accurate retrieval from the itinerary, total calculations, and daily budget compliance. The final output was also clear, organized, and accessible, presenting totals, remaining budgets, and a trip summary with visual indicators (emojiis) for easy interpretation.
- **Failures or gaps:** Copilot added extra commentary and emojis that were not explicitly requested in the specification. 

**Improvement Plan (25 words):**
Future iterations should ensure that the output remains strictly aligned with the provided specifications by removing any unnecessary commentary or weird stylistic things. The LLM’s responses should focus only on the outputs defined in the task (activities, totals, and summaries) without adding decorative or conversational elements.

---

## Set 4: AI-Assisted Debugging

### Task 4.1: Debugging with AI Feedback

**Issues Identified in Set 3:**
- The model adds extra commentary and emojies
- Currency symbols and rounding isnt always consistent
- (not visible) over budgeting behavior isn't strictly defined

**Debugging Request Sent to AI:**
I wrote the above specifications for the Daily Budget Breakdown. When I test it, I notice: The model adds extra commentary emojies. Currency symbols and rounding aren’t always consistent. Over budget behavior isn’t strictly defined (it might still list items). Please help me debug. Suggest concrete edits or rephrasings that will fix these. explain why each change helps.

**AI’s Main Suggestions:**
"The output format must be concis, visually clear" --> “The output must be strictly professional and free of emojis, casual commentary, or decorative language.”
- This sets a clear tone expectation. Without this, the model may default to a friendly or expressive style.
“All prices must be displayed in the user’s chosen currency, rounded to two decimal places.” --> “All prices must use the correct currency symbol (e.g., $, €, £) and be formatted to exactly two decimal places (e.g., $12.50).”
- This clarifies both symbol and formatting expectations. The model now knows to standardize output.
"Indicate how much of the budget remains or, if the total exceeds the budget, clearly display an alert.” --> “If the total daily cost exceeds the budget, do not list activities that cause the overage. Instead, display a clear warning: ‘⚠️ Over Budget: Daily total exceeds budget by [amount]’. Ensure the final daily cost never exceeds the budget.”
- This enforces a strict rule: no activities beyond budget, and a consistent alert format.

**Revised Prompt/Spec:**
Please generate a Daily Budget Breakdown for a user’s trip. The user will provide their total daily budget and preferred currency. You will have access to the full itinerary, including destinations, dates, available activities, and group size.

Using this information, list each day’s activities along with their individual costs, calculate the total daily cost, and compare it against the user’s specified daily budget. If the total daily cost exceeds the budget, do not list activities that cause the overage. Instead, display a clear warning: ‘⚠️ Over Budget: Daily total exceeds budget by [amount]’. Ensure the final daily cost never exceeds the budget. At the end, provide a short summary showing the total trip cost, average daily spending, and any days that went over budget.

Ensure that the total daily cost never exceeds the user’s specified daily budget. All prices must use the correct currency symbol (e.g., $, €, £) and be formatted to exactly two decimal places (e.g., $12.50). The output must be strictly professional and free of emojis, casual commentary, or decorative language.

**Justification:**
the fixes were chosen to make the output more consistent through multiple iterations, professional, and fully compliant iwht the original specifications and constraints. The earlier version of the prompt allowed informal tones, extra commentary, and emojis. By enforcing a clear rule for everything like tone, language, formatting, and behavior, it improves the reliability of the LLM's responses.

**Transcript Links:**
- [\[Debugging session link\]](https://copilot.microsoft.com/shares/7AhStrLXdF8o9nsBQRHdT)
- [\[Retest session link\]](https://copilot.microsoft.com/shares/YprYStrM65sQtekmKznn1)

**Reflection (25 words):**
The most useful feedback was to change formatting restrictions to be more specific, this gave Copilot a better understanding of what its responses should look like. Something that I was unable to test was the over-budgeting behavior, as the itinerary had no costs that were over the budget.

---

## Group Reflection (100 words)

**Prompt Engineering Reflection:**


[For prompt engineering, there has been a large introduction and review for the past few concepts that have been learnt in class. From the initial zero shot prompting, there has been a increase in the varied challenges needed for the different needs of prompters. The analysis given by self-correcting prompts was a large gamechanger, as it allowed for the Large language model to do most of the heavy lifting on enabling a benefical prompt. For Set 3 and onwards, the design element of prompting was brought to the forefront. Instead of decomposition seen in earlier prompting questions, the prompt is built from the ground up, forcing a different logical sequence on emphsis towards prompt patterns and elements. Overall, the prompting required and completed throughout this assignment has been very beneficial.]

