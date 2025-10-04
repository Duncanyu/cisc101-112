# CISC 101: Week 5 Tutorial - Research Paper Summarizer: Intensive I

Welcome to the Week 5 tutorial for CISC 101. In this session, you will work in groups of 3 to apply concepts from Weeks 2–4 to the *Research Paper Summarizer* application, using computational thinking (decomposition, abstraction, pattern recognition), variables, conditionals, loops, chain-of-thought (CoT), few-shot prompting, and context windows to summarize "Attention Is All You Need" (Vaswani et al., 2017). Open Microsoft Copilot in guest mode before starting.

## Required Materials

- Access to Microsoft Copilot (open in guest mode).
- A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files.
- The "Attention Is All You Need" paper PDF (download from https://arxiv.org/pdf/1706.03762).
- Collaboration with group members.

## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews Weeks 2–4 concepts: computational thinking, variables, conditionals, loops, CoT, few-shot prompting, context windows, hallucination mitigation.
- **Next 60 minutes**: Complete group activities in three sets.
- **Final 10 minutes**: Q&A with instructor.

## Activities (60 minutes)

### Set 1: Decomposition, Edge Cases and Loops

#### Task 1.1: Basic Decomposition  (10 minutes)

**Objective**: Apply decomposition with variables for summarizing sections.

**Steps**:

1. Decompose the task: "Summarize the paper 'Attention Is All You Need'." Be as specific with your processes. Follow the usual format:
   
   - **Inputs**: Paper title, paper text, etc.
   
   - **Process**: Get all sections, extract key points per section, etc.
   
   - **Output**: Section names, etc. 
     Each item in the list must have at least **distinct 3 components**. Use the following flowchart template to create your text-based flowchart:
     
     ```
     [Start] --> [Inputs: ...] --> [Step 1: ...] --> [Step 2: ...] --> [Outputs: ...]
     ```

**Deliverables**:

- Decomposition flowchart

#### Task 1.2: Designing a Robust Paper Summarizer Prompt (10 minutes)

**Objective**: Design a text-based flowchart and a prompt with conditionals to handle edge cases and loops.

Background: You are currently interning at a research center that is developing an AI-powered summarization tool to help researchers quickly review long academic papers. The tool needs to:

* Go through every section of an uploaded paper and create a short, clear summary of each one.

* Handle problematic sections gracefully without crashing or producing meaningless output.

Your team lead has asked you to design **the logic and prompt** for this tool.

They have specifically asked you to include these two edge cases:

1. Missing Section: The parser could not extract text from a section (the section is empty).

2. Very Short Section: A section has fewer than 50 words and might not be worth summarizing.

The system should skip these sections while clearly noting in the output why they were skipped.

You must also include a for loop that goes through each section in the paper, summarizing them one by one and collecting the outputs.

To do this, you need to:

1. Anticipate and handle **edge cases** using **conditional logic**.

2. Use a **for loop** to iterate through paper sections and summarize them.

**Steps**:

1. Create a text-based flowchart (in Markdown) showing the control flow logic for the conditionals and the loops. Use the template below.
   
   ```
   [Start] --> 
   [Inputs: sections list with section_title + section_text] --> 
   [] --> 
   [] --> 
   [] -->
   ....
   [] -->
   [Outputs: Markdown summaries + skip messages for all sections]
   ```
   
   

2. Write a **summarization prompt** based on your flowchart.
3. Test your prompt with the Attention is All You Need paper. Save transcript link.

**Deliverables**:

- Decomposition flowchart

- Summarization prompt

- Transcript link

#### Task 1.3: (Optional) Looped Prompt Design (10 minutes)

**Objective**: Use nested loops for iterative section summaries. This is an optional task that features a nested loop and conditionals. You receive extra marks for solving this task.

**Background**: 
You are currently interning at a research center that is developing an AI-powered summarization tool to help researchers quickly review long academic papers. The tool needs to:

* Go through every section of an uploaded paper.

* Inside each section, go through every subsection **(if any)** and summarize it.

* Output all summaries using a clear and consistent format.

Your team lead has asked you to design the logic and prompt instructions for this tool.

They have specifically asked you to:

1. Use an outer for loop to go through each section in the paper.

2. Use an inner for loop to go through each subsection inside each section, if any. 

3. Summarize each subsection in 100–150 words and display them grouped under their section titles.

**Steps**:

1. Create a text-based flowchart (in Markdown) showing the control flow logic for the nested loops. Use the template below:
   
   ```
   [Start] -->
   [Inputs: sections list, each with section_title + subsections list] -->
   [] -->
   [] -->
   [] -->
   ... -->
   [] -->
   [Outputs: Markdown summaries grouped by section, with bullet points for each subsection]
   ```
   
   

2. Write a **summarization prompt** based on your flowchart.
3. Test your prompt with the Attention is All You Need paper. Save transcript.
4. Write a 25-word reflection on what you learned from this task. Did your design include an if-statement? If yes, did the if-statement instructed the model to display a message that a section has or doesn't have any subsections? How satisfied are you with the model's output?

**Deliverables**:

* Decomposition flowchart
* Prompt
* Transcript link

### Set 2: CoT, and Few-Shot Prompting

#### Task 2.1: Chain-of-Thought Summarizer Prompt  (10 minutes)

**Objective**: Design a **CoT prompt** that guides a research paper summarizer to produce transparent, structured reasoning and multiple outputs per section.

**Steps**:

1. Create a CoT prompt that includes the following: a) explicit CoT instruction, b) for a certain section, provide an 50-word expert summary and a 50-word layperson summary of the main points, d) for a certain section, provides a mini glossary. Include variables where appropriate.

