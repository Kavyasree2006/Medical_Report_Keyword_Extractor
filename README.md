# Medical Report Keyword Extractor

An end-to-end Natural Language Processing project for preparing medical text, extracting healthcare keywords and clinical entities, building structured medical datasets, and exploring the results through an interactive dashboard.

The system converts free-text medical question-answer data and sample medical reports into structured healthcare information covering:

- Diseases
- Symptoms
- Medications
- Procedures
- Laboratory tests
- Searchable medical concepts

> Important: This project is for educational and research purposes only. It is not a medical device and must not be used for diagnosis, treatment decisions, or patient-care decisions without clinical validation.

---

## Project Overview

This project was developed in two main phases.

### Day 1: Medical Text Preparation, Analysis, and NLP

Day 1 focused on preparing the medical text dataset for NLP analysis.

Main tasks completed:

- Imported the medical text dataset using Python and Pandas.
- Inspected dataset columns, missing values, duplicate rows, and inconsistencies.
- Combined medical questions and answers into a single text field.
- Cleaned medical text by converting to lowercase and removing unwanted characters.
- Performed tokenization and text normalization.
- Removed stop words while preserving clinical terminology.
- Generated word-frequency and keyword-frequency outputs.
- Created training and testing datasets.

### Day 2: Entity Extraction, Keyword Identification, and Searchable Medical Knowledge System

Day 2 focused on extracting structured medical information from free-text data.

Main tasks completed:

- Implemented keyword extraction using TF-IDF, RAKE, and KeyBERT.
- Configured clinical entity extraction for healthcare categories.
- Identified diseases, symptoms, medications, procedures, and laboratory tests.
- Created structured clinical entity datasets.
- Generated entity-frequency and keyword-frequency outputs.
- Built a searchable medical concept database.
- Developed an interactive HTML, CSS, and JavaScript dashboard.
- Added CSV upload and browser-based entity extraction.

---

## Actual Output Summary

The following counts come from the generated project outputs.

| Output | Count |
| --- | ---: |
| Original prepared records | 16,407 |
| Cleaned NLP-ready records | 16,359 |
| Day 2 keyword/entity records | 16,359 |
| Searchable medical concept records | 16,359 |
| Structured clinical entity rows | 25,887 |
| Entity-frequency rows | 57 |
| Unique keyword-frequency rows | 29,882 |
| Sample medical reports | 20 |
| Training records | 13,087 |
| Testing records | 3,272 |

### Entity Category Totals

| Category | Frequency |
| --- | ---: |
| Disease | 10,824 |
| Symptom | 6,464 |
| Procedure | 4,599 |
| Medication | 3,253 |
| Lab Test | 747 |

### Top Extracted Entities

| Entity | Category | Frequency |
| --- | --- | ---: |
| syndrome | Disease | 4,519 |
| surgery | Procedure | 2,430 |
| pain | Symptom | 1,746 |
| cancer | Disease | 1,567 |
| drug | Medication | 1,560 |
| infection | Disease | 1,147 |
| weakness | Symptom | 1,023 |
| diabetes | Disease | 891 |
| tumor | Disease | 776 |
| anemia | Disease | 598 |

### Top Medical Keywords

| Keyword | Frequency |
| --- | ---: |
| symptom | 33,893 |
| may | 28,303 |
| people | 21,293 |
| sign | 19,733 |
| condition | 16,973 |
| treatment | 16,943 |
| disease | 15,475 |
| syndrome | 15,367 |
| cancer | 14,761 |
| blood | 13,711 |

---

## Features

- Medical text cleaning and preprocessing
- Missing-value and duplicate-record inspection
- Lowercasing and unwanted-character removal
- Tokenization and text normalization
- Stop-word removal with clinical-term preservation
- Word-frequency and keyword-frequency analysis
- TF-IDF keyword extraction
- RAKE keyword extraction
- KeyBERT keyword extraction on a sample due to high processing time
- Rule-based clinical entity extraction
- Medical concept tagging
- Healthcare category mapping
- Structured entity dataset generation
- Searchable medical knowledge base
- Train-test dataset preparation
- Interactive dashboard
- CSV upload and entity extraction
- CSV export of extracted entities and concepts
- Dark mode and light mode dashboard interface

---

## Technology Stack

