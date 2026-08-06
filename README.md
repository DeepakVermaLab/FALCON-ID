# FALCON-ID

FALCON-ID is a federated learning intrusion-detection research package organized from the linked Google Drive/Colab material. The repository is notebook-first and contains the runnable experiment notebooks, small result summaries, and supporting EDA reports.

## Scope

The project covers:

- Exploratory analysis for CSE-CIC-IDS2018, CIC-IIoT-2025, and CIC-BCCC-NRC-IoMT-2024.
- Dataset preprocessing with autoencoder feature generation and combined dataset building.
- Non-IID client dataset construction for federated learning simulation.
- Local IDS modeling with CNN + BiLSTM.
- Federated learning baselines and the FALCON-ID federated learning engine.
- Client clustering and specialized federated learning.
- Personalized federated learning with FedProx and local fine-tuning.
- Differential privacy, secure aggregation, final result tables, and energy-aware simulation.

## Repository Structure

```text
FALCON-ID/
├── EDA/                         # EDA notebooks and reports
├── PREPROCESSING/               # Dataset preprocessing notebooks
├── CLIENT_DATASET_BUILDER/      # Non-IID client builder notebooks
├── IMPLEMENTATION/              # Core modeling and FALCON-ID notebooks
├── RESULTS/                     # Final result notebooks and small artifacts
├── SIMULATION/                  # Energy-aware FL simulation notebook
├── docs/                        # Source link manifest
├── requirements.txt
└── PROJECT_STRUCTURE.md
```

## Setup

Create an environment and install dependencies:

```bash
cd /users/
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

Set dataset and output roots before running notebooks locally:

```bash
export FALCON_ID_DATASET_ROOT="/users/"
export FALCON_ID_OUTPUT_ROOT="/users/"
```

The notebooks were prepared from Colab material and any hard-coded local/Drive paths were sanitized to `/users/`.

## Notebook Run Order

Recommended execution order:

1. `EDA/notebooks/CSE_CIC_IDS2018_EDA.ipynb`
2. `EDA/notebooks/CIC_IIoT_2025_EDA.ipynb`
3. `EDA/notebooks/CIC_BCCC_NRC_IoMT_2024_EDA.ipynb`
4. `PREPROCESSING/notebooks/01_CSE_CIC_IDS2018_PREPROCESSING.ipynb`
5. `PREPROCESSING/notebooks/02_CIC_IIoT_2025_PREPROCESSING.ipynb`
6. `PREPROCESSING/notebooks/03_CIC_BCCC_NRC_IoMT_2024_PREPROCESSING.ipynb`
7. `PREPROCESSING/notebooks/04_COMBINED_DATASET_BUILDER.ipynb`
8. `CLIENT_DATASET_BUILDER/notebooks/01_CSE_CIC_IDS2018_CLIENT_BUILDER.ipynb`
9. `CLIENT_DATASET_BUILDER/notebooks/02_CIC_IIoT_2025_CLIENT_BUILDER.ipynb`
10. `CLIENT_DATASET_BUILDER/notebooks/03_CIC_BCCC_NRC_IoMT_2024_CLIENT_BUILDER.ipynb`
11. `CLIENT_DATASET_BUILDER/notebooks/04_COMBINED_CLIENT_BUILDER.ipynb`
12. `IMPLEMENTATION/notebooks/01_DATASET_LOADER_EDA_SUMMARY_IMPORT.ipynb`
13. `IMPLEMENTATION/notebooks/02_LOCAL_IDS_MODEL_CNN_BILSTM.ipynb`
14. `IMPLEMENTATION/notebooks/03_FEDERATED_LEARNING_BASELINE.ipynb`
15. `IMPLEMENTATION/notebooks/04_FALCON_ID_FEDERATED_ENGINE.ipynb`
16. `IMPLEMENTATION/notebooks/05_CLIENT_CLUSTERING_SPECIALIZED_FL.ipynb`
17. `IMPLEMENTATION/notebooks/06_PERSONALIZED_FL_FEDPROX_LOCAL_FINETUNING.ipynb`
18. `IMPLEMENTATION/notebooks/07_DIFFERENTIAL_PRIVACY_SECURE_AGGREGATION.ipynb`
19. `RESULTS/notebooks/01_FINAL_RESULTS_TABLES_COMPARISONS.ipynb`
20. `RESULTS/notebooks/02_FINAL_RESULTS.ipynb`
21. `SIMULATION/notebooks/01_ENERGY_AWARE_FL_SIMULATION.ipynb`

Additional exploratory notebooks are kept in `IMPLEMENTATION/notebooks/08_*`, `09_*`, `10_*`, and `99_*`.

## Data and Artifacts

Raw datasets and preprocessed datasets are not stored in this repository because they are large. Model binaries are also excluded from Git history. Source Drive links and file IDs are recorded in:

```text
docs/source_links.json
```

Small result summaries are included under `RESULTS/`.

## Validation

Before upload, notebooks were normalized and checked with `nbformat`; JSON and CSV files were parsed; and old local or Drive-specific path prefixes were replaced with `/users/`.
