# Coding Guide

This guide documents the released corpus table in [`../raw/taxonomy_mapping.csv`](../raw/taxonomy_mapping.csv).

## Record Metadata

| Release column | Cardinality | Purpose | Guidance |
| --- | --- | --- | --- |
| `Title` | single-value | Full paper title as released in the public corpus table. | Free-text title string. |
| `Paper` | single-value | Short citation-style identifier used across tables and figures. | Free text such as `Smith et al. 2024`. |

## Supporting Context Facets

| Release column | Cardinality | Purpose | Guidance |
| --- | --- | --- | --- |
| `Year` | single-value | Chronological placement for filtering and trend analysis. | Four-digit publication year. |
| `Venue` | single-value | Publication venue used for venue-quality handling and venue statistics. | Short venue name or acronym such as `COSE`, `TIFS`, or `arXiv`. |
| `Dataset` | multi-select | Dataset family or benchmark used to instantiate the study. | Semicolon-separated benchmark names as released in the public table, such as `CIC-IDS-2017`, `UNSW-NB15`, `ToN-IoT`, or `Custom capture`. |
| `Model type` | multi-select | Model family targeted, attacked, or defended in the study. | Semicolon-separated released model-family labels such as `CNN`, `Tabular NN`, `Graph-based NN`, `Custom IDS-specific NN`, or `Unknown`. |
| `NIDS granularity` | mostly single-value | Detector granularity used by the evaluated NIDS. | Usually `Packet-based` or `Flow-based`. A small number of released rows retain the combined label `Packet-based, Flow-based`. |

## Threat Assumptions

| Release column | Cardinality | Purpose | Guidance |
| --- | --- | --- | --- |
| `Surface` | mostly single-value | Where the adversarial manipulation acts. | Usually `Network-level`, `Feature-level`, or `Data-level`. A small number of rows retain combined labels such as `Data-level; Feature-level` or `Feature-level; Network-level`. |
| `Phase` | mostly single-value | When the attack or defense acts in the ML lifecycle. | Usually `Training-time`, `Inference-time`, or `Continuous`. One released row retains `Training-time; Inference-time`. |
| `Position/Access` | mostly single-value | Attacker foothold or operational access. | Usually `External`, `Insider limited`, or `Insider privileged`. One released row retains `Insider limited; Insider privileged`. |
| `Knowledge` | mostly single-value | How much the attacker knows about the target. | Usually `Black-box`, `Gray-box`, or `White-box`. A few rows retain combined labels such as `Gray-box; White-box` or `White-box; Black-box`. |
| `Goal` | mostly single-value | Security objective affected by the study. | The released corpus uses `Integrity-Evasion`, `Integrity-Poisoning`, and `Confidentiality`. A few rows retain combined goals such as `Integrity-Poisoning; Integrity-Evasion`. |

## Method Implementation

| Release column | Cardinality | Purpose | Guidance |
| --- | --- | --- | --- |
| `Attack technique` | multi-select | Attack family implemented under the stated assumptions. | Semicolon-separated released attack labels such as `Gradient-based`, `Surrogate/Transfer-based`, `Generative/Learning-based`, `Heuristic/Search-based`, `Zeroth-order`, `Boundary-based`, `Label-flipping`, `Morphing/Obfuscation`, and `Unknown`. The public table also preserves a few legacy variants such as `Generative/Learning` and `Surrogate/Transfer`. |
| `Defense technique` | multi-select | Defense family implemented under the stated assumptions. | Semicolon-separated released defense labels, or `None` when no defense is proposed. The release vocabulary includes values such as `Adversarial retraining`, `Ensemble`, `OOD detector`, `Robust training`, `Feature squeezing`, `Poisoned data detection`, `Adversarial purification`, `Differential Privacy`, `Adversarial detection`, `Feature engineering`, and a few retained legacy variants such as `Label Sanitization`, `Label sanitization`, `Secure MLOps (discussion only)`, and `Self-normalization`. |

## Outcome Evaluation

| Release column | Cardinality | Purpose | Guidance |
| --- | --- | --- | --- |
| `Code/Data availability` | single-value | Artifact availability marker used as a reproducibility signal. | `Code+Data`, `Code-only`, `Data-only`, or `None`. |
| `Evaluation metrics` | multi-select | Metrics used to quantify attack success, defense performance, or robustness. | Semicolon-separated reported metrics as released in the public table. The release preserves paper-level acronyms and spellings such as `Accuracy`, `Precision`, `Recall`, `F1`, `AUC`, `ASR`, `FPR`, `Detection Latency`, `Privacy loss`, and `MRR (Misclassification Reduction Rate)`. |
