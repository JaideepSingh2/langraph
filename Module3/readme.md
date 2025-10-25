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

Video3:
This part is about changing the message while the model runs the code. In the notebook, the model is first told to do something, then at the breakpoint, human feedback can be used to edit the command if needed, and the model continues with the updated code.

Tweaking:
The tools were switched from arithmetic to string operations and the prompts were updated to match. The section where the LLM waits for user input was changed to allow several inputs at different breakpoints, with each new input updating the previous one using a while loop.

file: ![edit-state-human-feedback.ipynb](edit-state-human-feedback.ipynb)

Video4:
Earlier, breakpoints would always trigger no matter what the user input was, which is not ideal for every situation. Dynamic breakpoints were added so they only activate when certain conditions are met, making them more flexible. This section shows how a dynamic breakpoint was created and how it changed the flow.

Tweaking:
A new dynamic breakpoint was added at step 3 to check if the input contains digits and another node was placed before END. The conditions and flags for dynamic nodes were updated, and dynamic_breakpoints.py was changed to include these updates.

file: ![dynamic_breakpoints.py](dynamic_breakpoints.py) ![dynamic_breakpoints.ipynb](dynamic_breakpoints.ipynb)

Video5:
I learned about replaying and forking at specific checkpoints or steps. Using get_state_history() lets you see the complete history of the graph’s states. Forking allows you to start the graph again from an earlier checkpoint with new input, while replaying simply re-runs a checkpoint without re-executing nodes since the graph tracks if it has already run that step.

Tweaking:
The arithmetic operation tools were updated and expanded, and the prompts were changed so that multiple tools could be called at the same time.

file: ![dynamic_breakpoints.py](dynamic_breakpoints.py)
