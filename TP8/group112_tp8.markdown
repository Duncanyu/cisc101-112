# Week 11 Group Reflection

## Group Members
- Brian Xu, Duncan Yu

## Set 1: Microsoft Copilot-Assisted Prompt Review

### Task 1.1: Microsoft Copilot Review of GitHub Repository Prompts
**Transcript Link**:
[Copilot Transcript](https://copilot.microsoft.com/shares/nMjfsVTu4b4V1LuVX8FNi)

**Name of selected module**:
02_plan_builder.md

**100-word summary of improvements**:
We decided to apply the suggestions that clarify how module 2 picks activities and structures every day. We added very simple proximity rules, some time blocks (morning, afternoon....), and activity metadata such as duration, theme, and cost. These changes imrpoved the clarity by making the temrs like "enar ldoging" and "different theme" less hazy. They improved the correctness by reflecting the user's pace and also refrained from skipping meals. Finally, they also improve reliability by also giving defaults when the lodging, budget and time of year is unknown. This helps module 2 generate more realistic plans before module 3 is applied.\

**Updated module**:
Updated module 02_plan_builder.md:
> Change log: clarified how Module 2 selects activities. I added simple proximity rules, time blocks, pace-based duration, and default assumptions for missing info.

### **Module 2 — Plan Builder (Options → Days)**

Create a short list of candidate activities (e.g., attractions, restaurants, parks).  
Each activity must include minimal metadata:  
- **Duration** (short 1–2h, medium 2–3h, long 3–4h)  
- **Theme** (culture, nature, food, shopping, wellness, etc.)  
- **Cost band** ($ low, $$ mid, $$$ high)  
- **Distance band** (near ≤1 km / 15 min walk, moderate ≤3 km / 20 min transit)

Use basic time blocks to structure the day:  
- **Morning (09:00–12:00)**  
- **Midday (12:00–15:00)**  
- **Afternoon (15:00–18:00)**  
- **Evening (18:00–21:30)**

Reflect user pace when selecting activities:  
- **Relaxed:** 4–5h of activities plus meals/rest  
- **Balanced:** 6–7h of activities plus meals  
- **Fast:** 8–9h of activities plus meals/transit

Use a simple loop to build days:

for each day:  
- **Morning:** pick an activity near lodging (or city center if lodging is unknown).  
- **Midday:** pick an activity close by (near or moderate distance from morning).  
- **Afternoon:** pick an activity with a different theme; allow moderate transit.  
- **Evening:** always include a dinner option matching budget/diet; if adding an event, place dinner before or after within the evening block.

Default assumptions:  
- If lodging is unknown → anchor morning near the city center or main transit hub.  
- If budget is missing → default to mid-range ($$); if invalid or negative → clamp to low ($).  
- If time of year is unknown → include at least one indoor-capable option per day.

**Github link**:
https://github.com/Nightbear1/CISC101-Group112-TravelPlanner

## Reflection
Copilot's suggestions helped us notice how the vague terms in our module created confusion. It pointed out the unclear proximity rules, missing logic for meals and the lack of defaults which we overlooked because the plan still technically worked. Human judgement still mattered when deciding which suggestions belonged to Module 2 vs Module 3. We pruposefully rejected anything that crossed into guardrails to protect the other modules. This is related directly to versioning and modularity, as we treated module 2 as an isolated component, we created a branch for review, reviewed changes, then accepted the pr once the module maintained consistency and we can confirm it worked.

