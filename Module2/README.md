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
