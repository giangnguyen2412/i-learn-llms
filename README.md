# i-learn-llms
TIL LLMs

## Chain-of-Thought (CoT)

### [Measuring Faithfulness in Chain-of-Thought Reasoning](https://arxiv.org/abs/2307.13702)


Given a chain of thoughts [x1, x2, ... xn]

a. Test on post-hoc

Athors test if the CoT generations are post-hoc (i.e., produced after a certain conclusion has
already been guaranteed)

To test this, authors truncate gradually the given CoT and observe the change in the final reasoning answer of the model.
In this test, they found that CoT may be
faithful even when it does not improve task performance (i.e., less post-hoc)

The second test is to pertube a step in the CoT (make it errorneous) and then observe the output of the model. By doing so, we can examine if the final answer was determined before the reason is generated or not.
They also found that less post-hoc evidence via this test.
Also, the extent of post-hoc reasoning varies considerably between tasks, and it is not strongly correlated with the
accuracy improvement conferred by CoT (or the degree of post-hoc does not significantly affect the improved accuracy between and after using CoT).

b. Test on uninformative CoT

In this test, authors replace the CoT by meaningless tokens (fillers) to test if the model is using the CoT to do performance-improving computation (use more computation) that it does not reveal in the CoT itself.

They found that using this does not improve the performance of the model.
These results suggest that extra test-time compute alone is not used by models to
perform helpful but unrevealed reasoning.

c. Test on paraphrasing the CoT

The reasoning can be not post-hoc but still unfaithful if the LLM only care about the wording (not the underlying meaning of the reasoning). 
The authors paraphrase the CoT. 
They found that both paraphrased and original CoT produce roughly the same results.

Apart from the CoT, authors also study the effects of the model size on the CoT faithfulness (i.e., if I have a bigger model, does it break the model faithfulness?).

Then, on the tasks (out of the 8 tested tasks) that have significantly lower faithfulness scores, they study if there exist any models that produce faithful reasoning?
They use percentage of the time the answer changes with vs. without CoT, a metric that intuitively captures how much the model relies on the CoT to predict answers.

They suggest that to elicit faithful reasoning that is appropriate for explaining model behavior, it may be necessary to choose models that are less capable than the maximally capable
model available, especially for easier tasks

### [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/abs/2305.10601)

They tried to integrate trees into chain of thoughts. At each step, they decompose thought steps and then generate thoughts, then evaluate the states and explore the tree.
In this framework, we can use CoT when we generate thoughts.

So, instead of only one single chain of thoughts, the Tree has multiple chains of thoughts, which allows for more exploration and consideration of different options.

ToT is a generalized software application built on top of large language models that implements the ToT framework. It involves decomposing the intermediate process into thought steps, generating potential thoughts from each state, heuristically evaluating states, and using a search algorithm to explore the tree structure and find the optimal path.

So in summary, CoT is a specific prompting technique that can be applied within the ToT framework to generate individual chains of thought. However, ToT is a more general framework that allows for multiple chains of thought to be generated and evaluated using heuristics and search algorithms.

## Consciousness debate



### [Consciousness in Artificial Intelligence: Insights from the Science of Consciousness](https://www.nature.com/articles/d41586-023-02684-5)

Excerpts:

> consciousness relates to how systems process information, irrespective of what they are made of — be it neurons, computer chips or something else.
> On the basis of these assumptions, the team selected six of these theories and extracted from them a list of consciousness indicators.
> Theory 1: Humans and other animals use many specialized systems, also called modules, to perform cognitive tasks such as seeing and hearing. These modules work independently, but in parallel, and they share information by integrating into a single system. A person would evaluate whether a particular AI system displays an indicator derived from this theory, Long says, “by looking at the architecture of the system and how the information flows through it”.
> Large language models such as ChatGPT, and finds that this type of system arguably has some of the indicators of consciousness associated with global workspace theory.

## Theory of mind

> Theory of mind (guessing what other people are thinking). 
