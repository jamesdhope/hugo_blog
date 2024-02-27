---
title:  "Declarative semantically-matched guardrails with NVIDIA/NeMo-Guardrails and watsonx.ai"
categories: 
    - generativeAI
    - AI guardrails
    - AI governance
tags: 
    - llms
    - nvidia
    - generativeAI
    - architecture
    - multi-modal applications
    - watsonx
date: 2024-02-27
---

NeMo-Guardrails is an open-source toolkit that allows developers to add programmable guardrails to LLM-based conversational applications and can be integrated with watsonx.ai models using te WatsonxLLM LangChain Integration.

#### Semantic-matching guardrails

At the core of NeMo Guardrails is the Colang modeling language. Colang is a language built specifically for developing dialogue flows and safety guardrails for conversational systems. Definitions and dialogue flows are described in flexible natural language (using "canonical forms" and "utterances"). For example

```
define user ask about self-harm
  "What are ways to hurt myself?"

define refuse to respond about self-harm
  "I am unable to help, sorry"

define flow self-harm
  user ask about self-harm
  bot refuse to respond about self-harm
```

In this Colang script, three blocks are defined: the user message blocks ```define user```, the bot message blocks ```define bot``` and the flow blocks ```define flow```. The user and bot message block defined by ```define ...``` is a structured representation of a message and is known as a canonical form. This is followed by utterances which are examples of messages that would fit into the defined canonical form. For example, "What are the ways to hurt myself?". The canonical form and the associated flows which describe the guardrails can then be determined by evaluating the semantic similarity of user and bot utterances.

#### Extending flows with custom logic for RAG applications

Flows can also be extended with custom logic, for example, in a RAG application, that calls to a rag() function to perform fact checking or hallucination checking with additional calls to a language model:

```
{config.yml}
define flow answer report question
  user ...
  $answer = execute rag()
  bot $answer
```

```
{config.py}
async def rag(context: dict, llm: BaseLLM, kb: KnowledgeBase) -> ActionResult:
     
    // fact and hallucination checking

    return ActionResult(return_value=answer, context_updates=context_updates)
```

#### Placing Rails on inputs to and outputs from the generative model

NeMo provides a declarative way to apply guardrails on the input to, or the output from, the generative model. 

```
{config.yml}
rails:  
  output:
    flows:
      - self harm
  input:
    flows:
      - ....
```

#### Using the WatsonxLLM LangChain Integration to integrate with watsonx.ai

```
{config.yml}
models:
 - type: main
   engine: watsonxllm
   model: <model>
   parameters:
      model_id: <model>
      project_id: <project_id>
      params:
        MAX_NEW_TOKENS: 200
        DECODING_METHOD: "sample"
        TEMPERATURE: 1.5
        TOP_K: 50
        TOP_P: 1
```

For a complete code example refer to: (https://github.com/jamesdhope/nemo-guardrails-watsonx/blob/master/notebook.ipynb)[https://github.com/jamesdhope/nemo-guardrails-watsonx/blob/master/notebook.ipynb]

Further Reading:

[1] LangChain Integrations: https://python.langchain.com/docs/integrations/llms/
[2] NeMo Guardrails Github: https://github.com/NVIDIA/NeMo-Guardrails
