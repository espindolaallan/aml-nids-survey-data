![Status: Preprint](https://img.shields.io/badge/status-preprint-blue)
![TechRxiv DOI](https://img.shields.io/badge/DOI-10.36227%2Ftechrxiv.176703966.68193688%2Fv1-blue)
![Data DOI](https://img.shields.io/badge/Data%20DOI-10.21227%2Fmdwb--bw29-blue)

# AML-NIDS Survey Data Companion

This repository packages the data companion for *“Understanding the Adversary: A Survey of Adversarial Machine Learning in Network Intrusion Detection”*.
![Methodology Pipeline](figures/survey_method.png)

Our corpus stems from the PRISMA-based workflow illustrated above: we queried six major digital libraries, deduplicated roughly 8,000 hits down to 4,259 unique records, filtered for venue quality, and manually screened titles, abstracts, and full texts. Progressing through identification, screening, eligibility, and inclusion yielded 94 peer-reviewed primary studies (plus 10 prior surveys) covering AML-for-NIDS research published between 2022 and early 2025.

![Adversary Profile](figures/adversary_profile.png)

Figure 2 encapsulates the five-axis adversary profile that anchors our survey: each study is characterized by its attack surface, attack phase, adversary position/access within the network, adversary knowledge assumptions, and adversary goal. Embedding these facets inside the ML-NIDS pipeline clarifies how adversarial leverage propagates from data acquisition through feature extraction to alerting, and provides a consistent frame for the quantitative analyses of RQ1–RQ3.

## Repository Layout
- `data/protocol/README.md` - guide to the protocol artifacts and screening-status summaries.
- `data/raw/taxonomy_mapping.csv` – master table encoding all 94 primary studies. Each row contains bibliographic metadata plus every taxonomy field.
- `data/protocol/` - screening and selection records:
  - `coding_guide.md`
  - `exclusion_log.csv`
  - `secondary_studies.csv`
  - `journals_venue_review_log.csv`
  - `conferences_venue_review_log.csv`
  - `unranked_venue_review_log.csv`
- Key CSVs:
  - `data/raw/taxonomy_mapping.csv` – master annotated primary-study table.
  - `data/exports/acronyms_table.csv` – acronym reference.
  - `data/exports/datasets_table.csv` – datasets list.
  - `data/exports/model_families_table.csv` – unified model families.
  - `data/exports/metrics_table_full.csv` – metrics list.
  - Per facet summaries in `data/derived/` (models, datasets, metrics, surfaces, phases, positions, knowledge, goals, attack/defense techniques, granularity, year, code/data).
- `figures/*.pdf` – Plots generated from the derived CSVs.
- `notebooks/SurveyPlots.ipynb` – Jupyter notebook that reads the CSVs and renders every figure from them.

## Column Dictionary (`taxonomy_mapping.csv`)
Each column describes one aspect of the AML-for-NIDS literature review:
- `Title`, `Paper`, `Year`, `Venue` – bibliographic metadata.
- `Dataset` – list of datasets leveraged (e.g., CIC-IDS-2017, UNSW-NB15, CSE-CIC-IDS-
2018).
- `Model type` – taxonomy of ML-NIDS models evaluated (e.g., Autoencoder, Tree-based, Generative).
- `NIDS granularity` – packet-based vs flow-based NIDS.
- `Surface` – attack surface targeted (network-level, feature-level, or data-level).
- `Phase` – lifecycle stage (training-time, inference-time, or continuous) where the adversary operates.
- `Position/Access` – attacker foothold such as external, insider-limited, or insider-privileged.
- `Knowledge` – black-box/gray-box/white-box assumptions.
- `Goal` – security objective impacted (integrity-evasion, integrity-poisoning, confidentiality, and combinations of these goals).
- `Attack technique` – method family (gradient, generative, heuristic, label-flipping, transfer, etc.).
- `Defense technique` – mitigation strategy (adversarial retraining, ensembles, sanitization, out-of-distribution detection, adversarial purification, etc.).
- Code/Data availability – indicates whether artifacts were released (Code+Data, Code-only, Data-only, or None).
- `Evaluation metrics` – metrics reported by the paper (e.g., Accuracy, Recall, ASR, Attack Severity).

### Snapshot of the Taxonomy Table
The unified taxonomy organizes the literature around a three-level core hierarchy: threat assumptions, method implementation, and outcome evaluation. These core layers are complemented by supporting context facets, such as models, datasets, and reproducibility markers, so conceptual assumptions can be connected to empirical practice across all 94 studies.

| Paper (short) | Year | Datasets | Model Types | Surface | Phase |
| --- | --- | --- | --- | --- | --- |
| Adversarial attacks against deep learning-based NIDS | 2022 | CSE-CIC-IDS-2018 | CNN; Feed-forward NN; Sequence/Temporal | Feature-level | Inference-time |
| Adversarial attacks against supervised ML-based NIDS | 2022 | CIC-IDS-2017 | Generative; Tree-based; Linear/Probabilistic | Data-/Feature-level | Training & Inference |
| Black-box attack and NIDS using ML for malicious traffic | 2022 | Kitsune-Mirai; CIC-IDS-2017; MAWILab; UNSW-NB15 | Anomaly-detection; Autoencoder; Feed-forward NN; Generative; Linear/Probabilistic; Sequence/Temporal | Network-level | Inference-time |

The complete table is available at [`data/raw/taxonomy_mapping.csv`](data/raw/taxonomy_mapping.csv).
Field-level coding guidance is documented in [`data/protocol/coding_guide.md`](data/protocol/coding_guide.md).

## Citation


If you leverage these artifacts, please cite the data companion:

> A. da S. Espindola, A. O. Santin, A. Casimiro, P. M. Ferreira, and E. K. Viegas, “AML-NIDS Survey Data Companion”. Data DOI: 10.21227/mdwb-bw29

The accompanying manuscript can be cited separately:

> A. da S. Espindola, A. O. Santin, A. Casimiro, P. M. Ferreira, and E. K. Viegas, “Understanding the Adversary: A Survey of Adversarial Machine Learning in Network Intrusion Detection”, TechRxiv preprint (2025). DOI: 10.36227/techrxiv.176703966.68193688/v1
