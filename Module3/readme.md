##Module 3

Video1:
There are several streaming modes: values mode — sends the whole graph state after each node runs.
Updates mode — sends only the state changes after each node.
Messages mode is for message-based workflows, and astream_events streams real-time tokens.

Tweaking:
The state class now uses running_outline: str instead of summary: str to store the ongoing conversation outline, summarize_conversation was updated to read and update running_outline, and all prompts and comments mentioning summary were changed to say outline.

![streaming-interruption.ipynb](streaming-interruption.ipynb)

Video2:
Breakpoints let us add human input during an agent’s task execution. They are used for approval to allow or stop execution, for debugging to fix issues, and for editing to change how tasks run. This was seen in both the notebook and langgraph studio.

Tweaking:
Additional tools and new breakpoint choices such as wait were introduced in the notebook. These updates were also made in the .py file, and the effect of breakpoints on the new tool was tested in langgraph studio. Changes were applied to both the notebook and the .py file.

file: ![modified_agent.py](modified_agent.py) ![breakpoints.ipynb](breakpoints.ipynb)
