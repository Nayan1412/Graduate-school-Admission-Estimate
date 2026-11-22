# Graduate Admission Prediction

A coursework project that compares **linear and polynomial regression** for graduate admission prediction and provides a **Streamlit interface** for exploring a saved model.

The repository includes the dataset, an analysis notebook, two saved model pipelines, and the application source.

## What the application does

- Collects GRE, TOEFL, CGPA, university rating, statement-of-purpose strength, recommendation strength, and research experience.
- Uses the saved polynomial regression pipeline to generate an estimate.
- Displays the estimate as a percentage and clips predictions to the range 0–1.

The displayed percentage is a model estimate from a coursework dataset. It is not a university-specific or validated admission probability.

## Technology

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Streamlit · Jupyter Notebook

## Repository guide

| File | Purpose |
| --- | --- |
| [main_notebook.ipynb](main_notebook.ipynb) | Data exploration, statistical analysis, model training, and evaluation |
| [streamlit.py](streamlit.py) | Interactive application |
| [dataset.csv](dataset.csv) | Dataset used by the project |
| [requirements.txt](requirements.txt) | Pinned application and analysis dependencies |
| `linear_regression_pipeline.pkl` | Saved linear regression pipeline |
| `poly_regression_pipeline.pkl` | Saved polynomial regression pipeline loaded by the app |

## Run locally

Use Python 3.10 and run the following commands from a terminal.

### 1. Download the project

```bash
git clone https://github.com/Nayan1412/Graduate-school-Admission-Estimate.git
cd Graduate-school-Admission-Estimate
python -m venv .venv
```

### 2. Activate the environment

**Windows PowerShell**

```powershell
.\.venv\Scripts\Activate.ps1
```

**Windows Command Prompt**

```bat
.venv\Scripts\activate.bat
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

### 3. Install dependencies and launch

```bash
python -m pip install -r requirements.txt
streamlit run streamlit.py
```

Run the app from the repository's root directory: it loads `poly_regression_pipeline.pkl` using a relative path.

The repository pins older package versions. If loading a saved pipeline fails, check that the installed scikit-learn version matches `requirements.txt`; do not assume a saved model is compatible with every library version.

## Explore the analysis

With the virtual environment active:

```bash
python -m pip install notebook
jupyter notebook main_notebook.ipynb
```

The notebook contains the training and evaluation workflow. Review its splits, metrics, and outputs before quoting model performance.

## Project context

Related coursework repository: [DATA-601 Group Project](https://github.com/SujanNeupane42/DATA-601-Group-Project).

For this copy of the project, use the clone URL in the setup instructions above.

## Limitations

- Dataset patterns may not generalize to other universities, applicant populations, or admission cycles.
- A regression output, even when clipped to 0–1, is not automatically a calibrated probability.
- The application is an educational demonstration and should not determine application decisions.
