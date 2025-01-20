# 2 types of LLMs

## 1. Base LLM

Predict next word, based on text training data


## 2. Instruction Tund LLM

1. lot of reasech and practice has been going
2. trained to follow instructions, fin tunned on instructions
3. **RLHF** - Reinforcement learning with human feedback
4. helpful, honest and harmless
5. easy to use, recommend to use




import openai
import os

from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file

openai.api_key  = os.getenv('OPENAI_API_KEY')


def get_completion(prompt, model="gpt-3.5-turbo"):
    messages = [{"role": "user", "content": prompt}]
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=0, # this is the degree of randomness of the model's output
    )
    return response.choices[0].message["content"]




# Instruction Tuned LLM

### Iterative process

![image](https://github.com/user-attachments/assets/700477d2-9ebd-4cbf-928e-0d929320a286)

1. Try something
2. Analyze where the result doesn't give what you want
3. clarify intructions, give more time to think
4. Refine prompts with a batch of examples

**Prompt guidelines**

1. Be clear and specific
2. Aanalyze why results doesn't give desired output
3. Refine the idea and the prompt
4. Repeat


# Lesson 4: Summarize

prod_review = """
Got this panda plush toy for my daughter's birthday, \
who loves it and takes it everywhere. It's soft and \ 
super cute, and its face has a friendly look. It's \ 
a bit small for what I paid though. I think there \ 
might be other options that are bigger for the \ 
same price. It arrived a day earlier than expected, \ 
so I got to play with it myself before I gave it \ 
to her.
"""

prompt = f"""
Your task is to generate a short summary of a product review from an ecommerce site. 

Summarize the review below, delimited by triple backticks, in at most 30 words. 

Review: ```{prod_review}```
"""

response = get_completion(prompt)
print(response)


## Inferring = Summarizing


## Transforming

language translation, Universal translator, spelling and grammar checking, tone adjustment, and format conversion.


## Spellcheck/Grammar check.

Here are some examples of common grammar and spelling problems and the LLM's response.

To signal to the LLM that you want it to proofread your text, you instruct the model to 'proofread' or 'proofread and correct'.



# Chatbots

import os
import openai
from dotenv import load_dotenv, find_dotenv
_ = load_dotenv(find_dotenv()) # read local .env file

openai.api_key  = os.getenv('OPENAI_API_KEY')


def get_completion(prompt, model="gpt-3.5-turbo"):
    messages = [{"role": "user", "content": prompt}]
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=0, # this is the degree of randomness of the model's output
    )
    return response.choices[0].message["content"]

def get_completion_from_messages(messages, model="gpt-3.5-turbo", temperature=0):
    response = openai.ChatCompletion.create(
        model=model,
        messages=messages,
        temperature=temperature, # this is the degree of randomness of the model's output
    )
comment     print(str(response.choices[0].message))
    return response.choices[0].message["content"]



1. Prsona
2. split up tasks
3. custome instructions in pro versions
4. Socratic prompting - critical thinking and exploration, uncoveer insights through questioning



# 4T

Traits - charasteristic
tasks - what
tones - sounds
targets - to whom



1. **Gen AI** - a broad description of AI that generates such as text, images, audio, video or code
2. **Prompt Engineering** - Constructing inputs that helps to get most out of Gen AI
3. **Token** - A unit easily understood by LLM

![image](https://github.com/user-attachments/assets/1d420139-4ece-47e9-8f2c-c2fe94da006d)

4. **Tokenization** - The mechanism by which a model spilts its inputs into tokens
5. **RLHF** - Rinforcement learning from Human Feedback
6. **Few Shot Learning** - teach to do somthing by showing fewstructured examples 


# Text Prompt Best Practices
 

1. Give Clear Instructions:

Unclear prompts may result in generic or inaccurate outputs. Be sure to include relevant details, such as the desired output format and context.

 

2. Assign a Persona:

Begin your prompt by assigning a specific role to the AI assistant.

 

Examples:

“You are a senior marketing professional specializing in social media campaigns…”

“As a user experience expert, you are capable of…”




3. Use Delimiters to Structure Your Prompt:

Delimiters can help organize the prompt clearly. This example uses three quotes as delimiters:

 

The following is a part of a Wikipedia article on Language Models:

“””

A language model is a probabilistic model of a natural language.[1] In 1980, the first significant statistical language model was proposed, and during the decade IBM performed ‘Shannon-style’ experiments, in which potential sources for language modeling improvement were identified by observing and analyzing the performance of human subjects in predicting or correcting text.

“””

 

In this prompt, markdown-style ticks are used with the label “python”

 

How can we make this function more efficient with lru_cache?

`python

def fib(n):

    if n in {0, 1}:

        return n

    return fib(n-1) + fib(n-2)

`

 

3. Break Tasks into Subtasks:

Divide complex tasks into manageable steps.



![image](https://github.com/user-attachments/assets/b262dc42-7d27-4637-8dbe-e38b7ae025dd)



# Do

1. be specific - tone, context, task
2. keeep it conversational
3. provicde some examples and guides
4. instead of just asking to write a mail, ask what you want the email to say
5. use delimters, grammar
6. Be poliet
7. Check accuracy

**Don't let AI's mistakes become your mistakes and reflect on your professionalism**


# Don't

1. just merely use
2. Be vague - lenghty
3. slangs and jargons
4. confusing instructions


Show them the AI is not an intellitent machine by saying the word of "Lolipop" to backwords






