2. Test your prompt with the "Model architecture" section and a 50-word limit. Save transcript link via shareable link.

**Deliverables**:

- Prompt
- Transcript link

#### Task 2.2: Few-Shot Prompt for Consistent Formatting (10 minutes)

**Objective**: Build a Few-Shot promp that uses your own outputs from Task 2.1 above as an example to teach the summarizer a consistent summarization style.

**Steps**:

1. Create a Few-Shot prompt that includes the expert and layperson summary the model provided in Task 2.1 as examples. The prompt should ask the model to provide similar formatting to summarize the Introduction, Background, and Results sections.

2. Test your prompt with the 3 sections, save transcript link via shareable link.

**Deliverables**:

- Prompt
- Transcript link

### Set 3: Iterative Refinement and Hallucination Mitigation

#### Task 3.1: Iterative Refinement with Context Windows (10 minutes)

**Objective**: Refine prompt design to work even when the research paper is longer than the model’s context limit.

**Steps**:

1. Refine your Task 2.2 Few-Shot prompt by adding the following context management strategies: a) instruct the model to summarize smaller chunks if the paper size exceeds the context window and b) introduce variables (e.g., [chunk1] and [chunk2]) to represent split parts of the paper.
2. Test, save transcript link via shareable link.

**Deliverables**:

- Refined prompt
- Transcript link

#### Task 3.2: Hallucination-Proofing Your Prompts (10 minutes)

**Objective**: Strengthen the prompts you wrote in earlier tasks by adding clear instructions that reduce hallucinations.  

**Steps**:  

1. Look back at the prompts you created in Set 1 and Set 2.  
2. Choose **two prompts** you wrote.  
3. Rewrite each one to include at least **one hallucination-mitigation instruction**, for example:  
   - *“Only include information explicitly present in the paper.”*  
4. Test one of your rewritten prompts with *Attention Is All You Need*. Save the transcript link.  
5. Write a 25-word reflection on how the output changed after adding hallucination-mitigation instructions.

**Deliverables**:  

- Two rewritten prompts with hallucination-mitigation rules.  
- Transcript link for one rewritten prompt.  
- 25-word reflection
  
  

## Group Assignment (5 minutes)

**Objective**: Compile work and write a 100-word reflection on prompt engineering.

**Steps**:

1. Combine outputs into one Markdown file using the template below.
2. Write a minimum of 100-word reflection. Reflect on everything you practiced in this tutorial. How did decomposition, variables, conditionals, loops, chain-of-thought, few-shot prompting, context windows, and hallucination mitigation interact to improve the **accuracy, clarity, and reliability** of LLM outputs? Which techniques did your group find most challenging to apply, and why? Which ones do you see as most useful in real-world applications, and how would you combine them when designing prompts for a professional or academic project?

**Submission Template**:

```
# Week 5 Group Reflection

## Group Members
- [List all group members’ names]

## Set 1: Decomposition, Edge Cases and Loops
### Task 1.1: Decomposition with Variables
**Decomposition Flowchart**:
[Insert text-based flowchart]

### Task 1.2: Conditional Flowchart for Edge Cases
**Flowchart**:
[Insert text-based flowchart with conditionals]

**Summarization Prompt**:
[Insert prompt with edge-case handling]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

### Task 1.3: Looped Prompt Design (Optional)
**Flowchart**:
[Insert text-based flowchart with nested loops]

**Prompt**:
[Insert summarization prompt with nested loops]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

**25-word Reflection**:
[Insert reflection]

---

## Set 2: CoT and Few-Shot Prompting

### Task 2.1: Chain-of-Thought Summarizer Prompt
**Prompt**:
[Insert CoT prompt for the "Model Architecture" section]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

### Task 2.2: Few-Shot Prompt for Consistent Formatting
**Prompt**:
[Insert Few-Shot prompt for Introduction, Background, and Results sections]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

---

## Set 3: Iterative Refinement and Hallucination Mitigation

### Task 3.1: Iterative Refinement with Context Windows
**Refined Prompt**:
[Insert refined Few-Shot prompt with context management strategies]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

### Task 3.2: Hallucination-Proofing Your Prompts
**Original Prompts**:
[Insert 2 original prompts from earlier tasks]

**Rewritten Prompts (with hallucination-mitigation rules)**:
[Insert 2 rewritten prompts]

**Transcript Link**:
[Insert Microsoft Copilot transcript link]

**25-word Reflection**:
[Insert reflection on how hallucination-proofing changed the outputs]

---

## Group Reflection (100 words)


```

**Deliverables**: Markdown file (`group#_week5_reflection.md`) with all task outputs, transcript links, and 100-word reflection.
