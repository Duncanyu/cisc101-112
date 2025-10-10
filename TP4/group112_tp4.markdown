# Week 6 Group Reflection

## Group Members
- [List all group members’ names]

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
[List 2–3 issues you noticed in your spec or prompt]

**Debugging Request Sent to AI:**
[Paste or paraphrase what you asked the AI]

**AI’s Main Suggestions:**
[List 3 key pieces of feedback and their rationale]

**Revised Prompt/Spec:**
[Insert updated version after applying fixes]

**Justification:**
[Briefly explain why you chose these fixes]

**Transcript Links:**
- [Debugging session link]
- [Retest session link]

**Reflection (25 words):**
[Write about which feedback was most useful and why]

---

## Group Reflection (100 words)

**Prompt Engineering Reflection:**


[For prompt engineering, there has been a large introduction and review for the past few concepts that have been learnt in class. From the initial zero shot prompting, there has been a increase in the varied challenges needed for the different needs of prompters. The analysis given by self-correcting prompts was a large gamechanger, as it allowed for the Large language model to do most of the heavy lifting on enabling a benefical prompt. For Set 3 and onwards, the design element of prompting was brought to the forefront. Instead of decomposition seen in earlier prompting questions, the prompt is built from the ground up, forcing a different logical sequence on emphsis towards prompt patterns and elements. Overall, the prompting required and completed throughout this assignment has been very beneficial.]

