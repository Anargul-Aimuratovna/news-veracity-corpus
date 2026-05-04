# Dataset Schema Description

## Overview

This document describes the structure of the Kazakh-Russian News Veracity Corpus.

The dataset is annotated using Label Studio and follows a multi-level annotation scheme combining document-level and span-level labels.

---

## Data Format

- Format: JSON
- Source: Label Studio export
- File: `data/corpus_labelstudio_export.json`

Each entry corresponds to one annotated news text.

---

## Core Field

- `text` — full news text

---

## Document-Level Annotation

The following fields are assigned to the entire document:

- `doc_label` — classification label:
  - `real`
  - `fake`

- `SOURCE_TYPE` — source of the text (e.g., social media, news outlet)

- `TIME_REF` — temporal reference (e.g., "today", "2025")

- `GEO_LOC` — geographic reference

- `TARGET_ENTITY` — main entity mentioned

- `confidence` — annotation confidence:
  - `low`
  - `medium`
  - `high`

- `notes` — justification of the decision

---

## Fake-Specific Fields

Available only when `doc_label = fake`:

### fake_news_type (multi-label)

- conspiracy_theory  
- fabricated_news  
- satire_or_parody  
- misleading_content  
- manipulated_content  
- false_context  
- false_connection  
- imposter_content  
- deepfake_synthetic_media  
- propaganda  
- advertising_disguised  
- hoax  
- rumor  

---

### author_intent

Free-text field describing the intention of the content (e.g., fear, manipulation, engagement).

---

## Span-Level Annotation

Annotated spans capture local disinformation markers.

Each span includes:

- text fragment (selected in UI)
- label (Level 2 subtype)

---

## Disinformation Markers

Markers are grouped into categories:

- clickbait  
- emotional_pressure  
- exaggeration  
- downplaying  
- scapegoating  
- misattribution  

Each category contains multiple Level 2 subtypes.

---