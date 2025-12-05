# CISC 101: Week 10 Tutorial – Research Paper Summarizer: Project Integration

Welcome to the Week 10 tutorial for CISC 101. In this session, you will work in groups of 3 to integrate your work for the *Research Paper Summarizer* application.

Required Materials

* Access to Microsoft Copilot (open in guest mode)
* A text editor (e.g., Notepad, VS Code, Typedown) for Markdown files
* The “Attention Is All You Need” paper PDF [[1706.03762] Attention Is All You Need](https://arxiv.org/abs/1706.03762)
* Collaboration with your group members

## Tutorial Structure (1.5 hours)

* **First 10 minutes**: Instructor reviews core concepts.
* **Next 60 minutes**: Complete group activities.
* **Following 10 minutes**: Write and compile a 100-word group reflection.
* **Final 10 minutes**: Q&A with instructor.

**Background**: This final project combines everything you learned across Weeks 2–12: decomposition, conditionals, loops, CoT, hallucination mitigation, modular prompting, specification design, version control, and GitHub workflows.

### Set 1: Design the Summarizer System Prompt (Meta-Prompting + Spec Integration)

You will **write a meta-prompt** that instructs an LLM to generate a full **Research Paper Summarizer project**, including:

* A complete **System Prompt**

* An **Internal Reference Framework** with multiple modules (similar to the Travel Planner architecture)

* Clearly defined rules, workflows, constraints, and output formats

Before generating anything, _your job is to design the meta-prompt itself_.

#### **Task 1.1: Revisit Your Specification Design (PS2) and Incorporate It**

You must review your PS2 (Week 10) Summarizer Specification Table, which included inputs, outputs, and constraints for a multi-section summarizer.  Your meta-prompt must explicitly integrate your spec design in PS2. You are required to quote or restate your PS2 specification components inside your meta-prompt or attach them as a block at the bottom. This ensures your Summarizer system prompt is grounded in your earlier design work. In addition to your spec design, your meta-prompt must tell the LLM to generate:

###### **1. A full System Prompt**

This system prompt must include:

* Greeting rules and tone rules

* Required user inputs (paper, section list, audience)

* Boundaries (no hallucinating sections, no inventing citations)

* Required output sections such as:
  
  * **Paper Summary**
  
  * **Section-by-Section Table**
  
  * **Expert Summary + Lay Summary** (from Week 10 modularity)
  
  * **Mini-Glossary**
  
  * **Checks & Warnings** (e.g., missing sections, empty text)

###### **2. A Multi-Module Internal Architecture**

Your meta-prompt must tell the LLM to create at least these modules:

* **Module 1: Intake & Setup** (normalize sections, detect missing/short sections)

* **Module 2: Section Loop** (for each section → summarize, check constraints)

* **Module 3: Guardrails**
  
  * missing/empty sections
  
  * <50-word sections
  
  * hallucination mitigation
  
  * long-paper chunking (from PS2 context-window strategies)

* **Module 4: Rendering & Refinement**
  
  * final summary structure
  
  * consistent formatting
  
  * expert/lay variants

###### **3. Two Additional Student-Created Modules**

Examples: Citation Extractor, Equation Explainer, Key Contributions Summarizer, etc.

**Deliverables:**

- Meta-prompt text

#### **Task 1.2 Run the Meta-Prompt and Verify**

Run the meta-prompt in Copilot. You should now receive:

* A generated **system_prompt.md**

* A reference framework similar to Travel Planner

###### **Verification Requirement**

Write a **1-paragraph verification** confirming the generated system prompt satisfies:

* All PS2 specification design items

* All required module behaviors

* All safety rules (hallucination checks, missing-section logic)

* All formatting rules

* All modularity rules borrowed from Travel Planner

* All additional student-created module requirements

Once finished, you must create a text-based flowchart summarizing the high-level flow of your prompt. Be brief and include main steps only.

**Deliverables:**

- Screenshot from Copilot chat showing the meta prompt is run

- Verification paragraph

- Text-based flowchart.

#### Set 2: Create and upload your work to Github

#### **Task 2: Upload the Full Project to GitHub**

You will now mirror the Travel Planner GitHub workflow to upload your work. Follow the steps below.

1. **Create a public repository**:`CISC101-Group#-PaperSummarizer`

2. **Create and upload the project files:**
   
   * `/system_prompt.md`
   
   * `/modules/*` for all modules
      Please ensure you create the correct paths for the modules.
   
   * a README explaining your repo components.

**Deliverables:**

- Github repo public link.

#### Set 3: Making a Branch, Changing Code, and Merging

#### Task 3: Branching, pulling and merging

In this task, you’ll extend your Paper Summarizer to handle two new product requirements. You will update two modules in your `/modules` folder, do the work on a branch, open a pull request and merge it into `main`. Follow the steps below.

1. You must update **both** of these:`/modules/02_section_loop.md` and `/modules/03_guardrails.md`

2. Read and implement changes to reflect the requirements below for Module 2:
   
   > New Requirement A: Add “Summary Level” Modes (Module 02)
   >  The summarizer should support two summary levels for each section:
   > 
   > * `summary_level = "short"`
   >   
   >   * 1–2 sentence summary per section
   > 
   > * `summary_level = "detailed"`
   >   
   >   * A short paragraph **plus** a bullet list of 3–5 key points for each section
   > 
   > **You must:**
   > 
   > * Add a **variable** (e.g., `summary_level`) to the module’s logic.
   > 
   > * Add **conditional behavior** in the section loop:
   >   
   >   * If `summary_level = "short"` → generate only a compact summary.
   >   
   >   * If `summary_level = "detailed"` → generate summary + bullet list.
   > 
   > * Make sure the instructions are clearly written in `02_section_loop.md` in the same style as the existing loop logic.

3. Read and implement changes to reflect the requirements below for Module 3:

> New Requirement B: Strengthen Evidence & Hallucination Guardrails (Module 03)
> 
> The summarizer should more clearly respect the **“only use what’s in the paper”** rule and expose that behavior.
> 
> **You must add BOTH of these guardrails to `03_guardrails.md`:**
> 
> 1. **Strict Evidence Mode**: Introduce a **mode or flag** (e.g., `evidence_mode = "strict"`). When it is set to `"strict"`:
>    
>    * The summarizer should:
>      
>      * Only include claims, equations, and results that appear in the provided text.
>      
>      * If it cannot find enough information, it must say so explicitly (e.g., “The source text does not provide enough detail to summarize this section in strict evidence mode.”).
> 
> 2. **Section Warning Messages**
>    For sections that are:
>    
>    * missing / empty, or
>    
>    * too short (< 50 words)
>    
>    The module must instruct the system to output a **standardized warning**, such as:
> * “Section skipped: no usable text was provided.”
> 
> * “Section very short: summary may be incomplete.”
>   You decide the exact wording.

4. Implement both changes in a new branch. Do not forget to include a short **Change Log entry** at the top of each updated module describing what you changed. Create a pull request and merge once finished.

**Deliverables:**

- Updated Module 2 text

- Updated Module 3 text

- Screenshot from the "open pull request page" including the title and the message detailing the changes that were made. 

- Screenshot from the compared changes. To view this, scroll down on the open pull request page.

- Screenshot from 

## IMPORTANT:

All your work including your markdown file and the screenshots should be compiled in a zip file and uploaded to OnQ.
