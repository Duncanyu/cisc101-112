**CISC 101 — Paper Summarizer Final Project Rubric (8 Marks Total)**
====================================================================



#### **Task 1.1 Meta-Prompt Requirements — 4 Marks Total**

_(1 mark each )_

| Required Element                              | Criteria                                                                                                                                                            | Breakdown               | Marks |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |:-----:|
| **Spec Design Included**                      | The meta-prompt explicitly includes/quotes all three PS2 spec components: inputs, outputs, constraints. (Must appear as text inside meta-prompt or appended block.) | Binary                  | **1** |
| **System Prompt Requirements Included**       | Meta-prompt instructs LLM to generate all required system prompt components: **greeting/tone, required inputs, boundaries, required output sections**.              | 0.25 for each component | **1** |
| **Module Architecture Requirements Included** | Meta-prompt instructs LLM to create all **four required modules** (Intake, Section Loop, Guardrails, Rendering).                                                    | 0.25 for each component | **1** |
| **Two Additional Student-Created Modules**    | Meta-prompt instructs LLM to generate at least **two clearly named new modules** (student-designed).                                                                | 0.5 for each component  | **1** |

#### Task 1.2 - Verification and flowchart

| Required Element           | Criteria                                                | Marks   |
| -------------------------- | ------------------------------------------------------- |:-------:|
| **Verification Paragraph** | Verification paragraph of system components is included | **0.5** |
| **Flowchart**              | High-level flowchart of the project is included.        | **0.5** |

#### 

#### **Task 2. GitHub Repository Structure — 0.5 Mark Total**

| Required Element         | Criteria                                                                                                                          | Marks    |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------- | -------- |
| **Correct GitHub Setup** | Public repo exists and contains a README, `/system_prompt.md` and a `/modules/` folder with all module files generated in Task 1. | **0.5*** |

#### **3. Module Updates (Task 3 Requirements) — 3 Marks Total**

_(1.5 marks per module — both required changes must be present for full marks)_

#### **3A. Module 02 — Section Loop Update (1.5 Marks)**

| Required Sub-Element               | Criteria                                                                               | Marks |
| ---------------------------------- | -------------------------------------------------------------------------------------- | ----- |
| **Summary Level Variable Added**   | `summary_level` variable clearly added to the module.                                  | 0.5   |
| **Conditional Logic Implemented**  | Conditional Logic for `short` vs `detailed` summaries appears inside the section loop. | 0.5   |
| **Detailed Mode Behavior Correct** | “Detailed” mode includes BOTH a paragraph and a bullet list.                           | 0.5   |

#### **3B. Module 03 — Guardrails Update (1 Marks)**

| Required Sub-Element                             | Criteria                                                                                                                                                                        | Marks |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----- |
| **Strict Evidence Mode Added**                   | A flag (e.g., `evidence_mode = "strict"`) is present **and** paired with Conditional Logic restricting summaries to text explicitly present in the paper if the flag is active. | 0.5   |
| **Missing/Short Section Warning Messages Added** | Conditional Logic for standardized warning text appears for missing, empty, or <50-word sections.                                                                               | 0.5   |


