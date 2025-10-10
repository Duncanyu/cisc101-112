
**Submission Template**:

# Week 6 Group Reflection

## Group Members
- [List all group members’ names]

---

## Set 1: Zero-Shot Prompting

### Task 1.1: Zero-Shot Prompt and Comparison

**Zero-Shot Prompt:**
[Insert zero-shot prompt text]

**Transcript Links:**
- [Zero-shot output link]
- [Few-shot output link (from TP3 reuse)]

**Analysis (25 words):**
[Insert reflection on clarity, structure, or tone differences]

---

## Set 2: Self-Consistency

### Task 2.1: Self-Consistency Assumption Analysis

**Transcript Links:**
- [Version 1 link]
- [Version 2 link]
- [Version 3 link]

**Comparison Notes:**
- **Strengths:** [Insert key points]
- **Weaknesses:** [Insert key points]
- **Differences:** [Insert key points]

**Selected Itinerary:**
[Paste or summarize selected version]

**Justification:**
[Explain why this version is best suited for the client]

**Analysis (25 words):**
[Insert reflection on self-consistency benefits]

---

## Set 3: Spec-Based Development

### Task 3.1: Designing Specifications

**Specifications for “Daily Budget Breakdown” Feature:**
- **Inputs:** Total daily budget and currency, itinerary (destinations, dates, available activities), group size
- **Outputs:** Daily budget breakdown that lists each day's activities and costs, calculated total daily cost with comparison again user's budget, remaining amount or if it exceeds the user budget, summary displaying trip cost, average daily spending, and any days over budget
- **Constraints:** Total daily cost must not exceed the user's specificed daily budget, format must be concise yet include enough context to maintain visual clarity, 

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


[Insert 100-word group reflection here]

