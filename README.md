# DL_AI_CGPT_Prompts

This repository was created using the contents from Deeplearning.ai's courses.

# Table of Contents
1. [Introduction](#introduction)
2. [Motivation for Prompt Engineering](#motivation-for-prompt-engineering)
3. [Understanding Large Language Models (LLMs)](#understanding-large-language-models-llms)
   - 3.1 [Base LLM](#base-llm)
   - 3.2 [Instruction Tuned LLM](#instruction-tuned-llm)
4. [Prompting Guidelines](#prompting-guidelines)
   - 4.1 [Principle 1: Clarity in Instructions](#principle-1-clarity-in-instructions)
      - 4.1.1 [Use Delimiters for Distinct Input Sections](#use-delimiters-for-distinct-input-sections)
      - 4.1.2 [Request Structured Output](#request-structured-output)
      - 4.1.3 [Check Condition Satisfaction](#check-condition-satisfaction)
      - 4.1.4 [Employ Few-shot Prompting](#employ-few-shot-prompting)
   - 4.2 [Principle 2: Allow Model "Thinking" Time](#principle-2-allow-model-thinking-time)
      - 4.2.1 [Specify Task Steps](#specify-task-steps)
      - 4.2.2 [Encourage Model Solution Exploration](#encourage-model-solution-exploration)
5. [Model Limitations: Addressing Hallucinations](#model-limitations-addressing-hallucinations)
6. [Iterative Prompt Development](#iterative-prompt-development)
   - 6.1 [Prompt Guidelines Through Iteration](#prompt-guidelines-through-iteration)
   - 6.2 [Example](#example)
7. [Summarizing Techniques](#summarizing-techniques)
   - 7.1 [Brevity-focused User Review Summarization](#brevity-focused-user-review-summarization)
      - 7.1.1 [Word/Sentence/Character Limit](#word-sentence-character-limit)
      - 7.1.2 [Shipping and Delivery Focus](#shipping-and-delivery-focus)
      - 7.1.3 [Price and Value Emphasis](#price-and-value-emphasis)
8. [Inference Strategies](#inference-strategies)
   - 8.1 [Sentiment Classification (Positive/Negative)](#sentiment-classification-positive-negative)
   - 8.2 [Emotion Identification](#emotion-identification)
      - 8.2.1 [Recognizing Anger](#recognizing-anger)
      - 8.2.2 [Extracting Product and Company Names from Reviews](#extracting-product-and-company-names-from-reviews)
   - 8.3 [Multitasking](#multitasking)
      - 8.3.1 [Topic Extraction](#topic-extraction)
      - 8.3.2 [Generating News Alerts (Zero Shot)](#generating-news-alerts-zero-shot)
9. [Transformational Tasks](#transformational-tasks)
   - 9.1 [Translation](#translation)
   - 9.2 [Universal Translator](#universal-translator)
   - 9.3 [Tone Transformation](#tone-transformation)
   - 9.4 [Format Conversion](#format-conversion)
   - 9.5 [Spellcheck/Grammar Check](#spellcheck-grammar-check)
   - 9.6 [Style-specific Rewriting](#style-specific-rewriting)
10. [Expansion Techniques](#expansion-techniques)
   - 10.1 [Automated Email Writing](#automated-email-writing)
      - 10.1.1 [Tailoring Customer Service Emails to Reviews](#tailoring-customer-service-emails-to-reviews)
      - 10.1.2 [Temperature Considerations](#temperature-considerations)
   - 10.2 [Chatbot Setup](#chatbot-setup)
      - 10.2.1 [OrderBot](#orderbot)



**Introduction**:
In natural language processing, prompts have gained popularity as a technique to refine language models for specific tasks. A prompt, a brief text input, serves as a starting point for the model to generate responses based on its training. Developers employ prompts for tasks like text generation, question-answering, sentiment analysis, and language translation. Tailoring prompts allows fine-tuning model behavior for enhanced performance in distinct domains. This approach marks a pivotal advancement in natural language processing, offering potential for the future development of more sophisticated language models.
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

* Work in progress...
