# CISC 101: Week 8 Tutorial - Travel Planner: Building and Testing Like a Software Engineer

Welcome to the Week 8 tutorial for CISC 101. In this session, you will work in groups of 3 to apply test-driven development (TDD) strategies to the *Travel Planner* prompt. Open Microsoft Copilot in guest mode before starting.

## Required Materials

- Access to Microsoft Copilot (open in guest mode).
- A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files.
- Collaboration with group members.

## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews Week 8 concepts.
- **Next 60 minutes**: Complete group activities in three sets.
- **Following 10 minutes**: Write a group reflection in Markdown.
- **Final 10 minutes**: Q&A with instructor.

## Activities (60 minutes)

The activities are divided into three sets: Set 1 focuses on TDD with provided tests, Set 2 on edge-case-driven and hallucination mitigation TDD.

Examine the following spec-based design for a travel planner prompt.

| **Category**          | **Specification**                                                                                                                                                                                         | Acceptance notes (these are not test oracles)                                                   |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Inputs**            | • City: Paris <br/>• Duration: 3 days <br/>• Total budget: $750 <br/>• Required activity types: museum, restaurant, park                                                                                  | Inputs are valid and as stated; no missing inputs or invalid values                             |
| **Activity Coverage** | For each of the 3 days, include exactly: 1 museum, 1 restaurant, 1 park. No extras, no omissions.                                                                                                         | Per-day check: 3 rows/day, one of each type                                                     |
| **Budget Constraint** | Total cost ≤ $750.                                                                                                                                                                                        | Recompute sum; confirm it is ≤ 750                                                              |
| **Outputs**           | A Markdown table with columns<u> Day, Activity, Cost</u>. <br/>Each day lists exactly 3 activities (1 museum, 1 restaurant, 1 park). <br/>A Total row appears at the bottom showing the sum of all costs. | Table renders correctly in Markdown; columns named exactly; Total row present and at the bottom |

---

##### **Notes About "*Test Oracles*"**

Each test oracle is a rule or expectation that defines what a *correct* output (or input) looks like. When filling the tables below, describe the **oracle — not just the test action.**

Example: 
❌ Test: "Check if budget under $750"  - this is a procedure, not a rule.

✅ Oracle: "Total cost in itinerary must be ≤ $750" - this is a rule. Think of each oracle as your “source of truth.”  - it’s the rule you’ll test against in the Red–Green–Refactor cycle.

----

##### Task 1.1: TDD Using Red → Green → Refactor Cycle

**Objective:** Experience the TDD loop by writing tests before prompting, then iterate through Red–Green–Refactor until the prompt satisfies the specs for budget, activity coverage, and format. Refer to the lecture notes to refresh your memory.

**Steps**:

1. **Red (Write a Failing Test)**: Write a failing test and record it in the table below as "T1". 

2. Run the prompt in Microsoft Copilot (guest mode). Begin with the minimal prompt: "Generate a 3-day Paris itinerary." Record Fail/Pass in the table for T1.

3. **Green (Refine Prompt)**: Fix the prompt to pass the failed test, rerun and record Fail/Pass.

4. **Refactor (Repeat)**: Repeat this process until your prompt has passed 4 distinct tests prepared based on the spec design provided above. 

**Deliverables**

- Test register table (see submission template below)
- Prompt versions (initial → refined)  
- Transcript links
- 25-word reflection on how TDD changed your prompt design process  

### Set 2: TDD for Edge Cases and Hallucination Testing

**Objective:** Follow the TDD loop by writing tests for edge cases.

In TP M3 - Set 2- Task 2.1, you added conditional logic for 2 edge cases (e.g., invalid budget, closed venue). 
Now you will write tests for those cases and verify them using TDD.  

>  **Note:** Ignore the <u>old sample prompt</u> (“1-day Paris itinerary for tomorrow”).  
> 
> Continue using the main Travel Planner specifications outline above. You should add extra inputs (e.g., trip date, hotel you're staying in) for tests. In other words, your refined prompt from Task 1.1 above should include "the trip start on date X" or "I am staying in hotex X" if needed.

### Task 2.1: Design Edge-Case Tests

**Steps**:

1. Refer to the edge cases you chose in TP M3/8, Set 2, Task 2.1.

2. **Red (Write Minimal Prompt)**: Write a failing test and record it in the table below as "T5". Begin with the final version of the refined prompt you wrote in Task 1.1 above. WHAT IN THE FUCK IS THE FUCKING PURPOSE OF THIS BULLSHIT. THIS IS THE REASON WHY THE GUY HAS A 1.1/5 WHAT AM I WRITING A TEST FOR IF I ALREADY FUCKING REFINED IT IN 1.1

3. Run the prompt in Microsoft Copilot (guest mode). Record Fail/Pass in the table for T5.

4. **Green (Refine Prompt)**: Fix the prompt to pass the failed test, rerun and record Fail/Pass.

5. **Refactor (Repeat)**: Repeat this process until your prompt has passed tests for two edge cases.

**Deliverables:**

* Test register table (see submission template)
* Prompt versions (initial → refined)
* 25-word reflection on how edge-case tests improved prompt robustness.

#### Task 2.2: Hallucination Mitigation Tests

**Objective:** Follow the TDD loop by writing tests for hallucination mitigation.

**Steps**:

1. Discuss with your group members where hallucinations might appear in the output. Based on your discussion, follow the steps below.

2. **Red (Write Minimal Prompt)**: Write a failing test and record it in the table below as "T7". Begin with the final version of the refined prompt you wrote in Task 1.1 above.

3. Run the prompt in Microsoft Copilot (guest mode). Record Fail/Pass in the table for T7.

4. **Green (Refine Prompt)**: Fix the prompt to pass the failed test, rerun and record Fail/Pass.

5. **Refactor (Repeat)**: Repeat until your prompt passes the hallucination test (T7).

**Deliverables:**

* Test register table (see submission template)
* Prompt versions (initial → refined)
* 25-word reflection on how hallucination tests strengthen your confidence in the output.

### Group Reflection

Write a 100-word reflection addressing:  

> How did writing tests first and iteratively refining prompts confirm or challenge the Week 6 specifications? 
> What role did edge-case testing play in building robust prompts? What additional tests might you create to validate inputs (e.g., non-existent cities, missing budget, or impossible dates)?



*Submission template:*

###Task 1.1

| Test ID | Test Oracle | Pass/Fail | Notes / Refinement Made | Transcript Link(s) |
| ------- | ----------- | --------- | ----------------------- | ------------------ |
| T1      |             |           |                         |                    |
| T2      |             |           |                         |                    |
| T3      |             |           |                         |                    |
| T4      |             |           |                         |                    |

[insert refined prompts]
[v1:...]

[v2:...]

[v3:...]

[v4:...]

[25-word reflection]

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
