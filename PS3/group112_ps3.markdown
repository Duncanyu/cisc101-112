# Names
Duncan Yu, Brian Xu, Noah Arega

# Task 1.1
```
You are an expert prompt engineer and technical writer. Generate a complete “Research Paper Summarizer” prompt project as Markdown files.

CRITICAL RULE: You must follow and explicitly implement the PS2 Summarizer Specification below. Do not invent requirements that contradict it.

============================================================
PS2 SUMMARIZER SPECIFICATION (VERBATIM FROM PS2)

| Category    | Description |
|------------|-------------|
| Inputs     | - Full paper text already split into labeled sections in original order (Abstract, Introduction, Methods, results, Discussion). <br> - Target audience description ("first year undergrad biology student") and purpose of summary (“exam review” “literature review”). <br> - Maximum word count per section summary and for the final combined summary (120 to 150 words per section and 400 - 500 words overall). |
| Outputs    | - One concise summary per section each clearly labeled with the original section title and within the specified word range (120 - 150 words). <br> - A unified overall summary that integrates the section summaries into a coherent narrative within its entire word limit ( 400 to 500 words). <br> - Optional bullet list of 3 – 5 key contributions/claims of the paper written in appropriate language. |
| Constraints| - No invented/halluycinated facts: every claim in the summaries must be directly supported by the source text. no external knowledge added. <br> - Consistent use of terminology across all section summaries and the unified summary (always “working memory,” not switching to “short-term memory” unless the paper does). <br> - Neutral, academic tone meaning no personal opinions, and no direct quotes longer than one sentence. <br> - Preserve section order of the original paper in the output (section summaries appear in the same sequence as the source). |

Notes:
The summarizer assumes sections are already labeled and may skip low information content such as references, and must stay within word limits without inventing any facts
============================================================

PROJECT GOAL (PS3 REQUIREMENTS)
Generate:
1) A full System Prompt
2) A Multi-Module Internal Reference Framework (like Travel Planner style: clear modules, explicit sequencing, responsibilities)
3) Two additional student-created modules (you choose)
4) A README explaining how everything works together

DELIVERABLE FORMAT (MANDATORY)
Return your answer as SEPARATE Markdown code blocks, one per file, each beginning with the file path as a heading inside the code block, exactly like:

'''md
# /system_prompt.md
...file contents...
'''

FILES YOU MUST OUTPUT
- /system_prompt.md
- /modules/01_intake_setup.md
- /modules/02_section_loop.md
- /modules/03_guardrails.md
- /modules/04_rendering_refinement.md
- /modules/05_<student_module_name>.md
- /modules/06_<student_module_name>.md
- /README.md

/system_prompt.md must include:
- greeting and tone rules
- required user inputs (paper, section list, audience)
- boundaries (no hallucinating sections, no inventing citations)
- required output sections such as:
  - Paper Summary
  - Section-by-Section Table
  - Expert Summary + Lay Summary
  - Mini-Glossary
  - Checks & Warnings

The modules must include at least:
- Module 1: Intake & Setup (normalize sections, detect missing/short sections)
- Module 2: Section Loop (for each section → summarize + check constraints)
- Module 3: Guardrails (missing/empty sections, <50-word sections, hallucination mitigation, long-paper chunking)
- Module 4: Rendering & Refinement (final assembly, formatting consistency, expert/lay variants)

EACH module file must include:
- Purpose
- Inputs
- Outputs
- Numbered step-by-step logic
- Failure modes + standardized warning messages

For the two student-created modules:
- choose two helpful extensions (examples: citation/evidence support mapping, equation explainer, key contributions finder, limitations finder)
- keep them strictly grounded in provided paper text
- define clear I/O and how they plug into the overall flow

FINAL RULES
- Output ONLY the required files listed above.
- Do NOT include extra commentary outside the file code blocks.
- Keep formatting clean Markdown.
END.
```

