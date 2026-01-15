
# 🛡️ Leveraging Large Language Models for Dual-Purpose Dataset Expansion and Abuse Detection in Social Media

This repository contains the implementation and experiments for an MSc Artificial Intelligence dissertation project. The work focuses on building a reproducible pipeline for multi-class online abuse detection using a unified 10-class taxonomy. Multiple public datasets are consolidated into a single label space, label provenance is retained, and transformer-based classifiers are evaluated under controlled experimental settings.

## 🧠 Pipeline Overview

1. Collect public datasets from official sources (e.g., Kaggle and associated public repositories).
2. Inspect datasets and apply inclusion and exclusion checks (remove unsuitable sources, missing text, and duplicates).
3. Standardise datasets into a unified schema (e.g., text and dataset source fields).
4. Define a unified 10-class taxonomy (5 toxic + 5 non-toxic categories).
5. Map original labels and signals into the unified taxonomy using transparent rule-based logic.
6. Apply LLM-assisted annotation to refine selected non-toxic samples into finer non-toxic subcategories, with constrained outputs and stored provenance.
7. Clean and normalise text (encoding fixes, whitespace standardisation, and noise removal).
8. Balance the dataset and create stratified train/validation splits while preserving dataset-source and label-source provenance.
9. Fine-tune transformer classifiers using consistent training settings.
10. Evaluate performance using accuracy and macro-F1 and compare outcomes across experiments.

## 📁 Repository Contents

This repository is organised as notebooks to support clarity and reproducibility:

- `Dataset_preparing.ipynb`  
  Dataset collection, inspection, cleaning, label mapping, LLM-assisted refinement, and final dataset construction.

- `Experiment_1.ipynb`  
  Source-restricted training and evaluation to analyse dataset-origin effects.

- `experiment_2.ipynb`  
  Architecture comparison under identical training conditions.

- `experiment_3.ipynb`  
  Final combined training and model selection.

- `Visualizations.ipynb`  
  Visual analysis and figures used for reporting results.

## 🏷️ Unified 10-Class Taxonomy

Toxic classes:
- `sexual_harassment`
- `cyberbullying`
- `hate_speech`
- `abusive_violence`
- `other_toxic`

Non-toxic classes:
- `non_sexual`
- `non_cyberbullying`
- `motivational_non_hate`
- `non_abusive_violence`
- `generic_neutral`

## 🔧 Installation

Clone the repository and set up a Python virtual environment.

```bash
git clone https://github.com/Malavika-Pramod173/MS_AI_Dissertation_Toxic_Behaviour.git
cd MS_AI_Dissertation_Toxic_Behaviour

conda create -n abuse-detection python=3.10 -y
conda activate abuse-detection

pip install -r requirements.txt

```
## 📄 Dataset Notice

This repository does not redistribute third-party datasets. The datasets used in this dissertation were obtained from public sources and remain subject to their original licenses and terms. To reproduce the experiments, users should download the datasets independently and follow the preprocessing steps provided in `Dataset_preparing.ipynb`.

Recommended practice:
- Store datasets locally (e.g., `data/raw/` and `data/processed/`)
- Avoid committing dataset files (CSV) to GitHub

## 📊 Experiments and Evaluation

Three controlled experiments are included:
- Experiment 1 analyses dataset source effects using source-restricted training.
- Experiment 2 compares transformer architectures under identical settings.
- Experiment 3 trains models on the final combined dataset for model selection.

Evaluation metrics:
- Accuracy
- Macro-F1

## 📤 Output

The notebooks in this repository produce the following outputs:

- Cleaned and unified datasets with preserved label and dataset provenance
- Trained transformer-based classification models (stored locally during experimentation)
- Evaluation results including accuracy and macro-F1 scores
- Visualisations such as class distributions and performance comparisons used for analysis and reporting

All outputs are generated during notebook execution and are not committed to the repository.

## 🏋️ Training

Model training is conducted within the experiment notebooks using transformer-based architectures. Fine-tuning is performed on the prepared unified dataset under controlled and consistent settings across experiments. Training procedures are designed to support fair comparison between models and to analyse the impact of dataset composition and annotation strategies.

## ⚖️ Ethical Considerations

No primary data from human participants is collected. Only publicly available datasets are used under their published terms. LLM assistance is applied in a controlled and transparent manner with provenance tracking.

## 📌 Citation

Malavika Pramod (2026). Leveraging Large Language Models for Dual-Purpose Dataset Expansion and Abuse Detection in Social Media. MSc Dissertation, Sheffield Hallam University.
