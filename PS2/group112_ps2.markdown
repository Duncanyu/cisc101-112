# Week 10 Group Reflection

## Group Members
- Brain Xu, Duncan Yu

---

## Set 1: Specification Design for a Multi-Section Summarizer

### Task 1.1: Designing Summarization Specifications

| Prompt            | Chosen Format  | Justification                                                                                                                                                                                                         |
|-------------------|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Eco-tour Iceland  | Markdown list  | A Markdown list makes it easy to read a simple day-by-day set of activities, with bullets for stops, hitchhiking legs, and camping spots, while still allowing inline notes like GPS coordinates.                     |
| Luxury Cruise     | Table          | A table clearly organizes each day’s ports, activities, cabin service details, and the full daily cost breakdown in separate columns, so costs and options can be compared at a glance.                               |
| Surprise Getaway  | JSON           | JSON works well for a time-locked plan where each activity can be stored as an object with fields like time, location, and description, allowing a system to reveal only the next activity one hour before it starts. |

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