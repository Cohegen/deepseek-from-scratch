# General LLM architecture
-The diagram below shows the general architecture of basically all LLM that exist today:

![Output examples](https://raw.githubusercontent.com/Cohegen/deepseek-from-scratch/main/deepseek_assets/Basic-LLM-architecture.webp)

- Think of an LLM as a car engine that takes oil to release energy that is used to drive the car.
- In general we don't know what takes place inside the car engine, since it a bunch of complex processes that take place inside a car engine.
- Similary most of us are unaware of how LLMs like deepseek,chatGPT, claude etc generate text. We are used to giving the model text and it generates texts as an answer. However, have you ever wondered how these models work under the hood. That's what we'll be doing.

## Journey of a Token through and LLM
- To understand how an LLM works let's use the following sentence as our example: "Attention is all you".
- Our task it to predict what word comes after the word "you".
- Before the predicted part let's begin our journey from the beginning from the start. So we give our model our example sentence as input.
- LLMs don't directly process text directly there are crucial process that take place before doing that, they are:
   1. Tokenization : 





