# WB Social Listening — Multi-Country Datasets (Pilot)

This repository contains pilot datasets used for social listening analysis across three country contexts:

- **Nigeria:** BBNaija Season 9 discourse (Nairaland; optional TikTok lens)
- **India:** Made in Heaven Season 2 discourse (YouTube comments)
- **Kenya:** Real Housewives of Nairobi discourse (Twitter/X posts)

The goal of these datasets is to support analysis of **gender norms**, **economic empowerment**, and related social narratives through public online conversation.

---

## What’s inside

Each country folder may include the following dataset stages:

1. **Raw**
   - Original collected data in a minimally processed form.

2. **Standardized**
   - Same schema style across countries (consistent column names + basic metadata).

3. **Cleaned**
   - Text cleaned (e.g., URLs removed, whitespace normalized), duplicates removed, and language tags added where applicable.

4. **Filtered / Candidate Set**
   - High-recall keyword filtering used to capture likely relevant content.

5. **Analysis-Ready**
   - Final curated subset used for coding and analysis (e.g., top-N selection for reproducibility).

---

## Columns (high-level)

Common metadata fields (where available):
- `platform`, `country`
- `created_at` / `timestamp`
- `text` (raw and/or cleaned)
- engagement fields (likes, replies, etc.) when available

Platform-specific fields may include:
- **Nairaland:** `post_id`, `parent_post_id`, `tier`
- **YouTube:** `video_id`, `comment_id`
- **Twitter/X:** `tweet_id`, `author_handle`

---

## Notes on language

- **Nigeria:** English + Nigerian Pidgin and other local markers may appear.
- **India:** English + Hinglish/Hindi tokens may appear (often in Latin script).
- **Kenya:** English dominates with some Swahili/Sheng mixing.

Language tags (if present) are descriptive and not strict exclusions.

---

## Ethics & responsible use

These datasets are derived from publicly available online content.  
Please use responsibly:

- Do not attempt to identify or contact individual users.
- Avoid quoting verbatim text in publications when it could enable re-identification.
- Treat the content as sensitive social data, even when public.
- Respect platform terms of service and local privacy expectations.

---

## Limitations

- The datasets are **pilot / sample-based** and may not represent all public discourse.
- Engagement metadata may be incomplete depending on platform access.
- Some records may contain slang, sarcasm, or coded language that requires contextual interpretation.

---

## Citation

If you reference this dataset, cite it as:

**WB Social Listening — Multi-Country Datasets (Pilot), 2024–2025.**

---

## Contact

For questions about structure, columns, or sampling choices, open an issue in this repo.


