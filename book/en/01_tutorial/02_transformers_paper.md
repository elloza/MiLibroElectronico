# 2. The Transformers Paper

This chapter summarizes the paper located in the project's recursos folder (`recursos/paper_transformers.pdf`):
**Attention Is All You Need** (Vaswani et al., NeurIPS 2017).

## Main idea

The core proposal is to replace recurrent and convolutional sequence models with an architecture based only on attention.
That architecture is the **Transformer**.

Instead of processing tokens one by one like an RNN, the Transformer can process all tokens in parallel during training.

## What problem it addressed

In machine translation and other sequence tasks, previous models:

- were slower to train due to sequential computation,
- had more difficulty modeling long-range dependencies,
- and scaled worse with sequence length.

The paper shows that self-attention improves both quality and training efficiency.

## Key Transformer components

1. **Self-Attention**: each token attends to other tokens in the same sequence.
2. **Scaled Dot-Product Attention**: attention scores are scaled by $\sqrt{d_k}$.
3. **Multi-Head Attention**: multiple parallel heads capture different relations.
4. **Positional Encoding**: since there is no recurrence, position is injected with sinusoidal signals.
5. **Encoder-Decoder stacks**: attention + feed-forward blocks with residual connections and layer normalization.

## Reported results

According to the paper:

- it outperformed prior state of the art on WMT14 English-German,
- achieved very strong performance on WMT14 English-French,
- and reduced training cost compared with previous approaches.

## Why it was influential

This paper reshaped deep learning for language and later many other domains.
Models such as BERT, GPT, and modern LLMs are built on Transformer foundations.

## One-line takeaway

The paper shows that **attention alone** can be the core of sequence models that are more accurate, more parallelizable, and more scalable than classic recurrent alternatives.
