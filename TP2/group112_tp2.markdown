# Week 3 Group Reflection

## Group Number

- 112

## Group Members Names

- Duncan Yu, Brian Xu, Noah Arega

## Set 1: Decomposition and Variables

### Task 1.1: Text-Based Flowchart

**Flowchart**:
[Start] --> [Input: Destination City=Paris, Trip Length=5, Budget=$750] --> [Process: Fetch list of activities] --> [Process: Filter all activities by budget, hours, distance, until a list of possible activities is generated] --> [Process: Select 1 of each following category, for each day] --> [1 museum] --> [1 restaurant] --> [1 park] --> [Output: costs per activity, booking links, 5-day itinerary]

**Analysis**:
The flowchart showed hidden steps clearly. By clearly defining what the inputs, processes, and outputs are, dependencies are made very clear. Because of this, it helps prevent any possible miscommunication between budgeting, timing, and activities.

### Task 1.2: Role-Play Challenge

**Adventure Seeker**: Prioritizes thrilling and active experiences.

**Decomposition**:
[Decomposition component one: Add "number of active experience" to input]
[Decomposition component two: Add "Identify similar activies that are more outdoors, thrilling, and active]
[Decomposition component three: Add "distance to thrilling activities" as a component when searching for the best hotel]
[Decomposition component four: Add "Requirement of longer time to sleep at night" to processes, in order for compensate for additional physical exertion in the day]
[Decomposition component five: Add "Physical Extertion" as a component to consider when creating the travel plan, to ensure enjoyable experience all throughout.]
[Decomposition component six: Add "Map of city, hotel, and activities" to output, while highlighting any recommeneded walks\running paths in between said activities]

**Analysis**:
The Adventure seeker persona highighted the need for additonal decomposition compoennets, whether that be in input, processess or output, in order to better tailor the output for each individual. The importance of having a concise and clear identity is essential in providing the best possible end result given certain requirments.

### Task 1.3: Decomposition Error Prediction Challenge

**Predicted Errors**:
1. No budget included, so costs would likely be missing.  
2. No booking links or details for activities.  
3. Activities may overlap or ignore realistic scheduling.  
4. Itinerary too vague and generic, lacking personalization.  

**Detected Errors**:
1. No costs were included anywhere in the itinerary.  
2. No links, booking or travel were provided.  
3. The schedule ignored travel time, making some transitions unrealistic.  
4. The itinerary was descriptive but generic, with no personalization to traveler needs.  

**Transcript Link**:
[\[Copilot share link\]](https://copilot.microsoft.com/shares/4Wn9bxPCrYogxuFQukLwA)

**Analysis**:
The analysis that was very similar to the predicted errors, where the lack of any descriptive requirements created a very generlized output. This generalized output was of not much use, given the lack of costs, timelines, links, and incorrect timings that do not account of travel time. In short, the lack of explicit needs creates a vague and generalized output.

### Task 1.4: Design a Prompt with Variables

**Variable-Based Prompt**:
   Plan a [trip length] day itinerary for [travel city] for an [traveler description] traveler. Include at least [number of museums] museums, [number of resturants] restaurants, and [number of parks] parks per day in [output format] with costs. Ensure total cost ≤ [trip cost], no meal exceeds [individual meal cost] euros, all restaurants must serve [dietary restrictions] food, all activities must be open in [month], transportation should stay under [transportation cost] euros, and at least one evening must feature attending a local [specific event]

**Variables categorized list**:
Quantatiative: [trip length], [number of museums], [number of resturants], [number of parks], [trip cost], [individual meal cost], [month], [transporation cost]
Qualitative: [travel city], [traveler description], [output format], [dietary restrictions], [specific event]

**Analysis**:
By replacing fixed values with both quantitative and qualitative variables, the prompt becomes a lot more generalized, in short becoming able to be used multiple times, without having to change the general format of the prompt.

## Set 2: Basic Prompt Design and SE4AI Principles

### Task 2.1: Prompt Reverse Engineering Challenge

**Inferred Prompt**:
Create a 2-day itinerary for Paris under a budget. Present the results in a table with the columns: Day, Museum, Restaurant, Park, and Cost. Each museum and restaurant should list its price in parentheses. Parks should be listed as free. At the end of each row, include the total daily cost. Use realistic Paris locations for each category.

**Transcript Link**:
https://copilot.microsoft.com/shares/bQKMnio12oSQb4PkjnTD5

**Analysis**:
The inferred prompt successfully reproduced the table format with all columns correctly.

### Task 2.2: Assumption Analysis and Decomposition Challenge

**Assumptions and Ambiguity**:
1. Copilot assumed the trip was only 3 days, though no duration was specified.  
2. It assumed restaurant preferences and style without any budget or dietary constraints.  
3. Copilot assumed that the activities must be specific well-known landmarks, restaurants, or attractions in Paris, rather than generic activities.

**Revised Prompt**:
Create a 3-day Paris itinerary. Each day must list three activities in this order: a museum in the morning, a lunch restaurant with its price in euros, and an outdoor activity in the evening. All activities should be within 2 km of each other, and the total daily cost must stay under €150. Keep entries concise by giving names and costs only, with no added description.

**Transcript Links**:
Initial Prompt: https://copilot.microsoft.com/shares/41teig1wSmTY7QuoK2Biu  
Revised Prompt: https://copilot.microsoft.com/shares/57FMR54TE7KkkgAfSMRM2

**Reflection**:
Working throughg Set 2 showed us how computational thinking helps sharpen prompt design. Reverse engineering the prompt in Task 2.1 forced us to identify hidden rules in the output, like table structure and cost formatting, which shows the need for decomposition and breaking down problems into parts. In Task 2.2, the assumption analysis showed us how missing details (budget, distance, traveler type) in our prompts can lead to vague or biased ouputs. Revising the prompt allowed us to practice specifying constraints, ordering tasks, and controlling flow to avoid ambiguity. Together, these activities demonstrated to us that computational thinking is not just coding logic but also allows us to systematically shape language for predictable, accurate, and testable results.
