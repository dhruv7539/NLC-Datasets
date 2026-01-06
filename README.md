# WB Social Listening — Multi-Country Datasets (Pilot)

This repository contains pilot datasets for social listening analysis across three country contexts:

- **Nigeria:** BBNaija Season 9 discourse (forum conversation corpus; optional short-video reach lens)  
- **India:** Made in Heaven Season 2 discourse (video-comment corpus)  
- **Kenya:** Real Housewives of Nairobi discourse (microblogging corpus; optional reach lens)

The datasets support analysis of gender norms, women’s economic empowerment, and related social narratives through public online conversation.

---

## Dataset Stages (shared convention)

Each country folder may contain one or more dataset “stages.” Not every country has every stage, but naming follows the same logic:

**1) Raw (source extract)**  
Minimally processed platform output retained for traceability. Raw files preserve original fields as collected.

**2) Standardized (schema-aligned)**  
Raw platform fields mapped into a consistent structure across countries (common metadata + text fields). If a platform does not provide stable identifiers, internal IDs may be assigned during this step.

**3) Cleaned (meaning-preserving normalization)**  
Light text normalization applied to improve downstream analysis while preserving meaning:
- URL stripping  
- whitespace normalization  
- casing normalization (where applicable)  
Emojis, slang, and code-switching tokens are retained because they often encode tone and cultural context.

**4) Candidate / Shortlist (relevance filtering)**  
A high-recall shortlist of likely relevant records produced using one or both of:
- **keyword family matching** (rule-based)  
- **semantic similarity filtering** (embedding-based relevance seeded by a curated query)  

This stage is intentionally permissive to reduce false negatives; precision is tightened downstream.

**5) Analysis-Ready (final subset for coding/analysis)**  
Final curated subset used for human/LLM coding and summary analysis (e.g., fixed Top-N or calibrated threshold selection for reproducibility), with any derived labels stored as additional columns.

---

## Columns (high-level)

Common fields may include (depending on platform availability):
- `country`, `platform`
- timestamp / created time (if available)
- raw and/or cleaned text fields
- optional engagement fields (e.g., views/likes/replies/shares when available)
- optional source context fields (e.g., thread/video/post URLs, query/hashtag seed)

Platform-specific identifiers vary by source. When available, datasets store stable source IDs; otherwise, stable internal IDs are assigned at standardization time.

---

## Language Notes

Content may include mixed-language and informal registers. Language tags (if present) are descriptive and used for sampling balance and error analysis rather than strict exclusion.

---

## Tools & Collection Workflow (high level)

Data collection and processing used a combination of:
- **Apify** actors (for programmatic extraction where applicable)  
- **Python** scripts for cleaning, deduplication, sampling, and dataset assembly  
- **Selenium WebDriver** (used only where needed) to support query-seeded discovery or extraction in cases where direct scraping/export was not available  
- Standard data tooling for tabular processing and reproducible exports  

Exact discovery queries / seed banks and platform-specific extraction settings are versioned separately (linked in project documentation).

---

## Responsible Use & Ethics

These datasets are derived from publicly available online content. Please use responsibly:
- Do not attempt to identify or contact individual users.
- Avoid quoting verbatim text in ways that enable re-identification.
- Treat public content as sensitive social data, even when public.
- Respect platform terms of service and local privacy expectations.

---

## Limitations

- Pilot/sample-based datasets may not be nationally representative.
- Engagement metadata can be incomplete or inconsistent across platforms.
- Sarcasm, slang, and coded language may require contextual interpretation.
- Cross-platform comparability is limited by platform norms and data access differences.

---

## Citation

If referencing this dataset, cite as:  
**WB Social Listening — Multi-Country Datasets, 2024–2025.**

---

## References / Acknowledgements

- Apify (data extraction platform)  
- Python (data processing and analysis)  
- Selenium WebDriver (automation used where required for discovery/extraction)  
