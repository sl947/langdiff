# Multilingual Disparities in LLM-Based Safety Judgments: Evidence from Brand Safety Applications.
This repository contains the code, prompts, and benchmark data accompanying our paper, “Multilingual Disparities in LLM-Based Safety Judgments: Evidence from Brand Safety Applications,” appearing at the 1st Workshop on Multilinguality in the Era of Large Language Models (MeLLMs) at ACL 2026.

## Contents

- `prompt_template.txt` - GARM Brand Safety Floor + Suitability prompt used for article ratings.
- `euronews_brand_safety_publication_dataset.jsonl.gz` - publication JSONL dataset, 70,381 article-language-model records. Each line includes article metadata, language, model, repeated runs, per-category agreement, and instability flags.
- `euronews_llm_ratings_consolidated_apr2.csv` - full row-level MiniMax ratings. Unit: article-language-model-run-category.
- `euronews_llm_ratings_consolidated_deepseek_1000.csv` - DeepSeek sample row-level ratings.
- `euronews_llm_ratings_consolidated_gemini_1000.csv` - Gemini sample row-level ratings.
- `out_reindexed_dedup_deepseek_sample_1000.jsonl` and `out_reindexed_dedup_gemini_sample_1000.jsonl` - run-level JSONL outputs for the sample robustness checks.
- `lang effect test, unconditional magnitude.ipynb` - unconditional language-disagreement analysis.
- `avg 3 run, conditional magnitute, run robust.ipynb` - conditional magnitude and robustness analysis.

## Data Notes
Copyright note: the release data intentionally excludes publisher article bodies.
Included article fields are limited to metadata such as title, URL, publication
dates, language, model, ratings, and reasoning traces.

Languages: `ar`, `de`, `el`, `en`, `es`, `fa`, `fr`, `hu`, `it`, `pl`, `pt`, `ru`, `tr`.

Main rating fields:

- `floor`: `safe` or `unsafe`
- `level`: `0`, `low`, `medium`, or `high`
- `category`: GARM brand-safety category
- `run_index`: repeated rating run
- `floor_agreement`, `level_agreement`, `unstable`: agreement/stability summaries across repeated runs

The full MiniMax CSV preserves raw model category strings, including a few typo variants of `obscenity_profanity` and `sensitive_social_issues` by the LLM model; the notebooks canonicalize these before analysis.

