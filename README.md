# KazFakeCorpus: A Bilingual Kazakh-Russian News Veracity Corpus

A bilingual dataset for fake news detection in Kazakh and Russian, developed as part of a research study on automatic veracity classification of news texts.

---

## Repository Structure

```
news-veracity-corpus/
├── data/
│   ├── corpus_labelstudio_export.json   # Main annotated corpus (Label Studio export)
│   └── external_validation_set.json     # External validation set (added in v2.0)
├── images/
│   └── KazFakeCorpus_2.png              # Annotation schema diagram
├── label_studio_config.xml              # Label Studio annotation configuration
├── schema_description.md                # Full annotation schema documentation
└── README.md
```

---

## Data Files

### corpus_labelstudio_export.json
The main corpus exported from Label Studio. Contains fully annotated texts with document-level and span-level annotation. Full schema is described in `schema_description.md`.


## Annotation

The main corpus uses a multi-level annotation scheme combining document-level labels (veracity class, fake news type, author intent) and span-level disinformation markers (clickbait, emotional pressure, exaggeration, scapegoating, misattribution). Full details are provided in `schema_description.md`.

![Annotation Schema](images/KazFakeCorpus_2.png)

---

## License

This dataset is released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**.  

---

## Citation

If you use this dataset, please cite the accompanying paper.

---

## Disclaimer

The dataset may contain subjective annotations. All fake news texts are included solely for research purposes. The authors are not responsible for misuse of the data.
