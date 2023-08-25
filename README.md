# i-learn-llms
TIL LLMs

## Chain-of-Thought (CoT)

### Measuring Faithfulness in Chain-of-Thought Reasoning

Given a chain of thoughts [x1, x2, ... xn]

Athors test if the CoT generations are post-hoc (i.e., produced after a certain conclusion has
already been guaranteed)

To test this, authors truncate gradually the given CoT and observe the change in the final reasoning answer of the model.
In this test, they found that CoT may be
faithful even when it does not improve task performance (i.e., less post-hoc)
