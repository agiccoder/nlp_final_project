# Financial Complaint Classification and Shortcut Robustness

**Authors:** Maksim Petrenko, Timur Khairislamov  
**Course:** Natural Language Processing in Python, HSE University  
**Submission type:** final project repository

## Project summary

This project studies whether financial complaint classifiers learn robust product-level patterns or mostly rely on surface lexical shortcuts. We compare:

1. **TF-IDF + Logistic Regression** as a strong classical baseline;
2. **Frozen DistilBERT embeddings + Logistic Regression** as a contextual embedding baseline without fine-tuning;
3. **Fine-tuned DistilBERT** as the main transformer model.

The evaluation goes beyond clean test accuracy. The notebook includes shortcut masking tests, calibration, selective prediction, retrieval-supported diagnostics, and comparative error analysis.

## Repository structure

```text
.
├── README.md
├── requirements.txt
├── final_project_shortcut_robustness_pipeline.ipynb
├── final_project_report.pdf
├── report/
│   ├── report.tex
│   └── report.pdf
├── data/
    ├── consumer_complaints_small.csv
│   └── README.md
├── artifacts_final/
│   ├── *.csv
│   ├── *.png
│   ├── config.json
└── └── final_results_summary.md

```

## Main files

- `final_project_shortcut_robustness_pipeline.ipynb` — full reproducible notebook with the experimental pipeline.
- `final_project_report.pdf` — 4-page two-column final report, placed in the repository root for submission.
- `report/report.tex` — LaTeX source for the report.
- `artifacts_final/` — exported figures, tables, summaries, and configuration files used in the report.
- `data/README.md` — data-source and local-data instructions.

## How to reproduce

Create an environment and install dependencies:

```bash
pip install -r requirements.txt
```

Then run the notebook:

```bash
jupyter notebook final_project_shortcut_robustness_pipeline.ipynb
```

The notebook first checks for a local CSV file in one of these locations:

```text
consumer_complaints_small.csv
../consumer_complaints_small.csv
data/consumer_complaints_small.csv
```

If the file is not found, it downloads the configured CSV from the URL inside the notebook.

## Expected outputs

A complete run writes outputs to `artifacts_final/`, including:

- standard performance tables;
- robustness results under product-cue and top-feature masking;
- calibration summaries;
- selective-prediction curves;
- retrieval-support diagnostics;
- selected error-analysis examples.

The current repository already contains the exported artifacts used in the report.
