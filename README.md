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

The second test is to pertube a step in the CoT (make it errorneous) and then observe the output of the model. By doing so, we can examine if the final answer was determined before the reason is generated or not.
They also found that less post-hoc evidence via this test.
Also, the extent of post-hoc reasoning varies considerably between tasks, and it is not strongly correlated with the
accuracy improvement conferred by CoT (or the degree of post-hoc does not significantly affect the improved accuracy between and after using CoT).
