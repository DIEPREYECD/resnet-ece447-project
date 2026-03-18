# resnet-ece447-project

A deep-learning project exploring ResNet architectures for ECE 447.

## Repository Structure

```
resnet-ece447-project/
├── README.md               # This file
├── .gitignore
├── report/                 # LaTeX report
│   ├── main.tex            # Top-level document
│   ├── refs.bib            # Bibliography
│   ├── sections/           # One .tex file per section
│   ├── figures/            # Figures included in the report
│   ├── tables/             # Table files included in the report
│   └── appendix/           # Appendix material
├── slides/
│   └── presentation.tex    # Beamer presentation slides
├── code/                   # Experiment code
│   ├── data/               # Raw and processed datasets (not tracked by git)
│   ├── models/             # Model definitions
│   ├── scripts/            # Training / evaluation scripts
│   ├── notebooks/          # Jupyter notebooks for exploration
│   ├── outputs/            # Model outputs (not tracked by git)
│   └── requirements.txt    # Python dependencies
├── results/                # Outputs from experiments
│   ├── plots/              # Generated figures and plots
│   ├── logs/               # Training logs
│   └── checkpoints/        # Saved model checkpoints (not tracked by git)
└── docs/
    └── project_notes.md    # Running notes and meeting summaries
```

## How to Run the Code

### 1. Set up the environment

```bash
cd code
pip install -r requirements.txt
```

### 2. Prepare data

Place (or symlink) your dataset under `code/data/`.

### 3. Train a model

```bash
python code/scripts/train.py
```

### 4. Evaluate a model

```bash
python code/scripts/evaluate.py
```

### 5. View results

Generated plots are saved to `results/plots/`, training logs to `results/logs/`, and model checkpoints to `results/checkpoints/`.

## Building the Report

```bash
cd report
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

The output PDF is written to `report/main.pdf`.

### CI-compiled PDF

Every push or pull request that touches `report/` automatically compiles the report
via GitHub Actions.  Once the **Compile LaTeX Report** workflow succeeds you can
download the compiled PDF from the run's **Artifacts** section:

1. Open the repository on GitHub and click the **Actions** tab.
2. Select the latest **Compile LaTeX Report** run.
3. Scroll to the **Artifacts** section at the bottom of the run summary.
4. Download the **`report-pdf-run123`** zip (where `123` is the run number) — it contains `main.pdf`.

## Building the Slides

```bash
cd slides
pdflatex presentation.tex
```