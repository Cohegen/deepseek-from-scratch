# DeepSeek Implementation from Scratch

![Output Example](../deepseek_assets/deepseek.webp)

## Overview
  1. Launch and Global Impact
     -DeepSeek is a Chinese-developed large language model released in January 2025. Its debut, notably the DeepSeek-R1 model on January 20, 2025, generated significant global attention—surpassing ChatGPT as the most-downloaded free app in the U.S. iOS App Store and triggering a sharp drop in Nvidia’s stock, wiping out hundreds of billions in market value.
  
  2.  Cost Effeciency and Market Reaction
     - DeepSeek earned headlines for its extraordinary cost-efficiency. Its V3 model was trained for roughly US $5–6 million using around 2,000 Nvidia H800 GPUs, compared to the estimated $100 million+ for GPT-4 and vastly more compute-hours. This shock revelation prompted fears of a cost war in AI and triggered a dramatic sell-off in tech stocks.

  3. Architectural Innovations
     - Deepseek's efficiency stems from several key technical innovations:
       a) Mixture-of-Experts(MoE)
          - A MoE with a whooping 671B parameters, though only about 34-37B parameters are activated per token, delivering major compute savings.

       b) Multi-Head Latent Attention (MLA)
          - MLA compresses the Key-Value cache into a lower-dimensional latent representation, drastically reducing memory usage during inference.

       c) Multi-Token Prediction (MTP)
          - Enables the model to predict several future tokens at once, boosting generation speed and efficiency.

       d) Auxiliary-Loss-Free Load Balancing
          - DeepSeek-V3 introduced a mechanism to balance load across experts dynamically, achieving about 90% utilization without traditional auxiliary loss terms.

       e) Reinforcement Learning Emphasis
         - DeepSeek notably leveraged reinforcement learning (RL) heavily arguing that reasoning capabilities can emerge through RL without strong supervised fine-tuning.
           
