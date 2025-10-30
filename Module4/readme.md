##Module 4

Video1:
I learned how parallel nodes can run together and used an add reducer to combine outputs from two nodes at once. The default order for parallel nodes set by Langgraph was changed using a sorting function. Tavily was used to create a web search agent that runs different searches in parallel nodes.

Tweaking:
More nodes were set to run in parallel and two sub-nodes were added inside a parallel node to expand the feature. A research article search using Tavily was created to check specific research sites for answers and added as a node.

![parallelisation.ipynb](parallelisation.ipynb)

Video2:
This section explained sub-graphs, which help in multi-agent systems by letting each sub-graph handle its own task and send results to the main graph. One sub-graph was used for failure analysis and another for summarizing the question in the example.

Tweaking:
A new subgraph called follow-up was added that asks "What more information do you need?" and the schema was updated to include it. The logs showed the follow-up question being printed, confirming it was integrated into the parent graph. The notebook and screenshots of the trace with the follow-up are included in the folder.

file: ![sub_graph.ipynb](sub_graph.ipynb)

Video3:
Map-reduce is a method where the map step splits a task into smaller parts to run in parallel, and the reduce step gathers and combines the results from those parts.

Tweaking:
Pickup-line generation and selection were added alongside the joke generator and best joke selection. Both joke and pickup-line generators were run in parallel to choose the best overall result. The map-reduce.py file was updated with these changes.

file: ![map_reduce.py](map_reduce.py) ![map-reduce.ipynb](map-reduce.ipynb)

Video4:
I learned how to build a Research Assistant by combining earlier concepts, creating an analyst for a topic where each analyst researches in parallel and their findings are merged into one report. The analyst asks questions about the topic, searches different sources for answers, and writes results to context for answering. This repeats until a condition is met, messages from the interview are saved to state, and a section is written based on the interview.

Tweaking:
The prompts were updated to focus on analyzing singularity and AGI along with their possible negative effects. A search_research function was added to work with the existing search_web and search_wikipedia functions using Tavily.

file: ![research-assistant.ipynb](research-assistant.ipynb)
