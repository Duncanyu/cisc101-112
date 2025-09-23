# Week 3 Group Reflection

## Group Number

- 112

## Group Members Names

- Duncan Yu, Brian Xu

## Set 1: Decomposition and Variables

### Task 1.1: Text-Based Flowchart

**Flowchart**:
[Start] --> [Input: City=Paris, Duration=5, Budget=$750] --> [Select Activites] --> [1 museum] --> [1 restaurant] --> [1 park] --> [Retrieve Activities + Costs & Links] --> 

**Analysis**:
Utilizing the flowchart helps identify specific variables that need to be used in order to tailor this prompt to each individual person. Additionally, the benefit of creating more processes helps specifically narrow down steps Copilot makes, bringing it more accurate.

### Task 1.2: Role-Play Challenge

**Persona Chosen**:
**Accessibility Seeker**: Needs wheelchair-accessible or sensory-friendly activities.

**Decomposition**:
[Additional process one: Make sure that all activities are wheelchair accessible, including the following (Wheelchair ramp, accessible handrail, accessible door-opening button, etc)] --> [Additional process two: Identify any other positives that can be found through the previous processes (newly renovated infrastructure) through news sources and online research. State which activity locations have such benefits, and reweigh previously mentioned activities and outputs]-->[Additional process three: Revisit previously selected locations, and cross references with review from Yelp, google review, reddit etc on accessibility in these sites] --> [Additional Process Four: Locate if there is any other activities that are planned specifically for wheelchair-bound individuals, locate them, and slide them into the itinerary]-->[Additional Process Five: Identify if any locations and activities have disability benefits, such as discounts or special programs]-->[Process Six: Identify altitude of all locations, making sure that proper oxygen content is available in any location. If not available, then identify any services to rent oxygen cans.]

**Analysis**:
Utilizing the decomposition and the flowchart style previously mentioned, it instinctively becomes clear on which values stand important, and which values should be held above others. By including this decomposition instead of a simple statement such as "Take into account that traveler is a wheelchair", the prompt becomes tailored to the specific needs of each prompter.

### Task 1.3: Decomposition Error Prediction Challenge

**Predicted Errors**:
1. Over budget
2. No links to activities, could be activities that no longer exist
3. Activities that don't happen frequently timeline wise
4. Activities do not account for other factors (physical exertion, time) in a day.

**Predicted Errors**:
1. No specific links, specific locations or times
2. No account into budget
3. No self-checking of activities chosen
4. General plan not tailored to any person.

**Transcript Link**:
[\[Insert transcript link\]](https://copilot.microsoft.com/shares/LwebpYwjySDhpPHytx2Dx)

**Analysis**:
As previously mentioned, the lack of any detail and specific decomposition turns the copilot prompt identified here into a general and extremely vague output. Only generalized information was given, and in return only generalized output, suited for most people was given in return.

### Task 1.4: Design a Prompt with Variables

**Variable-Based Prompt**:
  Plan a [amountofdays] itinerary for [city] for an [travelertraits] traveler. Include at least [FreqofLocation1] [Location1], [FreqofLocation2] [Location2], and [FreqofLocation3] [Location3] per day in bullet points with costs. Ensure total cost ≤ [totalbudget], no meal exceeds [individualmealcost] euros, all restaurants must serve [dietaryrestrictions] food, all activities must be open in [travelmonth], transportation should stay under [travelbudget] euros, and at least one evening must feature attending a[specificevent].

**Variables categorized list**:
Quantatiative: [amountofdays],[FreqofLocation1],[FreqofLocation2],[FreqofLocation3],[totalbudget],[individualmealcost],[travelmonth],[travelbudget]
Qualitative:[City],[travlertraits],[Location1],[Location2],[Location3],[dietaryrestrictions],[specificevent]

**Analysis**:
Replacing fixed values in the prompt with proper variables in the prompt allows for further flexibility, as the prompt can be reused for different travel itineraries. Not limited to that, there is also the benefit of being able to change any specific variables if any one variable changes during the course of the trip.

## Set 2: Basic Prompt Design and SE4AI Principles

### Task 2.1: Prompt Reverse Engineering Challenge

**Inferred Prompt**:
Create a 5 by 3 table, containing an itinerary for a day trip to Paris. THe table should have a Day column, a museum column, a restaurant column, park column, and total cost of day column. The cost of any activity should be listed next to its name in the table. The trip is two days long with a total budget of $80. Do not include anything other than what has explicitly been asked for.

**Transcript Link**:
https://copilot.microsoft.com/chats/XYJ4Mz1sZA9Scw5agw2YD

**Analysis**:
It ended up being quite easy to recreate the LLMs output, as the more information about the table given the closer the output was. The only issue that we had was that even after being explicitly told to only output the table, it still outputted an additional couple sentences, as well as showing the remaining budget.

### Task 2.2: Assumption Analysis and Decomposition Challenge

**Assumptions and Ambiguity**:
Copilot assumed the trip was 3 days.
Copilot assumed the tripgoer already had accommodations.
Copilot assumed that a budget wasn’t relevant.

**Revised Prompt**:
Create a travel itinerary for a 3 day solo trip to Paris, with a budget of $350. Each day should have 3 sections in the following order: morning, lunch, evening, and each of those should have a specific activity to perform at that time. Include accommodations. Account for and list the travel time to get from the location of one activity to another.

**Transcript Links**:
Initial Prompt: https://copilot.microsoft.com/chats/3XuoyQaLUJXteEYPAyALK
Revised Prompt: https://copilot.microsoft.com/chats/fRkMi5ifFuBtYqXiVWrSd

**Reflection**:
This task demonstrated to us how useless vague prompts are, and how without specificity the LLM is forced to make their own (usually wrong) assumptions.

## Reflection

Collectively, this week's tasks reinforced the importance of decomposition in breaking down complex problems into manageable steps. Task 1.1 introduced flowcharts as a tool of decomposition, and we used this tool on the Travel Planner, which allowed for the process to be broken down into manageable steps. Task 1.2 uses the same premise as 1.1, except with added constraints. Task 1.3 also tested our knowledge of decomposition, only this time in the context of understanding and identifying when it is executed poorly. Task 1.4 tested our application of decomposition by means of a prompt that we were required to break down into distinct variables. Task 2.1 tested our ability to decompose an output in order to infer the input prompt. 2.2 tested our ability to decompose an output to determine the assumptions, while demonstrating what happens if vague prompts are given to an LLM.

```

**Deliverables**: Markdown file (`group#_week3_reflection.md`) with all task outputs, transcript links, and 100-word reflection.

