# Week 5 Group Reflection

## Group Members
- Duncan Yu, Brian Xu

## Set 1: Decomposition, Edge Cases and Loops
### Task 1.1: Decomposition with Variables
**Decomposition Flowchart**:
[Start] --> [Inputs: 1. attachment="/data/path_to_file.pdf", 2. metadata=[title, authors], 3. Section headings or important stuff extracged from the PDF] --> [Step 1: Ingestion - Load PDF, pass file to parsing tool/step] --> [Step 2: Parse PDF, using Tesseract OCR + MuPDF] --> [Step 3: Chunk & Embed (big files only), using detected headings, digestible for LLM] --> [Step 4: Summarize & Synthesize, pass to LLM, LLM reads chunks, summarize chunks, sends response] --> [Outputs: 1. Key points and summaries for each section, 2. Finaly summary paragraph for entire article, 3. Citations]

### Task 1.2: Conditional Flowchart for Edge Cases
**Flowchart**:
[Start] --> 
    [Inputs: sections list with section_title + section_text] --> 
    For [each section starting iwth the first, until the last] --> 
    do
        [Check if section text is missing or empty] -->
            If [yes] -->
                [Skip and write down: "Skipped: Missing/Empty Text"] -->
                [continue / go to next section]
            Else -->
                [Check if section text is < 50 words] -->
                    If [yes] -->
                        [Skip and write down: "Skipped: Too Few Words"] -->
                        [continue / go to next section]
                    Else --> 
                        [Summarize section: Identify the purpose and problem, Identify the main methods and formulas, Identify key results and evidence/examples, Write a one sentence summary/takeawy] -->
                        [Add summary to list]
    end for -->
    [Outputs: Markdown summaries + skip messages for all sections]

**Summarization Prompt**:
You are a summarization assistant.
Attached to this query is a PDF called "Attention Is All You Need"

[1] Go through each section from first to last.
[2] If a section is missing or empty, skip it and write “Skipped: Missing or Empty Text.”
[3] If a section has fewer than 50 words, skip it and write “Skipped: Too Few Words.”
[4] Otherwise, summarize the section by stating the purpose or problem, main methods or ideas, key results, and one-sentence takeaway.
[5] After all sections are checked, list the summarized sections, the skipped ones with reasons, and give counts for total, summarized, and skipped sections.

**Transcript Link**:
https://copilot.microsoft.com/shares/AD9X5v7yWUG9Z8RCRywWF

---

## Set 2: CoT and Few-Shot Prompting

### Task 2.1: Chain-of-Thought Summarizer Prompt
**Prompt**:
Task: Summarize the section called “Model Architecture" from the paper "Attention Is All You Need". Think step by step and show your reasoning before writing the summaries.

[1] Check if the text is empty or under 50 words. If so, write “Skip: section missing or too short.”
[2] Read the section carefully. Identify the main goal, the methods used, and any results or examples.
[3] Explain your reasoning in short lines that show how the ideas connect.
[4] Write a 50 word expert summary using technical language.
[5] Write a 50 word layperson sumary using everyday language.
[6] List five key terms from the section with one-line plain explanations as a mini glossary.

**Transcript Link**:
https://copilot.microsoft.com/shares/kCcwNYHuaYPFv7EYi2jYh

### Task 2.2: Few-Shot Prompt for Consistent Formatting
**Prompt**:
Use the examples below to learn the format and style of summaries that i want. Each section must have an expert summary, a layperson summary, and a mini glossary with five key terms. Follow the same style to summarize the Introduction, Background, and Results sections.

[Example 1] - Model Architecture
Expert Summary: The Transformer architecture replaces recurrence and convolution with stacked self-attention and feed-forward layers in an encoder-decoder framework. It employs multi-head attention for diverse representation learning and positional encoding to retain sequence order. This design enables parallelization, reduces path lengths for long-range dependencies, and improves computational efficiency in sequence transduction tasks.
Layperson Summary: The Transformer is a new kind of AI model that understands sequences like sentences without using older methods like loops or filters. Instead, it looks at all parts of a sentence at once using “attention.” This makes it faster and smarter at tasks like translating languages or understanding text.
Mini Glossary: encoder –> reads input, decoder –> produces output, attention –> focuses on important words, multi-head –> uses several attention layers, positional encoding – tracks word order.

Now summarize each new section using the same structure and tone.
Each summary should stay around 50 words for both expert and layperson versions.
Do not include extra commenatry.

**Transcript Link**:
https://copilot.microsoft.com/shares/64rXorhKf8MokSjtxwnzf

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