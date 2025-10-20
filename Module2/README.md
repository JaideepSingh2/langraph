### Langraph

Module2:

Video1:
This lesson explains how to define a state schema in Python. You can use TypedDicts from the typing module or Python dataclasses to structure dictionary states. Additionally, Pydantic can be used for runtime type checking to ensure data validity.

Tweaking:
I added a new node called node_4 to handle the "empty" mood, making it parallel to node_2 and node_3. I also created a new code cell at the end of the notebook to test the Pydantic state with the "empty" mood. These changes ensure the graph can handle an additional mood state and demonstrate its validation.
file: ![state-schema.ipynb](state-schema.ipynb)

Video2:
I learnt that when two nodes in a LangGraph execute in parallel, their outputs for the same state key will, by default, overwrite each other, which can cause errors or loss of data. To address this, reducers are used so that instead of overwriting, the new values are accumulated (for example, added to a list along with the initial value). This behavior can be implemented using Annotated keys, allowing the graph to merge values from parallel nodes safely.

Tweaking:
I modified the code to use a list of movies instead of integers. The foo key, which was originally of type int, was changed to a movie key of type str. The initial operation that concatenated integers was updated to concatenate strings instead. Additionally, I changed the questions and logic in the implementation of the add_messages and remove_messages reducers to reflect the new context of handling movie titles.

file: ![state-reducers.ipynb](state-reducers.ipynb)

Video3:

LangGraph supports defining and using multiple state schemas within a single graph, specifically as Private, Input, and Output state schemas. Private states are used for passing information between nodes internally and are not exposed outside the graph. Input states are provided by the user as inputs to the graph, while Output states are the results produced by the graph and returned to the user. This separation helps minimize redundant information and encapsulates internal details, ensuring users only interact with the necessary data for the application.

Tweaking:
I updated the private state example to use a score (or scratch) key instead of the previous example, and made sure all invocations and references in the code reflect this change. Additionally, I reworked the input and output state schemas so that they are consistent with the new score/scratch structure, ensuring the flow and data handling in the graph align with the updated schema.

file: ![multiple-schemas.ipynb](multiple-schemas.ipynb)

Video 4:

In this video, we learned how editing messages can help reduce token usage, making our application more cost-efficient. We revisited removing messages and explored filtering which messages the LLM sees to lower token usage without altering the saved message state. Additionally, we covered trimming messages, which lets us control token usage by number and customize strategies, including whether to allow partial messages.

Tweaking:
I modified the deletion and filtering of messages, and also updated and added trimming functionality. Various token usage limits and trimming strategies were tested to observe their effects.

file: ![trim-filter-messages.ipynb](trim-filter-messages.ipynb)

Video 5:

I learned how to summarize conversation history using a Python function and implement it with LangGraph's checkpointers for persistence. The summary function is triggered only when the conversation history exceeds a certain number of messages, using a conditional edge. This approach is more resource-efficient for retaining essential information compared to trims, filters, or reducers.

Tweaking:

I changed the threshold for triggering the summary function to 8 messages and extended the conversation by introducing a new topic about my favourite movies to test this behavior. I also reviewed all the traces in LangGraph, which are included as attachments within the notebook.

file: ![chatbot-summarization.ipynb](chatbot-summarization.ipynb)