# Task 1.2
**Transcript Link:** [https://copilot.microsoft.com/shares/dFF3y9zDrmsD7o2HmtaG2]
**Screenshot:**
![alt text](image.png)

**Verification Paragraph:**
I verified that the generated research paper summarizer prompt project is complete and matches my ps2 summarizer specification and ps3 requirements. The output includes /system_prompt.md, modules /modules/01_intake_setup.md through /modules/06_limitations_finder.md and /README.md. The system prompt asks for the required ps2 inputs, meaning labeled paper sections, audience, purpose and word limits. It enforces the ps2 constraints, meaning no hallucinated or invented facts, no external knowledge, consistent terminology, neutral academic tone, no direct quotes longer than one sentence and preserving section order. It also defines the required output structure, meaning paper summary, section by section table, expert summary and lay summary, mini glossary and checks and warnings. Each module includes a purpose, inputs, outputs, numbered step by step logic and standardized warning messages for missing or short sections, word count violations, terminology issues and unsupported claims. The two student created modules add ps2 compatible optional outputs by extracting 3 to 5 key contributions and identifying explicit limitations, both grounded in the provided paper text. Overall, the modular pipeline supports consistent and structured summaries while maintaining strict grounding and word limit compliance.

**Text-based flowchart:**
```
Start
  |
  v
Module 01 Intake and Setup
  Input paper sections, audience, purpose, word limits
  Normalize section labels
  Check missing sections and short sections
  Output metadata report and normalized section list
  |
  v
Module 02 Section Loop
  For each section in source order
    Summarize the section within the per section word limit
    Check terminology consistency
    Save labeled section summary
  |
  v
Module 03 Guardrails
  Check each summary is supported by the source section text
  Flag missing sections and empty sections
  If paper is long, segment text for processing
  Output validated summaries plus warning log
  |
  v
Module 04 Rendering and Refinement
  Combine section summaries into unified overall summary within overall word limit
  Format section by section table
  Generate expert summary and lay summary
  Build mini glossary from paper terms
  Append checks and warnings
  |
  v
Module 05 Key Contributions Finder
  Extract 3 to 5 supported contributions or claims
  Output contribution list or warning if insufficient support
  |
  v
Module 06 Limitations Finder
  Extract 2 to 4 explicit limitations or output notice if none
  |
  v
Final Response
  Paper Summary
  Section by Section Table
  Expert Summary and Lay Summary
  Mini Glossary
  Checks and Warnings
  Optional Contributions and Limitations
End
```

# Task 2.1
**Github Repo:** [https://github.com/Duncanyu/CISC101-Group112-PaperSummarizer]

# Task 3.1
```
# /modules/02_section_loop.md

## Change Log
2025-12-05 Added summary_level input and conditional output formats for short and detailed modes

## Module 02: Section Loop

### Purpose
Iteratively summarize each section in source order while enforcing constraints, terminology consistency and required formatting based on summary_level.

### Inputs
- Normalized section list.
- Paper sections text keyed by section label.
- Word count limits.
- Audience and purpose metadata.
- summary_level with allowed values short or detailed.

### Outputs
- Section summaries stored with their original section labels.
- A terminology consistency report for all sections.
- A warning log for per section issues.

### Step-by-Step Logic
1. Set summary_level.
   - If summary_level is missing, set summary_level to detailed.
2. For each section in normalized section list order:
   1. Load the section text for that section label.
   2. If section text is missing or empty, do not summarize.
      - Emit the standardized warning described in Module 03 and continue to the next section.
   3. Extract the main claims, methods, results or conclusions present in the section text.
   4. Produce the section output based on summary_level:
      1. If summary_level is short:
         - Write a 1 to 2 sentence summary that covers the core point of the section.
      2. If summary_level is detailed:
         - Write one short paragraph summary within the per section word limit.
         - Then add a bullet list with 3 to 5 key points grounded in the section text.
   5. Ensure terminology matches the source text and remains consistent with prior sections.
   6. Apply a neutral academic tone and do not include direct quotes longer than one sentence.
   7. Store the section output using the original section label.
3. After all sections are processed, produce a terminology consistency report across section outputs.

### Failure Modes + Standardized Warning Messages
- Summary too short in detailed mode → `WARNING: Section [X] summary too short.`
- Summary too long in detailed mode → `WARNING: Section [X] summary too long.`
- Terminology mismatch → `WARNING: Inconsistent terminology in section [X].`
- Invalid summary_level → `WARNING: Invalid summary_level. Using detailed mode.`
```

```
# /modules/03_guardrails.md

## Change Log
2025-12-05 Added evidence_mode strict option and standardized warnings for missing, empty and too short sections

## Module 03: Guardrails

### Purpose
Prevent hallucinations, handle missing or empty sections, enforce grounding and apply standardized warnings. Support strict evidence behavior using evidence_mode.

### Inputs
- Paper sections text keyed by section label.
- Section outputs produced by Module 02.
- Metadata report from Module 01.
- evidence_mode with allowed values strict or standard.

### Outputs
- Validated section outputs.
- Warning log with standardized messages.

### Step-by-Step Logic
1. Set evidence_mode.
   - If evidence_mode is missing, set evidence_mode to standard.
2. Standardized section availability checks for each section label in the normalized section list:
   1. If the section label does not exist in the provided paper sections text, emit missing section warning.
   2. If the section text exists but is empty after trimming, emit empty section warning.
   3. If the section text has fewer than 50 words, emit too short section warning.
3. Grounding and hallucination checks for each produced section output:
   1. Compare each claim, method description, result and conclusion in the section output to the corresponding section text.
   2. If evidence_mode is strict:
      - Remove or rewrite any statement that is not directly supported by the section text.
      - If the section text does not contain enough information to support a meaningful summary, emit the strict evidence insufficiency warning for that section.
   3. If evidence_mode is standard:
      - Allow paraphrase, but do not allow new facts not present in the section text.
   4. If unsupported content remains, emit the unsupported claim warning.
4. Long paper handling
   1. If a section text is too long to process in one pass, segment it into chunks.
   2. Validate that any claims in the output are supported by at least one chunk.
   3. Emit a notice that chunking was used.
5. Compile all warnings into the warning log and pass validated outputs forward.

### Failure Modes + Standardized Warning Messages
- Missing section → `WARNING: Section [X] missing from input.`
- Empty section → `WARNING: Section [X] has no content.`
- Section too short → `WARNING: Section [X] too short (<50 words). Summary may be incomplete.`
- Unsupported claim → `WARNING: Unsupported claim in section [X].`
- Strict evidence insufficient information → `WARNING: Not enough information in section [X] to summarize in strict evidence mode.`
- Chunking required → `NOTICE: Section [X] segmented for processing.`
- Invalid evidence_mode → `WARNING: Invalid evidence_mode. Using standard mode.`
```

**PR Creation Screenshot:** (PLEASE IGNORE THE ALREADY CREATED UPDATE PULL REQUEST, I FORGOT TO TAKE A SCREENSHOT THE FIRST TIME)
![alt text](image-1.png)

**PR Compared Changes Screenshot:**
![alt text](image-2.png)