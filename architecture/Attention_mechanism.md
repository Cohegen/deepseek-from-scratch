## Attention in transformers

# Why We Need the Transformer in Deep Learning

Before Transformers, the dominant models for sequential data (like text, audio, DNA, time series) were **RNNs** (Recurrent Neural Networks) and their stronger variants like **LSTMs** and **GRUs**. These models read input step by step, passing information forward in sequence. That had some big **limitations**:

## 🚨 Limitations of RNNs/LSTMs
1. **Poor handling of long-term dependencies**  
   - RNNs struggle to remember information far back in a sequence (like the start of a long paragraph).  
   - Even LSTMs, which improved memory, had practical limits.

2. **Sequential bottleneck**  
   - RNNs and LSTMs process one token at a time, making training slow and less parallelizable.  

3. **Difficulty in capturing context**  
   - RNNs focus more on nearby tokens and can "forget" or distort the importance of words far apart.

---

## 💡 What the Transformer Brings

The **Transformer**, introduced in *"Attention Is All You Need"* (Vaswani et al., 2017), solved these problems with a new idea: **attention**.

- **Self-Attention**  
  Instead of moving step by step, Transformers look at *all tokens in parallel*. Each word can "attend" to every other word directly, no matter how far apart.  
  Example: In *"The cat that the dog chased was black"*, the model can directly connect *"cat"* with *"was black"*.

- **Parallelization**  
  Since Transformers don’t rely on sequential recurrence, we can process all words at once → **much faster training** on GPUs/TPUs.

- **Scalability**  
  Transformers scale extremely well with more data and parameters. This is why models like GPT, BERT, and LLaMA can be trained with billions of parameters.

- **Versatility**  
  They’re not just for text. The same architecture powers **vision transformers (ViT)**, **protein folding (AlphaFold)**, **speech recognition**, and even **reinforcement learning**.

---

- The goal of the transformer model is to predict the next word in a sequence of words.
![Output examples:](../deepseek_assets/2.webp)

Tokens, which smallest units of text, are associated with high-dimensional vectors called embeddings.
![Output examples:](../deepseek_assets/3.webp)

These embeddings capture semantic meaning in a high-dimensional space.
![Output examples:](../deepseek_assets/4.1.webp)

![Output examples:](../deepseek_assets/5.webp)

The attention mechanism helps adjust these embeddigs to encode richer contextual meanings of tokens within the input sequence.

![Output examples:](../deepseek_assets/6.webp)

Before diving deep into computational details of the transformer, it's important to consider an example that demonstrates the desired behavoir of attention.

![Output examples:](../deepseek_assets/7.webp)

For example the word 'mole' in each sentence in the diagram above, has different meanings in different contexts, but in the initial step of a transformer, the vector embedding associated with the token 'mole' is the same in all cases. It is the next step in which the surrounding embeddings provide contect and influence the specific meaning. The attention block allows the model to refine the meaning of a word and transfer information between embeddings. The prediction of the next token is based on the last vector in the sequence.

![Output examples:](../deepseek_assets/8.webp)

![Output examples:](../deepseek_assets/9.webp)

In order for the model to accurately predict the next word, the final vector in the sequence needs to be updated by all of the attention blocks to represent the relevant information from the full context window. Suppose the input is 'a fluffy blue creature roamed the verdant forest' and we only care about adjectives adjusting the meaning of their coresponding nouns. Each word is initially embedded as a high dimensional vector that encodes its meaning and position.

![Output examples:](../deepseek_assets/10.webp)

![Output examples:](../deepseek_assets/11.webp)

## The Attention Block
In deep learning, word embeddings are used to represent words and their positions in a context. The goal in attention mechanism is to refine the meaning of these embeddings by incorporating meaning from other words. This refining process is achieved through matrix vector multiplications, whre tunable weights are learned based on the data.
This done by computing a query vector for each word, which is obtained by multiplying a learned query matrix with the embeddings of each word.

![Output examples:](../deepseek_assets/12.webp)







