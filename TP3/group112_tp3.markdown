# Week 4 Group Reflection

## Group Number

- 112

## Group Members Names

- Brian Xu, Duncan Yu

## Set 1: Conditionals and Loops

### Task 1.1: Flowchart Design with Conditionals

**Flowchart**:
   1. [Start] -->  
   2. [Input: City = Paris, Days = 1 day, Hotel Budget = $200, Museum Budget = $20, Time window = 10:00 AM – 02:00 PM] -->  
   3. [Select airport hotel] -->  
   4. If [airport hotel cost > Hotel Budget] -->  
   5. Yes --> [Select alternative hotel] -->  
   6. No --> [Confirm hotel selection] -->  
   7. [Select one museum] -->  
   8. If: [Museum ticket > $20] -->  
   9. Yes --> [ Replace with public art gallery] -->  
   10. No --> [Confirm Museum ] -->  
   11. [Check for Restaurant type = vegan] -->  
   12. If:[Resturnat type == vegan] -->  
   13. Yes --> [Keep restaurant option] -->  
   14. No --> [subtitute with restaurant type = Vegetarian] -->  
   15. [Output: Final 1-day Paris itinerary including hotel, museum/gallery, and restaurant]  

### Task 1.2: Flowchart Design with For Loops

**Flowchart**:
   [Start] -->
   [Input: Days = 3, City = Paris] -->
   
   For [each day starting with day 1, until day 3] -->
   do
       [1 morning activity] -->
       [1 afternoon activity] -->
       [1 evening activity] -->
   end for
   
   [Output: Final 3-day travel plan in table format]

### Task 1.3: Flowchart Design with While Loops

**Flowchart**:
   [Start] -->
   [Input: Travel Plan, Days = 1, City = Paris, Excess Budget = $400] -->
   
   While [Excess budget > 0] -->
   do
       [find additional activity, retrieve cost] -->
       If: [cost > excess budget] -->
       Yes --> [continue/do nothing] -->
       No --> [add activity to itinerary, subtract cost from Excess budget] -->
   end while
   
   [Output: Final 1-day travel plan, additional activities each day]

## Set 2: Handling Edge Cases

### Task 2.1: Conditionals For Handling Edge Cases

**Selected edge cases**:
a. The museum selected is closed on the trip day
b. The weather is rainy, so outdoor activities need to be swapped for indoor ones

**Improved Prompt**:

```Plan a 1-day Paris itinerary for tomorrow with a budget of $150. Recommend one museum, one park, and one restaurant. Verify the museum's availability on that day, if not open, then suggest a different one, else keep the currently selected museum. Check weather on that day, if rainy, then swap any outdoor activities with indoor activities, else keep the current activity.```

**Transcript Link**:
https://copilot.microsoft.com/shares/hYxB8GhhUJWC9TDqNf5TT

**Reflection**:
The improved prompt gave the LLM the instructions needed to verify the availability of the museum and weather on the day. By highlighting these edge cases, the output enforces real-time, accurate resutls that portray the real circumstances of the trip.

## Set 3: Chain-of-Thought and Few-Shot Prompting

### Task 3.1:CoT prompting

**CoT prompt**:
Plan a 1-day Paris itinerary with one museum, one park, and one restaurant. Please show your step by step thought process by first estimating the time needed for each activity, adding them together, then comparing the total with the available 6 hours, and finally giving the answer with the completed itinerary.

**Transcript Link**:
https://copilot.microsoft.com/shares/xqmeGrxgguhQ1Z53wAHoM

**Analysis**:
The updated prompt allowed us to view the LLM's full thought process, allowing us to verify information. The model correctly followed instructions, by enforcing each step along the way.

### Task 3.2: Prompt Reverse Engineering

**Few shot prompt**:
Plan a 1-day Paris itinerary under $150 that includes a museum, a park, and a restaurant. Follow the style of these examples: [Example 1]: Museum: Louvre ($20) Park: Tuileries Garden (Free) Restaurant: Le Pain Quotidien ($15) Total Cost: $35. [Example 2]: Museum: Musée d’Orsay ($18), Park: Luxembourg Gardens (Free), Restaurant: Café de Flore ($12), Total Cost: $30. Now generate a new itinerary in the same format, with each activity listed and the total cost calculated. Do not add extra commentary.

**Transcript Link**:
https://copilot.microsoft.com/shares/rxqXhwBCkp3zdKeLk55zS

**Analysis**:
The updated prompt with 2 shots gave the LLM the information needed to match our expectations completely. It was able to match the ouput entirely.

## Reflection
Through these tasks, we learned that prompt engineering is similar to programming concepts. Conditionals helped structure the outputs by adapting the results to constrains, while the loops mirror repitition and scalability when building itinerarirfes cross days or within budgets. When handling edge cases, we learned the importance of thoroughness, to ensure the prompts would anticipate real-world complications. CoT prompting allowed us to see the LLM's reasoning, letting us verify information step by step. Few-shot prompting was extremely effecting. It showed the model concrete expectations and guided it to replicate the desired outcome. Collectively, these techniques helped enhance precision, reliability and clarity in prompt design, which converted vague instructions into systematic instructions.
