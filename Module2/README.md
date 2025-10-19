### Langraph

Module2:

Video1:
This lesson explains how to define a state schema in Python. You can use TypedDicts from the typing module or Python dataclasses to structure dictionary states. Additionally, Pydantic can be used for runtime type checking to ensure data validity.

Tweaking:
I added a new node called node_4 to handle the "empty" mood, making it parallel to node_2 and node_3. I also created a new code cell at the end of the notebook to test the Pydantic state with the "empty" mood. These changes ensure the graph can handle an additional mood state and demonstrate its validation.
file: ![state-schema.ipynb](state-schema.ipynb)
