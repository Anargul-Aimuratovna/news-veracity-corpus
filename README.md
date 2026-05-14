# A Bilingual Kazakh-Russian News Veracity Corpus

This repository contains a bilingual Kazakh-Russian news veracity corpus for automatic fake news detection, disinformation analysis, and interpretable NLP research.

---

## What's New (v2.0)

The corpus has been significantly expanded and refined based on reviewer feedback:

- **Dataset size increased to 280 texts** (up from an initial pilot of 21 labeled texts)
- **Real debunked fake-news examples added**: FAKE-class texts were prepared based on debunked fake messages and fact-checking materials from Kazakhstan-related sources, including Factcheck.kz.
- **Source diversity expanded**: REAL-class texts now cover three major Kazakhstani news outlets across both Kazakh and Russian languages.
- **Bilingual coverage improved**: both Kazakh and Russian texts are represented in both FAKE and REAL classes.
- **Corpus format**: exported from Label Studio as JSON (`external_validation_set.json`)

---

## Overview

To construct the research corpus, a multi-level annotation scheme for news texts was developed for the task of automatic detection of reliable and unreliable content.

The scheme combines **document-level** and **span-level** annotation, enabling both global classification and fine-grained analysis of disinformation markers.

---

## Annotation Structure

### Document-Level Annotation

Each text is annotated with:

| Field | Description |
|-------|-------------|
| `SOURCE_TYPE` | Source type (social media, news outlet, messenger, etc.) |
| `TIME_REF` | Temporal reference of the claim |
| `GEO_LOC` | Geographic location |
| `TARGET_ENTITY` | Target entity of the claim |
| `doc_label` | `real` / `fake` |
| `confidence` | Annotator confidence score |
| `notes` | Justification for the label |

---

### Fake-Specific Annotation

For texts labeled as `fake`, additional labels are provided:

**`fake_news_type`** (multi-label):

| Type | Description |
|------|-------------|
| `conspiracy_theory` | Claims of hidden actors or secret plans |
| `fabricated_news` | Entirely invented stories |
| `misleading_content` | True facts presented in a misleading context |
| `propaganda` | Content promoting a political agenda |
| `hoax` | Deliberately deceptive content |
| `rumor` | Unverified circulating claims |

---

### Author Intent

Fake news texts are additionally annotated with `author_intent`:

| Intent | Description |
|--------|-------------|
| `fear` | Intended to provoke fear or panic |
| `distrust` | Intended to undermine trust in institutions |
| `anger` | Intended to provoke anger or outrage |
| `agenda_promotion` | Intended to promote a specific viewpoint |
| `engagement` | Intended to maximize sharing and virality |

---

### Span-Level Annotation

Span-level annotation captures local markers of disinformation at the token/phrase level.

Marker groups include:

| Group | Description |
|-------|-------------|
| `clickbait` | Sensational or misleading headlines/phrases |
| `emotional_pressure` | Language designed to provoke emotional response |
| `exaggeration` | Claims that overstate facts |
| `downplaying` | Claims that minimize or dismiss facts |
| `scapegoating` | Blaming specific groups without evidence |
| `misattribution` | False attribution of quotes or actions |

Each group is represented by fine-grained Level 2 subtypes.

---

## Dataset Format

- **Format**: JSON
- **File**: `external_validation_set.json`
- **Encoding**: UTF-8
- **Structure**: simplified JSON format for classification experiments

### JSON Schema

```json
[
  {
    "№": "1",
    "TEXT": "Original text of the news item",
    "Language": "RU",
    "Source": "Factcheck.kz",
    "Class": "FAKE"
  }
]
```

| Field | Type | Values |
|-------|------|--------|
| `№` | string | Sequential number (1–280) |
| `TEXT` | string | Raw text of the news item |
| `Language` | string | `RU` / `KZ` |
| `Source` | string | Source outlet name |
| `Class` | string | `FAKE` / `REAL` |

---

## Languages

| Language | Code | Script |
|----------|------|--------|
| Kazakh | KZ | Cyrillic |
| Russian | RU | Cyrillic |

---

## Intended Use

This corpus is designed to support:

- Binary fake news classification (FAKE / REAL)
- Cross-lingual fake news detection
- Multilabel disinformation type classification
- Span-level disinformation marker detection
- Ablation studies on annotation granularity
- Cross-domain generalization experiments

---

## Limitations

- The corpus covers primarily Kazakhstani news topics; cross-national generalization may be limited.
- Fake texts are sourced from fact-checking platforms, which may introduce a selection bias toward more viral or high-impact disinformation.
- Span-level annotations are subjective and reflect individual annotator interpretation.
- The dataset may not fully represent all domains of disinformation circulating in Kazakhstan.

---

## License

This dataset is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**.


---

## Disclaimer

This dataset may contain subjective annotations and potential biases inherent to the sources from which texts were collected. The authors are not responsible for misuse or misinterpretation of the data. All fake news texts are included solely for research purposes.

---

## Dataset Schema

![Schema](images/KazFakeCorpus_2.png)
