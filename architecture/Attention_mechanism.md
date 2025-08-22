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

For example the word 'mole' in each sentence in the diagram above, has different meanings in different contexts, but in the initial step of a transformer, the vector embedding associated with the token 'mole' is the same in all cases. It is the next step in which the surrounding embeddings provide contect and influence the specific meaning. The attention block allows the model to refine the meaning of a word and transfer information between embeddings. The prediction of the next token is based on the last vector in the sequence.

![Output examples:](../deepseek_assets/8.webp)







