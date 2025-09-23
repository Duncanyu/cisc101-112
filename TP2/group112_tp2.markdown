# Week 3 Group Reflection

## Group Number

- 112

## Group Members Names

- Duncan Yu, Brian Xu

## Set 1: Decomposition and Variables

### Task 1.1: Text-Based Flowchart

**Flowchart**:
[Start] --> [Input: City=Paris, Days=5, Budget=$750] --> [Process: Fetch list of activities] --> [Process: Filter by budget, hours, distance] --> [Process: Select activities] --> [1 museum] --> [1 restaurant] --> [1 park per day] --> [Output: costs per activity] --> [Output: booking links] --> [Output: 5-day itinerary]

**Analysis**:
The flowchart showed hidden steps clearly, it organized inputs, processes, and outputs, making dependencies clear and preventing vague jumps between budgeting, timing, and activities.

### Task 1.2: Role-Play Challenge

**Persona Chosen**: Accessibility Seeker: Needs wheelchair-accessible or sensory-friendly activities.

**Decomposition**:
[Additional process one: Make sure that all activities are wheelchair accessible, including the following (Wheelchair ramp, accessible handrail, accessible door-opening button, etc)] --> [Additional process two: Identify any other positives that can be found through the previous processes (newly renovated infrastructure) through news sources and online research. State which activity locations have such benefits, and reweigh previously mentioned activities and outputs]-->[Additional process three: Revisit previously selected locations, and cross references with review from Yelp, google review, reddit etc on accessibility in these sites] --> [Additional Process Four: Locate if there is any other activities that are planned specifically for wheelchair-bound individuals, locate them, and slide them into the itinerary]-->[Additional Process Five: Identify if any locations and activities have disability benefits, such as discounts or special programs]-->[Process Six: Identify altitude of all locations, making sure that proper oxygen content is available in any location. If not available, then identify any services to rent oxygen cans.]

**Analysis**:
The Accessibility Seeker persona changed decomposition by requiring accessibility checks, reviews, discounts, and environmental considerations, forcing new inputs and processes beyond generic activity selection and budgeting.

### Task 1.3: Decomposition Error Prediction Challenge

**Predicted Errors**:
1. No budget included, so costs would likely be missing.  
2. No booking links or details for activities.  
3. Activities may overlap or ignore realistic scheduling.  
4. Itinerary too vague and generic, lacking personalization.  

**Detected Errors**:
1. No costs were included anywhere in the itinerary.  
2. No booking or ticket links were provided.  
3. The schedule ignored travel time, making some transitions unrealistic.  
4. The itinerary was descriptive but generic, with no personalization to traveler needs.  

**Transcript Link**:
[\[Copilot share link\]](https://copilot.microsoft.com/shares/nV3hTzsHYGavqPcumMt4n)

**Analysis**:
The predicted errors matched the test: no costs, missing links, unrealistic timing, and generic suggestions. Without explicit processes, vague prompts produced incomplete and repetitive results.

### Task 1.4: Design a Prompt with Variables

**Variable-Based Prompt**:
  Plan a [amountofdays] itinerary for [city] for an [travelertraits] traveler. Include at least [FreqofLocation1] [Location1], [FreqofLocation2] [Location2], and [FreqofLocation3] [Location3] per day in bullet points with costs. Ensure total cost ≤ [totalbudget], no meal exceeds [individualmealcost] euros, all restaurants must serve [dietaryrestrictions] food, all activities must be open in [travelmonth], transportation should stay under [travelbudget] euros, and at least one evening must feature attending a[specificevent].

**Variables categorized list**:
Quantatiative: [amountofdays],[FreqofLocation1],[FreqofLocation2],[FreqofLocation3],[totalbudget],[individualmealcost],[travelmonth],[travelbudget]
Qualitative:[City],[travlertraits],[Location1],[Location2],[Location3],[dietaryrestrictions],[specificevent]

**Analysis**:
Replacing fixed values with variables makes prompts adaptable, reusable, and easier to test. Variables expose hidden conditions, ensure clarity, and improve flexibility across different scenarios.

## Set 2: Basic Prompt Design and SE4AI Principles

### Task 2.1: Prompt Reverse Engineering Challenge

**Inferred Prompt**:
Create a Markdown table with five columns: Day, Museum, Restaurant, Park, and Cost. Fill in exactly two rows (Day 1 and Day 2). Each activity should list its cost in parentheses. The Cost column should show the total for that day. Do not include any text outside the table.

**Transcript Link**:
https://copilot.microsoft.com/shares/R8u8zrWHCc7fz1ofN3W2b

**Analysis**:
The inferred prompt successfully reproduced the table format with all columns. Costs appeared in parentheses, but output control (activities) within the table remained difficult.

### Task 2.2: Assumption Analysis and Decomposition Challenge

**Assumptions and Ambiguity**:
1. Copilot assumed the trip was only 3 days, though no duration was specified.  
2. It assumed restaurant preferences and style without any budget or dietary constraints.  
3. It interpreted “flows naturally” as visiting famous attractions in proximity, without defining distance, travel time, or traveler type.  

**Revised Prompt**:
Create a 3-day Paris itinerary with exactly three activities per day: morning, lunch, and evening. Each day must start with a cultural site, then lunch at a vegetarian-friendly restaurant under €40, and finish with an evening entertainment. Ensure activities are within 2 km of each other, include estimated travel times, and specify costs.  

**Transcript Links**:
Initial Prompt: https://copilot.microsoft.com/shares/41teig1wSmTY7QuoK2Biu  
Revised Prompt: https://copilot.microsoft.com/shares/wGb56mXELcWw7uCBwThDE

**Reflection**:
Collectively, this week’s tasks highlighted how decomposition and prompt design clarify hidden steps and assumptions. Task 1.1 showed flowcharts organize processes into visible inputs, actions, and outputs. Task 1.2 demonstrated how personas introduce unique constraints like accessibility, forcing richer decomposition. Task 1.3 revealed how vague prompts omit costs, links, and timing, showing decomposition prevents errors. Task 1.4 used variables to improve flexibility and reuse. Task 2.1 emphasized structure inference through reverse engineering outputs. Task 2.2 showed that constraints reduce vague assumptions and enabled realistic, testable outputs, especially when paired with detailed travel, cost, and distance considerations.
