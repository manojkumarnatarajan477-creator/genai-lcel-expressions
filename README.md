## Design and Implementation of LangChain Expression Language (LCEL) Expressions

### AIM:
To design and implement a LangChain Expression Language (LCEL) expression that utilizes at least two prompt parameters and three key components (prompt, model, and output parser), and to evaluate its functionality by analyzing relevant examples of its application in real-world scenarios.

### PROBLEM STATEMENT:

### DESIGN STEPS:

#### STEP 1:
 Import the required libraries (os, openai, dotenv, and LangChain modules) and configure the OpenAI API key using the .env file.




#### STEP 2:
 Create a prompt template using ChatPromptTemplate, initialize the ChatOpenAI model (gpt-4o), and define StrOutputParser() to process the output.

#### STEP 3:

 Combine the prompt, model, and output parser using the LCEL pipe (|) operator to create a chain. Invoke the chain with the input topic "earth" and display the generated response.

 ### STEP 4:
 Execute the chain with different input topics and verify that it generates relevant and meaningful responses for each topic.
 
### PROGRAM:

```py
import os
import openai

from dotenv import load_dotenv, find_dotenv

_ = load_dotenv(find_dotenv())
openai.api_key = os.environ['OPENAI_API_KEY']

from langchain.prompts import ChatPromptTemplate
from langchain.chat_models import ChatOpenAI
from langchain.schema.output_parser import StrOutputParser

prompt = ChatPromptTemplate.from_template(
    "Tell me an interesting fact about {topic}"
)

model = ChatOpenAI(model="gpt-4o")

output_parser = StrOutputParser()

chain = prompt | model | output_parser

chain.invoke({"topic": "earth"})

```

### OUTPUT:
<img width="1441" height="707" alt="image" src="https://github.com/user-attachments/assets/da720979-46da-4cc9-a778-170b82e9709e" />


### RESULT:
