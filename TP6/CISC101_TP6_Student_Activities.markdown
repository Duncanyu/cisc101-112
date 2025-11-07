# CISC 101: Week 9 Tutorial - Travel Planner: Structured Outputs and Modular Prompts

Welcome to the Week 9 tutorial for CISC 101. In this session, you will work to understand data structures and create modular prompt systems for the *Travel Planner* application. Open Microsoft Copilot in guest mode before starting.



## Tutorial Structure (1.5 hours)

- **First 10 minutes**: Instructor reviews structured outputs and modular prompts.
- **Next 60 minutes**: Complete group activities in two sets.
- **Following 10 minutes**: Write a group reflection in Markdown.
- **Final 10 minutes**: Q&A with instructor.

## Activities (60 minutes)

The activities are divided into two sets: Set 1 focuses on output formats, Set 2 on modular prompt systems.

### Set 1: Mastering Structured Output Formats

#### Task 1.1:  Output Selection for Prompts

**Objective**: Suggest the best output format for three different prompts and justify your choices.

**Steps**:

1. Consider the following three prompts:

2. * “Plan a 3-day zero-budget eco-tour of Iceland using hitchhiking and wild camping, with activities mapped to GPS coordinates.”
   * “Generate a 2-week multi-country luxury cruise itinerary with full daily cost breakdown and cabin service details.”
   * “Plan a surprise weekend getaway where each activity is revealed one hour before it starts.”
   
   For each prompt, choose between Markdown list, table, and JSON.

3. Write 1-2 sentences per case explaining why the format best fits the scenario. Compile your choices in the table below.
   
   ```
   | Prompt | Chosen Format | Justification |
   |--------|---------------|---------------|
   | Eco-tour Iceland | | |
   | Luxury Cruise | | |
   | Surprise Getaway | | |
   ```

4. Save table.

**Deliverables**:

- Format selection table

### Set 2: Modular Prompt Systems

#### Task 2.1: Modularizing Prompts

**Objective**: Break the Travel Planner into modular prompts.

**Background:** A travel agency is upgrading their AI-powered Travel Planner so that itineraries can be quickly adapted for any new city a client chooses. The current prompt is one large block that must be rewritten every time the destination changes. To fix this, you will use modular prompting: breaking the job into smaller, structured steps where each module has a single purpose and passes its output forward. This approach makes the system easier to update, reuse, and format for clients. Follow the steps below to modularize the prompt.

**Steps**:

1. Run Module 1 provided below. Replace the variable placeholders with your own choices. 

> You are Module 1 (Setup) for a Travel Planner application. Your task: Create a trip plan setup in VALID JSON with exactly these keys:- city: "[city]- days: [number of days]- theme: [theme as short string]. Provide your output in JSON.

2. Copy and save the JSON output. You will paste it into Module 2.

3. For Module 2, write a prompt that:
   
   * Uses the JSON data structure you defined in Module 1 as the starting input.
   
   * Generates 3 morning options and 3 afternoon options for each day
   
   * Outputs a Markdown table with columns: 
     Day | Morning Options | Afternoon Options
   
   * Each cell lists bullet points
   
   * No extra commentary outside the table

4. Test the prompt, and save the output.

5. Choose one morning and one afternoon option per day (Assume the client selected them.)

6. For Module 3, write a prompt that:
   
   * Includes the Module 2 table, and clearly mark which options you (or the client) selected. (Alternatively, you can only include the selected options.)
   
   * Uses only the selected activities from Module 2
   
   * Outputs a Markdown table with columns: Day | Morning | Afternoon | Insider Tip
   
   * Adds one short and helpful travel tip per day
   
   * No commentary outside the table

7. Run the Module 3 prompt and save the output.
   
   

## Group Assignment

**Objective**: Compile work and write a 100-word reflection on modular systems.

**Steps**:

1. Combine outputs into one Markdown file using the template below.
2. Write a 100-word reflection addressing: "What did you learn about data structures and modular prompt design?"

**Submission Template**:

```
# Week 9 Group Reflection

## Group Members
- [List all group members’ names]

## Set 1: Mastering Strcutured Output Formats

### Task 1.1: Output Selection for Prompts
**Format Selection Table**:
| Prompt | Chosen Format | Justification |
|--------|---------------|---------------|
| Eco-tour Iceland | | |
| Luxury Cruise | | |
| Surprise Getaway | | |

## Set 2: Modular Prompt Systems

### Task 2.1: Modularizing Prompts 
**Prompts**:
[Insert Module 1 output]

[Insert Module 2 prompt]
[Insert transcript link]

[Insert Module 3 prompt]
[Insert transcript link]

## Reflection
[Insert 100-word reflection]
```

**Deliverables**: Markdown file (`group#_week9_reflection.md`) with all task outputs, transcript links, and 100-word reflection.
