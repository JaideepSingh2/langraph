##Module 3

Video1:
There are several streaming modes: values mode — sends the whole graph state after each node runs.
Updates mode — sends only the state changes after each node.
Messages mode is for message-based workflows, and astream_events streams real-time tokens.

Tweaking:
The state class now uses running_outline: str instead of summary: str to store the ongoing conversation outline, summarize_conversation was updated to read and update running_outline, and all prompts and comments mentioning summary were changed to say outline.

![streaming-interruption.ipynb](streaming-interruption.ipynb)
