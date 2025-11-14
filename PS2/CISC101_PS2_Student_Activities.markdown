# CISC 101: Week 10 Tutorial – Research Paper Summarizer: Advanced Prompt Engineering

Welcome to the Week 10 tutorial for CISC 101. In this session, you will work in groups of 3 to apply advanced prompt engineering concepts: Specification Design, Test-Driven Development (TDD), and Modular Prompting  to the *Research Paper Summarizer* application. 

Required Materials

- Access to Microsoft Copilot (open in guest mode)
- A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files
- The “Attention Is All You Need” paper PDF [[1706.03762] Attention Is All You Need](https://arxiv.org/abs/1706.03762) 
- Collaboration with your group members

## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews core concepts: spec design, TDD, and modular prompts.
- **Next 60 minutes**: Complete group activities in four sets.
- **Following 10 minutes**: Write and compile a 100-word group reflection.
- **Final 10 minutes**: Q&A with instructor.
  
  

## Activities (60 minutes)

The tutorial includes four core sets that progressively build on your previous work with the *Research Paper Summarizer*.

### Set 1: Specification Design for a Summarizer

#### Task 1.1: Designing Summarization Specifications

**Objective:** Write a short, testable specification defining how a multi-section summarizer should behave.

**Background:** You are working on a summarization tool that can handle long academic papers by summarizing each section individually and combining the results into a unified summary. Before writing any prompts, you must define the inputs, outputs, and constraints for this system.

**Steps:**

1. Identify the **inputs**, **outputs**, and **constraints** of your summarizer. 
   Use the table format below:

| Category    | Description |
| ----------- | ----------- |
| Inputs      |             |
| Outputs     |             |
| Constraints |             |

Insert at least <u>two components in each row</u>. Examples of constraints: maximum summary length per section, section order, audience type, consistency of terminology, etc. 

2. Be specific and measurable — imagine this specification will serve as a ‘contract’ for the prompt’s behavior.

3. Review your table as a group to ensure it clearly defines how the summarizer should behave. 

**Deliverables:**

- Specification table (inputs, outputs, constraints)

### Set 2: Test-Driven Development (TDD)

#### Task 2.1: Writing Tests Before Prompts

**Objective:**  Apply the Red–Green–Refactor cycle to improve a summarization prompt systematically.

**Background:** Based on your spec design, you will go through the RGR process to write and test three oracles and refine accordingly.

**Use the following table:**

| **Test ID** | **Test Oracle**                                                                                                | **Pass/Fail** | **Notes / Refinement Made** | **Transcript Link** |
| ----------- | -------------------------------------------------------------------------------------------------------------- | ------------- | --------------------------- | ------------------- |
| **T1**      | Example: The summary must mention all main sections of the paper (Introduction, Methods, Results, Discussion). |               |                             |                     |
| **T2**      |                                                                                                                |               |                             |                     |
| **T3**      |                                                                                                                |               |                             |                     |

**Steps:**

1. Write your first failing test (T1) and record it in the table below. Begin with a minimal prompt:
   
   > Summarize the paper "Attention Is All You Need".

2. Run this prompt and record Fail/Pass in the table for T1. Save the transcript link.

3. Revise the prompt to pass the failed test. Rerun it, then record the new Pass/Fail result in the same row. If it passes, save another transcript link. This same link (and output) can serve as the "fail test" for your next oracle iteration.

4. Next, design another failing test (T2) and follow the same procedure. 
   **NOTE**: If the test unexpectedly passes on the first trial, it may be due to _model memory leakage_ from earlier runs of the paper summarizer prompt. Record it as a pass, but refine your prompt regardless. If repeated failures occur even after reasonable efforts at refinement, note this in the table — no penalty will apply.

5. Write a 25-word reflection explaining how writing tests first influenced your prompt design.

**Deliverables:**

- Completed test table with Pass/Fail results
- Refined prompt versions (v1 → v3)
- 25-word reflection

### Set 3: Modular Prompting

#### Task 3.1: Designing a Modular Summarizer

**Objective:**  Use modular design to generate summaries for two different audiences — experts and laypersons.

**Background:**  A research team wants a summarizer that produces both expert-level and general-audience summaries. You will design a modular summarizer with two linked modules.

**Modules summary:**

| **Module**         | **Description**                                                                                                                                                            | **Output**               |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| **A: Expert Lens** | Summarize one section (e.g., *Results*) in technical terms suitable for specialists. Focus on precision, terminology, and key findings.                                    | ~100-word expert summary |
| **B: Lay Lens**    | Takes the output of A as its input. Re-express the same section for non-experts in plain language, using analogies and simple explanations while keeping factual accuracy. | ~100-word lay summary    |

**Steps:**

1. Choose one section of *Attention Is All You Need* (e.g., Results or Model Architecture).  
2. Write two separate prompts (Modules A&B) following the table above.  The output of Module A serves as input in Module B.
3. Run each module in Microsoft Copilot (guest mode).  
4. Save transcript links for each module.  
5. If you haven’t named the paper explicitly in your Module B prompt, rewrite your prompt again telling the LLM that this summary is from the "Attention is All You Need" research paper, and ask it to provide the layperson summary. Test the prompt, do you notice any differences to your first trial? (I.e., does providing the LLM with more information about the source of the summary change its answer?) If your original prompt named the paper, note that instead.
6. Write a 50-word reflection addressing the following:  
- How modularizing by audience improved tone, clarity, or control.  
- Which module most improved reliability or readability.

**Deliverables:**

- Two prompts (A&B)  
- Two transcript links  
- Answer to step 5, 3-4 sentences
- 50-word reflection  
  
  

## Group Reflection

Write a 100-word reflection covering:

- How specification design, TDD, and modularity work together.  
- How modularity improves clarity, reliability, and scalability for complex summarization systems.  
- Which skill or concept was most challenging and why.  

**Submission template:**

```
# Week 10 Group Reflection

## Group Members
- [List all group members’ names]

---

## Set 1: Specification Design for a Multi-Section Summarizer

### Task 1.1: Designing Summarization Specifications

| **Category** | **Description** |
|---------------|-----------------|
| **Inputs** |  |
| **Outputs** |  |
| **Constraints** |  |

**Notes:**  
[Insert any additional notes or assumptions made while defining the specification.]

**Deliverable:**  
Specification table completed above.

---

## Set 2: Test-Driven Development (TDD) for Summarization

### Task 2.1: Writing Tests Before Prompts

| **Test ID** | **Test Oracle (Expected Rule)** | **Pass/Fail** | **Notes / Refinement Made** | **Transcript Link** |
|--------------|---------------------------------|----------------|------------------------------|----------------------|
| **T1** | The summary must mention all main sections of the paper (Introduction, Methods, Results, Discussion). |  |  |  |
| **T2** | The summary must stay under 200 words. |  |  |  |
| **T3** | The summary must avoid hallucinated content (no unsupported claims). |  |  |  |

**Refined Prompts:**  
[v1: …]  
[v2: …]  
[v3: …]

**25-word Reflection:**  
[]

---

## Set 3: Modular Prompting

### Task 3.1: Designing and Testing a Perspective-Based Modular Summarizer


**Module A**  
[Insert prompt text]  
**Transcript Link:** [Insert link]

**Module B**  
[Insert prompt text]  
**Transcript Link:** [Insert link]

**Answer to step 5**
[insert answer]

**50-word Reflection:**  


```

**Deliverables**: Markdown file (`group#_week10_reflection.md`) with all task outputs, transcript links, and 100-word reflection.
