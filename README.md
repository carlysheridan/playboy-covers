# Playboy Cover Archive — Speculative Cover Generator

**815 covers · 1953–2020 · Open source dataset**

This project uses a digitized archive of *Playboy* magazine covers as a dataset for investigating how AI image generation models reproduce, extrapolate, and fail to escape the visual logic of historical media.

The five-year publishing gap (2020–2025) is treated as a methodological opening. By prompting image generation models to produce covers for years that never existed, we generate evidence of what those models have learned to expect and what they cannot imagine, regardless of instruction.

---

## How it works

Cover images were scraped directly from the Playboy digital archive and passed to Claude (Anthropic) to generate structured visual descriptions across 15 fields: clothing, pose, expression, mood, color palette, cultural context, and more. That AI-generated metadata became the dataset.

Dominant visual patterns were extracted using frequency analysis and assembled into image prompts using weighted random selection with no LLM interpretation, no editorial judgment. The prompt is a direct transcription of the archive's own statistics. The weights mean the most common values win most often, but not always, reflecting the real distribution rather than hardcoding the modal value every time.

```
Playboy archive  →  Claude Vision  →  Frequency analysis  →  Weighted prompt  →  Image generation
(cover images)      (15-field           (pandas / Counter)    (pure Python,        (FLUX.1-schnell
                     metadata)                                  no LLM)              or SDXL)
```

---

## Dataset

The published dataset contains AI-generated metadata only. Original cover images are not included due to copyright restrictions.

| Field | Value |
|---|---|
| Total covers | 815 |
| Date range | December 1953 – December 2020 |
| Metadata fields | 15 per cover |
| Format | CSV |

**Fields:** Year · Date · Price · Archive URL · Colors · Cultural Context · Caption · Clothing · Hair · Pose · Expression · Mood · Era Indicators · Issue ID · Decade

---

## Copyright note

Original Playboy cover images are the intellectual property of Playboy Enterprises and are not included in this repository. The AI-generated metadata are published under the [MIT License](LICENSE).

---

## Citation

If you use this dataset or build on this work:

```
Sheridan, C. & Gomez, R. (2026). Playboy Cover Archive — Speculative Cover Generator.
MA Applied AI for Art & Design, Elisava Barcelona.
```
---

*MA Applied AI for Art & Design · Elisava Barcelona · 2026*
