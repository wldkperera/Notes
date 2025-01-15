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


# Inferring = Summarizing









