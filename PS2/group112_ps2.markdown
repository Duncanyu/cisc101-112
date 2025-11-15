# Week 10 Group Reflection

## Group Members
- Brain Xu, Duncan Yu, NArega

---

## Set 1: Specification Design for a Multi-Section Summarizer

### Task 1.1: Designing Summarization Specifications

| Category    | Description |
|------------|-------------|
| Inputs     | - Full paper text already split into labeled sections in original order (Abstract, Introduction, Methods, results, Discussion). <br> - Target audience description ("first year undergrad biology student") and purpose of summary (“exam review” “literature review”). <br> - Maximum word count per section summary and for the final combined summary (120 to 150 words per section and 400 - 500 words overall). |
| Outputs    | - One concise summary per section each clearly labeled with the original section title and within the specified word range (120 - 150 words). <br> - A unified overall summary that integrates the section summaries into a coherent narrative within its entire word limit ( 400 to 500 words). <br> - Optional bullet list of 3 – 5 key contributions/claims of the paper written in appropriate language. |
| Constraints| - No invented/halluycinated facts: every claim in the summaries must be directly supported by the source text. no external knowledge added. <br> - Consistent use of terminology across all section summaries and the unified summary (always “working memory,” not switching to “short-term memory” unless the paper does). <br> - Neutral, academic tone meaning no personal opinions, and no direct quotes longer than one sentence. <br> - Preserve section order of the original paper in the output (section summaries appear in the same sequence as the source). |

**Notes:**  
The summarizer assumes sections are already labeled and may skip low information content such as references, and must stay within word limits without inventing any facts

**Deliverable:**  
Specification table completed above.

---

## Set 2: Test-Driven Development (TDD) for Summarization

### Task 2.1: Writing Tests Before Prompts

| Test ID | Test Oracle | Pass/Fail | Notes / Refinement Made | Transcript Link |
|--------|-------------|-----------|--------------------------|-----------------|
| T1 | The output must contain four clearly separated, labeled section summaries for **Introduction**, **Methods**, **Results**, and **Discussion**, in that order. | Fail on v1: Pass after v2. | Prompt v1 only asked for a single paragraph summary of the whole paper, so the model was not instructed to separate or label sections. Prompt v2 adds explicit instructions to summarize each section separately and label them with the section names in the correct order. | Run 1 (v1, fail): [https://copilot.microsoft.com/shares/rDCdofw75E4wK18DL1DhU] · Run 2 (v2, pass): [https://copilot.microsoft.com/shares/VpDNgyKXN3Ki2LvY2sAuk] |
| T2 | Each section summary must be between **80 and 120 words**, and no section may fall outside this range. | Pass on v2, but to make it better I explicitly metnioned in v3: Pass after v3. | Prompt v2 required section summaries but did not specify any word range, so some sections came out much shorter or longer than others. Prompt v3 adds an explicit 80 120 word constraint per section, so the model is instructed to keep all sections within a measurable range. | Run 1 (v2, ~pass): [https://copilot.microsoft.com/shares/VpDNgyKXN3Ki2LvY2sAuk] · Run 2 (v3, pass): [https://copilot.microsoft.com/shares/h7CZ1nfc1wjR1KnaTEu2g] |
| T3 | The final overall summary must clearly state that the key contribution is a **transformer architecture based on self-attention that replaces recurrent and convolutional networks for sequence modeling**. | Fail on earlier v2 draft: Pass after refined v3. | The version v2 asked for an overall summary but did not instruct the model to highlight the self attention based transformer or its replacement of RNNs/CNNs, so this contribution was often only implied or missing. The refined v3 explicitly requires the final overview to name and briefly explain this main contribution. | Run 1 (v2, fail): [https://copilot.microsoft.com/shares/VpDNgyKXN3Ki2LvY2sAuk] · Run 2 (refined v3, pass): [https://copilot.microsoft.com/shares/h7CZ1nfc1wjR1KnaTEu2g] |

**Refined Prompts:**  
*v1:* 
Summarize the paper “Attention Is All You Need” in one clear paragraph for an undergraduate student who has taken an introductory machine learning course.

*v2:*
Summarize the paper “Attention Is All You Need” for an undergraduate student who has taken an introductory machine learning course.

Produce four separate summaries, one for each of the following sections, in this exact order: Introduction, Methods, Results, and Discussion.

For each section, write a short, coherent paragraph that explains the main goal, ideas, or findings of that section in simple language.

Label each paragraph with the corresponding section name as a heading, and keep terminology consistent with the paper (for example, use the same technical terms that the authors use).

*v3:*
Summarize the paper “Attention Is All You Need” for an undergraduate student who has taken an introductory machine learning course.

1. Produce four separate summaries, one for each of the following sections, in this exact order: Introduction, Methods, Results, and Discussion.

2. Each section summary must be a single paragraph between 80 and 120 words. Explain the main ideas and findings of that section in clear, accessible language while keeping technical terminology consistent with the paper.

3. After the four section summaries, write a unified overall summary of 4 - 6 sentences that clearly states that the key contribution of the paper is a transformer architecture based on self attention that replaces recurrent and convolutional networks for sequence modeling.

4. Use only information from the paper itself, do not add external examples or claims, and avoid personal opinions.

**25-word Reflection:**  
Writing tests first exposed gaps in my prompts  so each revision deliberately added missing structure or constraints instead of vaguely hoping for truly better summaries.

---

## Set 3: Modular Prompting

### Task 3.1: Designing and Testing a Perspective-Based Modular Summarizer


**Module A**  
Summarize the Model Architecture section of the research paper “Attention Is All You Need” for an expert audience of machine learning researchers.

Write about 100 words.

Focus on the transformer architecture itself: self-attention mechanism, multi-head attention, positional encoding, encoder–decoder stack, and how these components replace recurrence and convolution.

Use technical terminology precisely and concisely, assume familiarity with sequence-to-sequence models, RNNs, and CNNs, and highlight only the most important design decisions and motivations, not basic background.
[Transcript Link](https://copilot.microsoft.com/shares/4q6F1oF1ojMkbzWWeJWhH)

**Module B**  
Here is a technical summary of the Model Architecture section of the research paper “Attention Is All You Need”:

[The Transformer architecture eliminates recurrence and convolution by relying entirely on self-attention to model global dependencies. Both encoder and decoder stacks comprise six identical layers, each combining multi-head self-attention with position-wise feed-forward networks, wrapped in residual connections and layer normalization. Multi-head attention projects queries, keys, and values into multiple subspaces, enabling richer contextual representations at constant path length. Decoder self-attention employs causal masking to preserve autoregressive generation, while encoder–decoder attention links source and target sequences. Positional encodings, implemented via sinusoidal functions, inject sequence order information absent in pure attention. This design achieves parallelization, reduced sequential operations, and superior long-range dependency modeling.]

Rewrite this as a ~100-word explanation for a general audience with no background in machine learning.

This explanation should still be clearly identified as describing the “Attention Is All You Need” model.

Keep all core facts accurate, replace jargon with everyday language, use one or two simple analogies, avoid equations and acronyms, and focus on what the model does and why it matters.
[Transcript Link](https://copilot.microsoft.com/shares/fQ7hLfGcZqJUtUB3BAnit)

**Answer to step 5**
My original prompt named the paper.

**50-word Reflection:**
Separating expert and lay lenses made me control tone more deliberately and avoid muddled middle ground explanations. The expert module improved reliability by enforcing precise terminology. The lay module most improved readability, since rewriting from a technical scaffold let me focus on clarity, analogies and gentle pacing for different reader groups.