| Area | Tools Used |
| --- | --- |
| Programming | Python, JavaScript |
| Data Processing | Pandas, NumPy |
| NLP | NLTK, Scikit-learn, RAKE, KeyBERT |
| Visualization | Matplotlib, WordCloud, HTML Canvas |
| Dashboard | HTML, CSS, JavaScript, Streamlit |
| Testing | Python unittest |

---

## Project Structure

```text
.
|-- data/
|   |-- raw/
|   |   `-- medical_reports.jsonl
|   `-- processed/
|-- docs/
|   `-- project_documentation.md
|-- interface/
|   |-- data/
|   |   `-- dashboard-data.js
|   |-- index.html
|   |-- styles.css
|   |-- app.js
|   `-- README.md
|-- src/
|   `-- medical_keyword_extractor/
|       |-- __init__.py
|       |-- extractor.py
|       |-- lexicon.py
|       |-- pipeline.py
|       |-- preprocessing.py
|       `-- search.py
|-- tests/
|   `-- test_extractor.py
|-- tools/
|   `-- build_dashboard_data.py
|-- dashboard.py
|-- run_pipeline.py
|-- requirements.txt
`-- README.md
```

---

## Dataset and Generated Files

The original dataset was provided as:

```text
archive (3).zip
```

It contained:

```text
train.csv
```

The original dataset columns were:

```text
qtype
Question
Answer
```

During preprocessing, additional columns were created:

```text
medical_text
clean_text
tokens
tokens_no_stopwords
normalized_tokens
preprocessed_text
```

### Main Output Files

| File | Description |
| --- | --- |
| `prepared_medical_text_dataset (1).csv` | Dataset after initial preparation |
| `cleaned_medical_text_dataset (1).csv` | Final cleaned NLP-ready dataset |
| `medical_train_dataset (1).csv` | Training dataset |
| `medical_test_dataset (1).csv` | Testing dataset |
| `word_freq_df.csv` | Word-frequency results |
| `keyword_frequency.csv` | Keyword-frequency results |
| `entity_frequency.csv` | Entity-frequency results |
| `structured_clinical_entities.csv` | Structured extracted entities |
| `day2_medical_entity_keyword_dataset.csv` | Day 2 keyword and entity dataset |
| `searchable_medical_knowledge_dataset.csv` | Searchable keyword and knowledge dataset |
| `searchable_medical_concept_database.csv` | Searchable concept database |
| `sample_medical_reports.csv` | Sample reports for dashboard testing |

---

## NLP Workflow

### 1. Data Import

The dataset was imported using Pandas. The CSV file was loaded and inspected for shape, column names, missing values, and duplicate records.

### 2. Initial Data Inspection

The following checks were performed:

- Dataset shape
- Column names
- Data types
- Missing values
- Duplicate records
- Empty questions
- Empty answers
- Question-type distribution

### 3. Text Cleaning

The medical text was cleaned by:

- Combining `Question` and `Answer`
- Converting text to lowercase
- Removing unwanted symbols
- Removing extra spaces
- Removing newline characters
- Preserving useful medical patterns such as `type-2`, `covid-19`, and `x-ray`

### 4. Tokenization and Normalization

The cleaned text was tokenized into individual words. Stop words were removed while preserving important clinical terms such as:

```text
pain
fever
cancer
diabetes
infection
treatment
surgery
drug
vaccine
diagnosis
test
```

Text normalization was performed using lemmatization.

### 5. Vocabulary Analysis

Word-frequency and keyword-frequency analysis were performed to identify common medical language patterns. Word-frequency charts and word-cloud visualizations were generated during the notebook workflow.

### 6. Keyword Extraction

Three keyword extraction methods were implemented:

- TF-IDF
- RAKE
- KeyBERT

TF-IDF and RAKE were applied to the full dataset. KeyBERT was applied to a sample of records because transformer-based extraction is computationally expensive for large datasets.

### 7. Clinical Entity Extraction

A rule-based entity extraction approach was used to identify clinically relevant entities. Extracted entities were mapped into healthcare categories:

- Disease
- Symptom
- Medication
- Procedure
- Lab Test

### 8. Medical Concept Database

Extracted entities and keywords were used to create a searchable medical concept database. The database allows searching records by healthcare concepts such as:

```text
fever
diabetes
cancer
pain
surgery
vaccine
blood test
```

