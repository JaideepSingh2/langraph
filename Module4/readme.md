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
