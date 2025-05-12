# llm_finetune_labs

## Overview

This project explores **personality-driven fine-tuning** of a large language model using [Qwen3-0.6B-Base](https://huggingface.co/Qwen/Qwen3-0.6B-Base).
The goal is to build two distinct AI advisors:

* **Encouraging Persona**: Focuses on opportunities, positive framing, and solution-oriented advice.
* **Critical Persona**: Highlights risks, cautious planning, and challenge awareness.

Both models were fine-tuned with [LoRA (Low-Rank Adaptation)](https://arxiv.org/abs/2106.09685) for **parameter-efficient tuning** using instruction-response pairs reflecting each mindset.



## How to Run (Kaggle or Colab)

1. Upload your `career_encouraging.jsonl` and `career_critical.jsonl`
2. Run the LoRA fine-tuning script:

   ```python
   train_lora_model(tokenized_encouraging_dataset, "encouraging")
   train_lora_model(tokenized_critical_dataset, "critical")
   ```
3. Save trained models as `.zip` to reuse across sessions



## Key Learnings

* The **encouraging model** produces more solution-driven, optimistic guidance — often more human-like.
* The **critical model** holds its risk-focused framing well, but may struggle with contradictory prompts (e.g., being asked to be encouraging).