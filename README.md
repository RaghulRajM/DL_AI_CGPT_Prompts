# DL_AI_CGPT_Prompts

This repository was created using the contents from Deeplearning.ai's courses.

**Intro**:
There are two types of LLMS-
Base LLMs - That predict the next word. For eg, If asked what's the capital of France?, It predicts Which is the largest city in France?....

**Instruction Tuned LLMs** - Tries to follow instructions. Gives Paris as the answer when that question is asked. It uses Reinforcement Learning with Human Feedback. The course will focus on this type. 

**Guidelines**:
* **Instructions need to be clear and specific** : Make use of delimiters (""", ```, ---) to distinguish between the instructions and the content to be used.
  * Delimiters help in preventing prompt injections (Some part of the content that's conflicting with the instruction). 
  * We may also ask for structured output (HTML/JSON). For eg. Provide them in JSON format with the following keys: 
book_id, title, author, genre.
  * Check whether the conditions are satisfied. Check assumptions required to do the task. For eg. Rewrite the content only if it contains set of instructions into a sequence of steps.
  * Few-shot prompting: Give successful examples of completing the tasks and then ask the model to perform the task.

* **Give the model sometime to think** :
  * Specify the steps to complete a task. Rather than telling "Output a json object that contains the following keys: french_summary, num_names." Provide steps to summarize in english, translate in French, Give all the names and take their count.
  * Instruct the model to work out it's own solution before reaching a conclusion. For eg. If the objective is to grade a student's HW question. Rather than providing the question and the student's answer, ask the model to derive it's own answers and compare the solution with that of the student's only after the model had arrived at a solution. Otherwise it'll simply tell it's correct.
    
* **Model Limitations**:
  * Hallucination: Make statements that sound plausible but are incorrect
     * To combat this, ask the model to first find releavant information and answer based on that information.


