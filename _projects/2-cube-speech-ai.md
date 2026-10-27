---
layout: page
title: Speech AI & Data Pipelines — 2 Cube Global
description: Curating domain speech data and evaluating adaptation versus zero-shot synthesis for multilingual supply-chain applications.
img:
importance: 4
category: engineering
---

**From paired audio and transcripts to a practical model comparison**

At 2 Cube Global, I worked on multilingual text-to-speech for supply-chain applications. My work connected data preparation with model adaptation and evaluation: turn domain recordings into usable training examples, adapt a speech model, and assess whether that adaptation was worthwhile compared with a zero-shot alternative.

**Role:** AI Engineer Intern | ML Data Pipelines & Evaluation.<br>
**Dates:** May–September 2025.<br>
**Location:** Los Angeles, CA.

## The problem

Domain adaptation depends on reliable audio–text pairs. When a transcript does not match its audio, the example becomes a poor training signal and makes evaluation less trustworthy. At the same time, adapting a model introduces data-preparation and training costs, so the model decision needs to account for both output quality and cost.

## Data curation and validation

I built **Python and Librosa pipelines** to process paired recordings and transcripts into aligned utterances for model adaptation and evaluation. The workflow connected audio processing, audio–text alignment validation, and filtering of mismatched samples.

| Data preparation measure               | Result        |
| -------------------------------------- | ------------- |
| Paired audio and transcripts processed | **80+ hours** |
| Aligned utterances produced            | **45K**       |
| Misaligned samples filtered            | **16%**       |

This work made data quality an explicit part of the modeling workflow. The curated domain data supported adaptation, while validation helped keep mismatched examples from distorting the model comparison.

## Model adaptation and evaluation

I adapted **F5-TTS** on the curated domain data and benchmarked it against **zero-shot Qwen3-TTS** for multilingual supply-chain speech.

| Approach                      | What the comparison examined                                                  |
| ----------------------------- | ----------------------------------------------------------------------------- |
| F5-TTS adapted on domain data | The value of investing in curation and model adaptation for the application   |
| Zero-shot Qwen3-TTS           | The quality–cost trade-off of a model used without domain-specific adaptation |

The evaluation informed technology selection by considering speech quality alongside cost. It connected the data pipeline to a practical engineering question: when does domain adaptation justify the additional work?

## My contribution

- Built the audio and transcript curation and validation pipelines.
- Prepared aligned domain utterances and filtered misaligned examples.
- Adapted F5-TTS and benchmarked it against a zero-shot Qwen3-TTS baseline.
- Evaluated quality–cost trade-offs to inform the team's technology choice.

**Stack:** Python, Librosa, F5-TTS, and Qwen3-TTS.

[Experience]({{ '/experience/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
