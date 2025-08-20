# General LLM architecture
The diagram below shows the general architecture of basically all LLMs that exist today:

![Output examples](https://raw.githubusercontent.com/Cohegen/deepseek-from-scratch/main/deepseek_assets/Basic-LLM-architecture.webp)

Think of an LLM as a car engine that takes oil to release energy that is used to drive the car.
In general, we don't know what takes place inside the car engine, since it involves a bunch of complex processes. Similarly, most of us are unaware of how LLMs like DeepSeek, ChatGPT, Claude, etc., generate text. We are used to giving the model text and it generates text as an answer. However, have you ever wondered what actually happens inside?

## Journey of a Token through an LLM
To understand how an LLM works, let's use the following sentence as our example: "Attention is all you."
Our task is to predict what word comes after the word "you."

Before we get to the predicted part, let's begin our journey from the start. We give our model our example sentence as input.

LLMs don't process text directly; there are crucial processes that take place before doing that:

1. **Tokenization**: Each word is broken down into small units called tokens. Tokens are small pieces of words, subwords, or characters in an input sequence. Each token is assigned a unique identifier (an integer). For example, "Attention" might become `[77321]`, "is" `[210]`, "all" `[443]`, "you" `[987]`. The actual numbers depend on the tokenizer and vocabulary.

2. **Vector Embedding**: The tokens are mapped into vectors in a high-dimensional space, so as to capture their meaning. The number of dimensions depends on the model being used; some have 768 dimensions, others have 12,808 dimensions. This mapping allows the model to work with mathematical representations of words.

3. **Positional Embedding**: While vector embeddings carry information about each token, they don't capture the order of tokens in the sequence. Positional embeddings are added to token embeddings to help the model understand the position of each token in the input. This is crucial for language, since "Attention is all you" means something different from "You all is attention".

### The Transformer Block
After preprocessing, the token vectors (with positional information) enter the core of the LLM: the Transformer block.

- **Self-Attention Mechanism**: The transformer uses self-attention to allow each token to "see" other tokens in the sequence. This mechanism helps the model weigh the importance of each token relative to others, enabling it to capture context, relationships, and meaning.
- **Feedforward Networks**: After attention, the output goes through feedforward neural networks for further processing.
- **Layer Stacking**: Multiple layers of attention and feedforward networks are stacked, allowing deep learning of complex patterns.

### Prediction and Output
Once the input sequence has passed through all the layers:

- The final output is a set of logits (raw scores) for each possible next token in the vocabulary.
- The model picks the token with the highest score (or samples from the distribution) as its prediction: for our example, it might pick "need" to complete the sentence as "Attention is all you need".

### Postprocessing
- The predicted tokens are mapped back from vectors to words using the vocabulary.
- The sequence is detokenized to produce readable text.

---

## Summary of the Process

1. **Input**: Raw text → Tokenization (IDs) → Embeddings (vectors) → Positional Embeddings
2. **Processing**: Transformer blocks (self-attention, feedforward layers)
3. **Output**: Probability distribution over possible next tokens → Choose token → Repeat for next word

---

## Why is this architecture powerful?

- **Context-awareness**: The self-attention mechanism allows the model to use context from anywhere in the input, not just nearby words.
- **Scalability**: Stacking transformer layers enables learning of extremely complex language patterns.
- **Generalization**: The embedding space allows the model to capture similarities and relationships between words and concepts.

---

