# GPT2-from-scratch

This repository contains implementation of **GPT-2 small-sized model (≈ 124 M parameters)** completely from scratch using pytorch following workflow from <a href="https://amzn.to/4fqvn0D">Build a Large Language Model From Scratch by Sebastian Raschka</a>.
I have trained the model on "the verdict" book dataset. For next update, I will try to fine tune the LLM for specific use cases.

## 🔑  Key Features
* **Pure-PyTorch** – no Hugging Face, fairseq, Lightning, or megablocks.
* **Readable notebook** that walks through every layer & forward pass.
* **Tokenizer**: OpenAI `tiktoken` (GPT-2 BPE vocabulary = 50 257 tokens).
* **Dataset**: *The Verdict* (public-domain mystery novel, 3.3 MB plain-text).
* **Training loop**: vanilla `AdamW`, gradient-clipping, optional top-k / temperature sampling during generation.
* **Reproducible** – single-seed run reaches ≈ 2.7 nats/char (≈ 35 PPL) after 10 epochs on a single consumer GPU.

  ---

## 📦 Model Configuration

| Hyper-parameter | Value |
|-----------------|-------|
| Layers (`n_layers`) | **12** |
| Attention heads (`n_heads`) | **12** |
| Embedding size (`emb_dim`) | **768** |
| Context length | **1024** tokens |
| Vocabulary size | **50257** |
| Dropout | **0.1** |
| QKV bias | **True** |
| Total parameters | **124 M** |

---

## References:
- [Language Models are Unsupervised Multitask Learners (GPT-2 Paper)](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf)
- [Attention is all you need](https://arxiv.org/abs/1706.03762)
- [Building LLMs from scratch youtube playlist](https://www.youtube.com/playlist?list=PLPTV0NXA_ZSgsLAr8YCgCwhPIJNNtexWu)
