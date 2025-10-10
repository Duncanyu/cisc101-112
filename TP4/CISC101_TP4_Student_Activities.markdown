# CISC 101: Week 6 Tutorial - Travel Planner: Advancing Prompting + Spec Design + AI4SE

Welcome to the Week 6 tutorial for CISC 101. In this session, you will work in groups of 3 to apply zero-shot prompting, self-consistency, spec design and AI4SE for the *Travel Planner* prompt. Open Microsoft Copilot in guest mode before starting.

## Required Materials

- Access to Microsoft Copilot (open in guest mode).
- A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files.
- Collaboration with group members.

## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews Week 6 concepts.
- **Next 60 minutes**: Complete group activities in four sets.
- **Following 10 minutes**: Write a group reflection in Markdown.
- **Final 10 minutes**: Q&A with instructor.

## Activities (60 minutes)

The activities are divided into four sets: Set 1 focuses on zero-shot prompting, Set 2 on self-consistency, Set 3 on spec design, and Set 4 on on AI-assisted debugging (AI4SE).

### Set 1: Zero-Shot Prompting

#### Task 1.1: Zero-Shot Prompting

**Objective**:Understand how zero-shot prompting differs from few-shot prompting and how it affects clarity and output consistency in the _Travel Planner_.

Background: In a previous tutorial (Task 3.2), you wrote a few-shot prompt for the Travel Planner that included examples to teach the model the correct style and structure of itineraries. Now, we will contrast that with a zero-shot prompt, where no examples are provided.

**Steps**:

1. Open a new chat in Microsoft Copilot in guest mode.
2. Test the following prompt: "Plan a 1-day Paris itinerary under $150 that includes a museum, a park, and a restaurant." Save transcript via shareable link.
3. Start a new chat in Microsoft Copilot in guest mode. Reuse your few-shot prompt from Task 3.2 (TP3) and test it again for comparison. Save transcript link.
4. Write a 25-word reflection in Markdown on how the two outputs differed (structure, tone, clarity).

**Deliverables**:

- Transcript links
- 25-word analysis

### Set 2: Self-Consistency

#### Task 2.1: Self-Consistency Assumption Analysis

**Objective**: Explore how generating multiple outputs for the same prompt can reveal hidden assumptions, inconsistencies, or errors. Practice selecting the best version.

Background: A travel agency has received a request from a niche client: a family with a toddler, a senior with mobility limitations, and a tight budget. Since you don’t have much prior experience designing itineraries for these needs, you will use _self-consistency prompting_. This means generating multiple versions of the plan, each representing a different reasoning path, and then comparing them to select the most reliable, client-ready itinerary.

**Steps**:

1. Open Microsoft Copilot in guest mode

2. Run this prompt three times, each in a new chat and save all three transcript links. 
   
   ```
   Plan a 1-day Paris itinerary with a $500 budget for a family with a toddler and a senior who cannot walk long distances. 
   ```

3. Review the three outputs and compare them. Identify:
   
   * Major differences (activities chosen, handling of mobility needs, budget strategies).
   
   * Weaknesses (e.g., unrealistic activities, missing toddler-friendly options).
   
   * Strengths (e.g., accessibility, balance of indoor/outdoor activities).

4. Select the best itinerary and justify why it best meets the client’s needs.

5. Write a 25-word reflection in Markdown on how self-consistency gave you a stronger plan than relying on a single output.

**Deliverables**:

- Three transcript links
- Comparison notes (strengths, weaknesses, differences).
- Selected itinerary and justification
- 25-word analysis

### Set 3: Spec-Based Development

#### Task 3.1: Designing Specifications

**Objective:** Learn how to design specifications (inputs, outputs, and constraints) for a new feature before writing a prompt.

Background: The travel agency has requested an additional feature for their AI-powered Travel Planner: they want to include a _“Daily Budget Breakdown”_ for trips. Each day of the itinerary should list activities with individual costs and ensure the total daily cost does not exceed the user’s specified daily budget.

Before you write a prompt, you must design specifications. 

**Steps**:

1. Identify **inputs, outputs, and constraints** for the “Daily Budget Breakdown” feature.

2. Write them as a short specification.

3. Be as precise as possible (e.g., specify format, daily limits, or accessibility needs).

**Deliverables**:

* Written specification.
  
  

#### Task 3.2: Writing and Testing a Prompt from Your Specs

**Objective:** Translate your specifications into a working prompt and evaluate whether the output meets your design.

**Steps**:

1. Based on your specification from Task 3.1, write a clear prompt that instructs the AI to generate a **Daily Budget Breakdown.**

2. Run the prompt in Microsoft Copilot (guest mode). Save the transcript link.

3. Compare the AI’s output against your specifications. Did it follow the inputs, outputs, and constraints you defined? Where did it succeed or fail?

4. Write a 25-word explanation in Markdown describing whether your specification was met and how you would improve the prompt or the spec for the next iteration.

**Deliverables**:

* Final prompt.

* Transcript link.

* Comparison

* 25-word explanation.

### Set 4: AI4SE - AI-Assisted Debugging

#### Task 4.1: Debug the “Daily Budget Breakdown” Prompt with AI

**Objective:** Fix prompt/spec mismatches you found in Set 3 using AI assistance.

**Steps**:

1. Open a new chat with the AI (start fresh — don’t reuse your earlier chat).

2. Paste your full prompt and spec from Set 3.

3. Add a short debugging request that looks like this:
   
   > I wrote the above specifications and prompt for an AI-based Travel Planner app. I noticed a few issues when testing it: 
   > e.g.: 
   > – It sometimes gives incomplete itineraries 
   > – The tone is inconsistent 
   > – Some costs are missing 
   > Please help me debug it. Suggest concrete edits or re-phrasings that could fix these issues, and explain why each change might help.

4. Read the AI’s feedback carefully.
   
   * Note at least three specific suggestions.
   
   * Decide which ones to apply and justify your choice briefly.

5. Revise your prompt/spec based on the chosen fixes.

6. Test the revised version in a new chat with the spec design from Set 3.

7. Write a 25-word reflection explaining what type of feedback was most useful and how it will influence how you debug prompts in the future.
   **Deliverables**:
   
   * Transcript links from the debugging and testing sessions
   
   * List of selected AI suggestions you chose to apply 
   
   * Revised prompt/spec showing the applied fixes
   
   * 25-word reflection

## Group Assignment (10 minutes)

**Objective**: Compile work and write a 100-word reflection on prompt engineering.

**Steps**:

1. Combine outputs into one Markdown file using the template below.
2. Write a 100-word reflection addressing the following: What did your group learn about designing and debugging prompts? How did zero-shot prompting, self-consistency, specification design, and AI-assisted debugging improve your understanding of prompt engineering?

**Submission Template**:

```
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
- **Inputs:** [List expected user inputs]
- **Outputs:** [List what AI should produce]
- **Constraints:** [Budget limits, accessibility, etc.]

---

### Task 3.2: Writing and Testing a Prompt

**Final Prompt:**
[Insert your full prompt]

**Transcript Link:**
[Insert test run link]

**Evaluation:**
- **Met specifications?** [Yes/No/Partially]
- **Successes:** [List 1–2 strengths]
- **Failures or gaps:** [List 1–2 issues]

**Improvement Plan (25 words):**
[Describe how you’d improve next iteration]

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

```

**Deliverables**: Markdown file (`group#_week6_reflection.md`) with all task outputs, transcript links, and 100-word reflection.
