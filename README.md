# Multilingual Disparities in LLM-Based Safety Judgments: Evidence from Brand Safety Applications.
This repository contains code, prompts, and benchmark data for paper, “Multilingual Disparities in LLM-Based Safety Judgments: Evidence from Brand Safety Applications.”

## Contents

- `prompt_template.txt` - GARM Brand Safety Floor + Suitability prompt used for article ratings.
- `euronews_brand_safety_publication_dataset.jsonl.gz` - publication JSONL dataset, 70,381 article-language-model records. Each line includes article metadata, language, model, repeated runs, per-category agreement, and instability flags.
- `euronews_llm_ratings_consolidated_apr2.csv` - full row-level MiniMax ratings, 3,163,492 rows. Unit: article-language-model-run-category.
- `euronews_llm_ratings_consolidated_deepseek_1000.csv` - DeepSeek sample row-level ratings, 301,410 rows.
- `euronews_llm_ratings_consolidated_gemini_1000.csv` - Gemini sample row-level ratings, 301,365 rows.
- `out_reindexed_dedup_deepseek_sample_1000.jsonl` and `out_reindexed_dedup_gemini_sample_1000.jsonl` - run-level JSONL outputs for the sample robustness checks.
- `lang effect test, unconditional magnitude.ipynb` - unconditional language-disagreement analysis.
- `avg 3 run, conditional magnitute, run robust.ipynb` - conditional magnitude and robustness analysis.

## Data Notes

Languages: `ar`, `de`, `el`, `en`, `es`, `fa`, `fr`, `hu`, `it`, `pl`, `pt`, `ru`, `tr`.

Main rating fields:

- `floor`: `safe` or `unsafe`
- `level`: `0`, `low`, `medium`, or `high`
- `category`: GARM brand-safety category
- `run_index`: repeated rating run
- `floor_agreement`, `level_agreement`, `unstable`: agreement/stability summaries across repeated runs

The full MiniMax CSV preserves raw model category strings, including a few typo variants of `obscenity_profanity` and `sensitive_social_issues`; the notebooks canonicalize these before analysis.

