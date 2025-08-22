## Attention in transformers
- The goal of the transformer model is to predict the next word in a sequence of words.
![Output examples:](../deepseek_assets/2.webp)

Tokens, which smallest units of text, are associated with high-dimensional vectors called embeddings.
![Output examples:](../deepseek_assets/3.webp)

These embeddings capture semantic meanig in a high-dimensional space.
![Output examples:](../deepseek_assets/4.1.webp)

![Output examples:](../deepseek_assets/5.webp)

The attention mechanism helps adjust these embeddigs to encode richer contextual meanings of tokens within the input sequence.

![Output examples:](../deepseek_assets/6.webp)

Before diving deep into computational details of the transformer, it's important to consider an example that demonstrates the desired behavoir of attention.

![Output examples:](../deepseek_assets/7.webp)



