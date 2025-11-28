# CISC 101: Week 12 Tutorial - Travel Planner: AI-Assisted Prompt Review and Iteration

Welcome to the Week 12 tutorial for CISC 101. In this session, you will work in groups of 3 to use Microsoft Copilot as a companion to review, test, and iterate your *Travel Planner* modular prompts from Week 11. 

## Required Materials

- Access to Microsoft Copilot (open in guest mode).
- A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files.
- GitHub account with a public `CISC101-TravelPlanner` repository (from Week 11).
- Collaboration with group members.

## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews Microsoft Copilot collaboration for prompt review/iteration and modular prompts/GitHub.
- **Next 60 minutes**: Complete group activities in three sets.
- **Following 10 minutes**: Write a group reflection in Markdown.
- **Final 10 minutes**: Q&A with instructor.

## Pre-Class Preparation

1. Ensure your group’s public `CISC101-TravelPlanner` repository (from Week 11) includes Week 11’s prompts (refer to TP7).
2. Verify all members can access the repository.

## Recap

Last week, you created modular prompt files and practiced Git branching and merging.  This week, we extend that workflow by integrating AI-based code/prompt review.  AI4SE treats the LLM as a partner who can critique prompt quality—checking clarity, correctness, and robustness.  You’ll combine AI critiques with a human peer review, apply improvements, and document your debugging process.

## Activities

### Set 1: Microsoft Copilot-Assisted Prompt Review

#### Task 1.1: Microsoft Copilot Review of GitHub Repository Prompts (20 minutes)

**Objective**: Use Microsoft Copilot to critique one of your existing Travel Planner modules.

**Steps**:

1. Choose one module from your `/modules` folder (e.g., `plan_builder.md`).

2. Copy the content of the module into Copilot (or another LLM tool) and issue this meta-prompt:
   
   > You are acting as a senior software engineer specialized in LLM prompt systems. Below is the complete context for an AI-based Travel Planner project.  It contains:
   > 
   > 1. The System Prompt (public behavior rules)  
   > 2. The Internal Reference Framework (the 4-module architecture)  
   > 3. The Module under review (*INSERT YOUR MODULE NAME HERE*)
   > 
   > Your role is to critique only the specified module (INSERT MODULE NAME AGAIN), ensuring that:
   > 
   > - The module remains consistent with the system prompt and reference framework.  
   > - No interference or edits are made to the other modules or system components.  
   > - All suggestions preserve the Travel Planner’s tone, workflow, and presentation rules.  
   > 
   > For your critique, focus on:
   > 
   > - Clarity – Are instructions unambiguous and coherent?  
   > - Correctness – Does it align with system and reference logic?  
   > - Robustness – Does it gracefully handle edge or invalid cases (e.g., missing data, negative budgets, weather)?  
   > 
   > Use **Chain-of-Thought reasoning** to justify *why* each improvement is needed.  Label your reasoning clearly as `"Justification:"` (no hidden reasoning steps). 
   
   **Note**: It is important to upload (or copy) the entire UPDATED Markdown files for the system prompt and the reference files in this prompt to ensure <u>any suggested fixes do not interfere or duplicate the functionalities of other parts of your code.</u>

3. Review the AI’s feedback and discuss what you agree is worth implementing.  Write a short 100-word summary describing:
   
   - What suggestions you chose to apply, and  
   - Why these changes improve the module.

4. In the same chat, instruct the LLM to revise **only based on your selected improvements**. 
      Example prompt:  
   
   > “Revise the module below to implement the following changes: [*paste summary*]. 
   > Keep structure consistent with the Travel Planner reference and system prompt.”

5. To implement and document the update, create a new branch in GitHub (e.g., `03_guardrails-debug-v2`). At the top of the module, add a short change log, then commit changes with a message such as:  “Refined Module 03 based on AI critique: added indoor backup and format check.”

6. If possible, test the revised prompt in Copilot or another LLM.  If you added edge cases, try to test the LLM by simulating the edge scenario. Once verified, open a pull request and merge your branch back to `main`.

**Deliverables**:

- Transcript link
- Name of selected module 
- 100-word summary of selected improvements
- Updated module text
- Public GitHub link to the updated module branch

## Group Reflection

Write a 100-word reflection addressing:

- What did the AI critique help you notice?
- How did human judgment shape your final decisions?
- How does this experience connect to versioning and modularity?

**Submission Template**:

```
# Week 11 Group Reflection

## Group Members
- [List all group members’ names]

## Set 1: Microsoft Copilot-Assisted Prompt Review

### Task 1.1: Microsoft Copilot Review of GitHub Repository Prompts
**Transcript Link**:
[Insert link]

**Name of selected module**:
[...]


**100-word summary of improvements**:
[...]

**Updated module**:
[...]

**Github link**:
[...]

## Reflection
[Insert 100-word reflection]
```

**Deliverables**: Markdown file (`group#_week12_reflection.md`) with all task outputs, transcript links, GitHub screenshots, and 100-word reflection, submitted via the course platform (e.g., Canvas).
