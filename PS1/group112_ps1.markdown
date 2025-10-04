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
###Task 1.3:

1. 
   [Inputs: sections list, each with section_title + subsections list] -->
  [Start] --> 
    [Inputs: sections list with section_title + section_text] --> 
    For [each section starting with the first, until the last] --> 
    do
        For [each subsection starting with the first, until the last] -->
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
    [Outputs: Outputs: Markdown summaries grouped by section (100-150 words) + skip message of any message, with bullet points for each subsection]
   ```
   
   

2. 
Summarize the section called “Model Architecture" from the paper "Attention Is All You Need". Think step by step and show your reasoning before writing the summaries.
[1] Identify all section names, and for section named "Model Architecture" from the paper "Attention Is All You Need" attached to this inquiry, continue.
[2] For each subsection, do steps 3-8
[3] Check if the text is empty or under 50 words. If so, write “Skip: section missing or too short.”
[4] Read the section carefully. Identify the main goal, the methods used, and any results or examples.
[5] Explain your reasoning in short lines that show how the ideas connect.
[6] Write a 100 word expert summary using technical language.
[7] Write a 50 word layperson sumary using everyday language.
[8] List five key terms from the section with one-line plain explanations as a mini glossary.


3. Test your prompt with the Attention is All You Need paper. Save transcript.
https://copilot.microsoft.com/shares/LRXw2UTtRgF2B54Sr3yQu

4. Write a 25-word reflection on what you learned from this task. Did your design include an if-statement? If yes, did the if-statement instructed the model to display a message that a section has or doesn't have any subsections? How satisfied are you with the model's output?

Our design did include a few if-statements, in order to instruct the model on edge cases. For the model's output, it followed the proper guidelines properly, including both expertand layperson summaries.

---

## Set 2: CoT and Few-Shot Prompting

### Task 2.1: Chain-of-Thought Summarizer Prompt
**Prompt**:
Summarize the section called “Model Architecture" from the paper "Attention Is All You Need". Think step by step and show your reasoning before writing the summaries.

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
Use the examples below to learn the format and style of summaries that I want. Each section must have an expert summary, a layperson summary, and a mini glossary with five key terms. Follow the same style to summarize the Introduction, Background, and Results sections.

If the paper is too long to process at once, divide it into smaller parts labeled [chunk1], [chunk2], [chunk3], and so on. Summarize each chunk separately using the same structure, then merge all chunk summaries into one combined final output with consistent tone and one unified glossary.

[Example 1] – Model Architecture
Expert Summary: The Transformer architecture replaces recurrence and convolution with stacked self-attention and feed-forward layers in an encoder-decoder framework. It employs multi-head attention for diverse representation learning and positional encoding to retain sequence order. This design enables parallelization, reduces path lengths for long-range dependencies, and improves computational efficiency in sequence transduction tasks.
Layperson Summary: The Transformer is a new kind of AI model that understands sentences without using older methods like loops or filters. It looks at all parts of a sentence at once using “attention.” This makes it faster and smarter at tasks like translating languages or understanding text.
Mini Glossary: encoder –> reads input, decoder –> produces output, attention –> focuses on important words, multi-head –> uses several attention layers, positional encoding –> tracks word order.

Now summarize each [chunk] or section using the same structure and tone.
Each summary should stay around 50 words for both expert and layperson versions.
After all chunks are summarized, merge them into a single final summary with one unified glossary. Please DO NOT include ANY extra commentary.

**Transcript Link**:
https://copilot.microsoft.com/shares/6UuWphNsvg8UT5LpYqAFk

### Task 3.2: Hallucination-Proofing Your Prompts
**Original Prompts**:
Task 1.2 - summarization prompt:
You are a summarization assistant.
Attached to this query is a PDF called "Attention Is All You Need"

[1] Go through each section from first to last.
[2] If a section is missing or empty, skip it and write “Skipped: Missing or Empty Text.”
[3] If a section has fewer than 50 words, skip it and write “Skipped: Too Few Words.”
[4] Otherwise, summarize the section by stating the purpose or problem, main methods or ideas, key results, and one-sentence takeaway.
[5] After all sections are checked, list the summarized sections, the skipped ones with reasons, and give counts for total, summarized, and skipped sections.

Task 2.2 - Few shot prompt:

Use the examples below to learn the format and style of summaries that i want. Each section must have an expert summary, a layperson summary, and a mini glossary with five key terms. Follow the same style to summarize the Introduction, Background, and Results sections.

[Example 1] - Model Architecture
Expert Summary: The Transformer architecture replaces recurrence and convolution with stacked self-attention and feed-forward layers in an encoder-decoder framework. It employs multi-head attention for diverse representation learning and positional encoding to retain sequence order. This design enables parallelization, reduces path lengths for long-range dependencies, and improves computational efficiency in sequence transduction tasks.
Layperson Summary: The Transformer is a new kind of AI model that understands sequences like sentences without using older methods like loops or filters. Instead, it looks at all parts of a sentence at once using “attention.” This makes it faster and smarter at tasks like translating languages or understanding text.
Mini Glossary: encoder –> reads input, decoder –> produces output, attention –> focuses on important words, multi-head –> uses several attention layers, positional encoding – tracks word order.

Now summarize each new section using the same structure and tone.
Each summary should stay around 50 words for both expert and layperson versions.
Do not include extra commenatry.

**Rewritten Prompts (with hallucination-mitigation rules)**:
Task 1.2 - summarization prompt:
Attached is a PDF titled “Attention Is All You Need.”
This summarization task follows a controlled specification.

[1] Go through each section from first to last.
[2] If a section is missing or empty, write “Skipped: Missing or Empty Text.”
[3] If a section has fewer than 50 words, write “Skipped: Too Few Words.”
[4] Otherwise, summarize the section by stating the purpose or problem, main methods or ideas, key results, and a one-sentence takeaway.
[5] After all sections are checked, list summarized sections, skipped ones with reasons, and counts for total, summarized, and skipped sections.
[6] Hallucination Mitigation Rule: Please only included information explicitly present in the paper. Do not infer, guess, or use outside knowledge. If the content is unclear, write “Information not stated in paper.”
[7] Validation Rule: Verify each summary against the source text before moving to the next section.

Task 2.2 - Few shot prompt:

Use the examples below to learn the format and style of summaries.
Each section must have an expert summary, a layperson summary, and a mini glossary of five key terms. Follow the same style to summarize the Introduction, Background, and Results sections.

[Example 1] – Model Architecture
Expert Summary: The Transformer architecture replaces recurrence and convolution with stacked self-attention and feed-forward layers in an encoder-decoder framework. It employs multi-head attention for diverse representation learning and positional encoding to retain sequence order. This design enables parallelization, reduces path lengths for long range dependencies, and improves computational efficiency in sequence tasks.
Layperson Summary: The Transformer is a new AI model that reads sentences without using loops or filters. It looks at all words at once using “attention,” making it faster and smarter for translation and text tasks.
Mini Glossary: encoder –> reads input, decoder –> produces output, attention –> focuses on important words, multi-head –> uses several attention layers, positional encoding –> tracks word order.

Now summarize each new section using the same structure and tone.
Each summary should stay around 50 words for both expert and layperson versions.
Hallucination Mitigation Rule: Only use information explicitly found in the text. If the paper does not state something, write “Not mentioned in the paper.” Do not insert background knowledge or assumptions.
Spec Constraint: Input = paper text, Output = structured summaries and glossary, Constraint = accurate and verifiable content only.
Please, DO NOT include ANY extra commentary.

**Transcript Link**:
Task 1.2: https://copilot.microsoft.com/shares/khjzqQxCzn6WaCeHthgDx
Task 2.2: https://copilot.microsoft.com/shares/MkmhXWX5kFWiPHKYqbxfK

**25-word Reflection**:
Adding hallucination mitigation constraints made only slight differences. The summaries stayed focused and consistent, with similar length and tone, likely due to the small data size of the material and the clarity of the writing.

---

## Group Reflection (100 words)
Throughout this tutorial, we all learned how structured prompting techniques are used to make LLM outputs more accurate and reliable. Decomposition helped us clearly define each stage of summarization. VAriables, loops, and conditionals controlled what happens during repetition, and edge cases. CoT prompting and few shot prompting improved and displayed reasoning and format consistency. Managing context windows prevented overflow and ensured each chunk was unanimously processed, and the results were all coherent. Hallucination mitigation reinforced knowledge by having the LLM verify it's response with the source text. Our group found loops and conditional logic hardest to apply conceptually and fewshot prompting and hallucination controls were the most useful for giving us clear and verifiable results in real world academic contexts.