---

## Interactive Dashboard

The project includes a standalone interactive dashboard built with HTML, CSS, and JavaScript.

Open:

```text
interface/index.html
```

### Dashboard Highlights

- Colorful modern interface
- Dark mode and light mode toggle
- Touch-friendly buttons
- Dataset summary cards
- Entity category summary
- Keyword-frequency visualization
- Sample report testing
- Free-text medical report input
- Clinical entity extraction from pasted reports
- Structured entity output
- Searchable medical concept database
- Entity explorer table
- CSV upload and extraction
- CSV export functionality

### Dashboard Data Source

The dashboard uses:

```text
interface/data/dashboard-data.js
```

This file was generated from the project output CSV files using:

```text
tools/build_dashboard_data.py
```

### CSV Extraction Feature

The dashboard supports uploading CSV files and extracting entities directly in the browser.

Supported CSV text columns:

```text
medical_report
medical_text
text
report
Question
Answer
```

After uploading a CSV, click:

```text
Extract From CSV
```

The extracted results can be exported as:

```text
uploaded_csv_extracted_entities.csv
```

### Dashboard Export Options

| Dashboard Button | Exported Output |
| --- | --- |
| Export Entities CSV | Structured entity dataset |
| Export Concepts CSV | Searchable concept database |
| Download Report CSV | Entities from one tested report |
| Export CSV Extraction | Entities extracted from uploaded CSV |

---

## Python Pipeline

The repository also includes a Python pipeline for processing local sample reports.

Run:

```powershell
python run_pipeline.py
```

The pipeline generates files in:

```text
data/processed/
```

Generated artifacts include:

```text
cleaned_reports.csv
structured_entities.json
structured_entities.csv
medical_knowledge_base.json
search_index.json
pipeline_summary.json
```

---

## Streamlit Dashboard

The project also includes a Streamlit dashboard.

Run:

```powershell
streamlit run dashboard.py
```

The Streamlit dashboard reads generated files from:

```text
data/processed/
```

Use this option if you want a Python-based dashboard. Use `interface/index.html` if you want the standalone HTML dashboard.

---

## Installation

Create a virtual environment:

```powershell
python -m venv .venv
```

Activate it:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

---

## Usage

### Run Python Extraction Pipeline

```powershell
python run_pipeline.py
```

### Run Tests

```powershell
python -m unittest discover tests
```

### Open HTML Dashboard

Open this file in a browser:

```text
interface/index.html
```

### Run Streamlit Dashboard

```powershell
streamlit run dashboard.py
```

---

## Example Input and Output

### Input

```text
Patient reports chest pain and shortness of breath. Troponin is elevated.
Started aspirin 81 mg daily and scheduled coronary angiography.
```

### Extracted Output

```json
{
  "entities": [
    {
      "text": "chest pain",
      "category": "symptom"
    },
    {
      "text": "shortness of breath",
      "category": "symptom"
    },
    {
      "text": "troponin",
      "category": "lab_test"
    },
    {
      "text": "aspirin",
      "category": "medication"
    },
    {
      "text": "coronary angiography",
      "category": "procedure"
    }
  ]
}
```

---

## Key Observations

- The dataset contains a large amount of medical question-answer text.
- Disease entities appeared most frequently, followed by symptoms and procedures.
- Common medical keywords included symptom, treatment, disease, syndrome, cancer, and blood.
- The extracted entity dataset contained 25,887 structured entity rows.
- The searchable concept database contained 16,359 records.
- The HTML dashboard allows users to explore, search, test, and export medical concept data.
- CSV upload support makes the dashboard useful for testing new medical reports.

---

## Limitations

- The entity extraction system is rule-based and depends on predefined medical terms.
- It may miss complex medical terms that are not included in the lexicon.
- KeyBERT was applied to a sample instead of the complete dataset due to processing time.
- The project is intended for learning, research, and demonstration, not clinical use.

---

## Future Improvements

- Add advanced medical NER models.
- Add support for PDF medical report upload.
- Map extracted entities to ICD, SNOMED CT, RxNorm, or LOINC codes.
- Add spelling correction for medical terminology.
- Add confidence scoring for each extracted concept.
- Improve visualization with more chart types.
- Deploy the dashboard as a hosted web application.
- Add user authentication for secure medical data handling.

