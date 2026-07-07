# 🏥 Medical Report Keyword Extractor and Clinical NLP Dashboard

> An end-to-end medical NLP project that cleans clinical text, extracts healthcare keywords, identifies diseases, symptoms, medications, procedures, and lab tests, builds a searchable medical concept database, and provides an interactive HTML dashboard with CSV-based entity extraction.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)
![NLP](https://img.shields.io/badge/NLP-Medical_Text_Processing-green.svg)
![Dashboard](https://img.shields.io/badge/Dashboard-HTML_CSS_JS-orange.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-purple.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

---

# 📌 Project Overview

The **Medical Report Keyword Extractor and Clinical NLP Dashboard** is an NLP-based healthcare text processing system designed to convert unstructured medical text into structured, searchable healthcare information.

The project works on medical question-answer data and sample medical reports. It performs text cleaning, preprocessing, keyword extraction, clinical entity extraction, medical concept tagging, and dashboard-based exploration.

The system identifies important clinical concepts such as:

- Diseases
- Symptoms
- Medications
- Procedures
- Laboratory tests
- Medical keywords
- Searchable healthcare concepts

Unlike simple text analysis projects, this project provides a complete pipeline from raw medical text to a usable interactive dashboard.

---

# 🚀 Features

## 🧹 Medical Text Cleaning and Preprocessing

The dataset is cleaned and prepared for NLP analysis.

Preprocessing steps include:

- Missing value checking
- Duplicate record checking
- Inconsistency handling
- Lowercase conversion
- Unwanted character removal
- Whitespace and newline cleanup
- Tokenization
- Stop-word removal
- Clinical term preservation
- Text normalization

Generated columns include:

- `medical_text`
- `clean_text`
- `tokens`
- `tokens_no_stopwords`
- `normalized_tokens`
- `preprocessed_text`

---

## 🔍 Keyword Extraction

The project implements multiple keyword extraction techniques.

Methods used:

- **TF-IDF**
- **RAKE**
- **KeyBERT**

TF-IDF and RAKE were applied to the full dataset. KeyBERT was tested on a sample of records because transformer-based keyword extraction requires more processing time.

The final keyword dataset includes:

- TF-IDF keywords
- RAKE keywords
- KeyBERT sample keywords
- Disease tags
- Symptom tags
- Medication tags
- Procedure tags
- Lab test tags

---

## 🧬 Clinical Entity Extraction

The system extracts clinically relevant entities from medical text and maps them to predefined healthcare categories.

Entity categories:

- Disease
- Symptom
- Medication
- Procedure
- Lab Test

The extracted results are stored in a structured dataset containing:

- Record ID
- Question type
- Source question
- Extracted entity
- Entity category

---

## 🏷️ Medical Concept Tagging

Medical concept tagging converts free-text reports into organized healthcare tags.

Example:

```text
The patient has fever, chest pain, and cough. A blood test was recommended.
```

Structured output:

| Category | Extracted Concepts |
|----------|--------------------|
| Disease | Not found |
| Symptom | fever, chest pain, cough |
| Medication | Not found |
| Procedure | Not found |
| Lab Test | blood test |

---

## 🔎 Searchable Medical Knowledge System

The project creates a searchable medical concept database from the extracted entities and keywords.

Users can search records by terms such as:

- fever
- diabetes
- cancer
- pain
- vaccine
- surgery
- blood test

The searchable database contains medical questions, answers, combined medical text, entity tags, and concept tags.

---

## 📊 Interactive Dashboard

The project includes a colorful interactive dashboard built using:

- HTML
- CSS
- JavaScript

Dashboard features:

- Dark mode and light mode
- Touch-friendly buttons
- Dataset summary cards
- Entity category dashboard
- Keyword frequency visualization
- Sample medical report testing
- Free-text medical report input
- Structured entity output
- Searchable concept database
- Entity explorer table
- CSV upload
- CSV-based entity extraction
- Export extracted entities as CSV
- Export searchable concepts as CSV

Open the dashboard:

```text
interface/index.html
```

---

# 📊 Actual Project Outputs

The project was completed using the generated dataset outputs.

| Output | Count |
|--------|------:|
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

---

# 🧾 Entity Category Summary

| Entity Category | Frequency |
|-----------------|----------:|
| Disease | 10,824 |
| Symptom | 6,464 |
| Procedure | 4,599 |
| Medication | 3,253 |
| Lab Test | 747 |

---

# 🏆 Top Extracted Medical Entities

| Entity | Category | Frequency |
|--------|----------|----------:|
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

---

# 🔠 Top Medical Keywords

| Keyword | Frequency |
|---------|----------:|
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

# 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Main programming language |
| Pandas | Data loading, cleaning, and analysis |
| NumPy | Numerical processing |
| NLTK | Tokenization, stop words, normalization |
| Scikit-learn | TF-IDF and train-test split |
| RAKE | Keyword phrase extraction |
| KeyBERT | Context-aware keyword extraction |
| Matplotlib | Data visualization |
| WordCloud | Word cloud generation |
| HTML | Dashboard structure |
| CSS | Dashboard styling and dark mode |
| JavaScript | Dashboard interactivity and CSV extraction |
| Streamlit | Optional Python dashboard |
| unittest | Testing |

---

# 📂 Project Structure

```text
Medical Report Keyword Extractor/
│
├── data/
│   ├── raw/
│   │   └── medical_reports.jsonl
│   └── processed/
│
├── docs/
│   └── project_documentation.md
│
├── interface/
│   ├── data/
│   │   └── dashboard-data.js
│   ├── index.html
│   ├── styles.css
│   ├── app.js
│   └── README.md
│
├── src/
│   └── medical_keyword_extractor/
│       ├── __init__.py
│       ├── extractor.py
│       ├── lexicon.py
│       ├── pipeline.py
│       ├── preprocessing.py
│       └── search.py
│
├── tests/
│   └── test_extractor.py
│
├── tools/
│   └── build_dashboard_data.py
│
├── dashboard.py
├── run_pipeline.py
├── requirements.txt
└── README.md
```

---

# 📁 Dataset

The original dataset was provided as:

```text
archive (3).zip
```

It contained:

```text
train.csv
```

Original columns:

- `qtype`
- `Question`
- `Answer`

The dataset contains medical question-answer pairs covering symptoms, conditions, treatments, susceptibility, prevention, and other healthcare-related topics.

---

# 📦 Generated Output Files

| File | Description |
|------|-------------|
| `prepared_medical_text_dataset (1).csv` | Dataset after initial preparation |
| `cleaned_medical_text_dataset (1).csv` | Final cleaned NLP-ready dataset |
| `medical_train_dataset (1).csv` | Training dataset |
| `medical_test_dataset (1).csv` | Testing dataset |
| `word_freq_df.csv` | Word-frequency results |
| `keyword_frequency.csv` | Keyword-frequency results |
| `entity_frequency.csv` | Entity-frequency results |
| `structured_clinical_entities.csv` | Structured extracted medical entities |
| `day2_medical_entity_keyword_dataset.csv` | Day 2 keyword and entity dataset |
| `searchable_medical_knowledge_dataset.csv` | Searchable keyword and knowledge dataset |
| `searchable_medical_concept_database.csv` | Searchable concept database |
| `sample_medical_reports.csv` | Sample medical reports for testing |

---

# 🔄 Project Workflow

```text
Medical Dataset
        │
        ▼
Data Import Using Pandas
        │
        ▼
Initial Data Inspection
        │
        ▼
Missing Value and Duplicate Checking
        │
        ▼
Medical Text Cleaning
        │
        ▼
Tokenization and Text Normalization
        │
        ▼
Stop Word Removal
        │
        ▼
Medical Vocabulary Analysis
        │
        ▼
Word Frequency and Word Cloud Generation
        │
        ▼
TF-IDF, RAKE, and KeyBERT Keyword Extraction
        │
        ▼
Clinical Entity Extraction
        │
        ▼
Medical Concept Tagging
        │
        ▼
Structured Entity Dataset
        │
        ▼
Searchable Medical Concept Database
        │
        ▼
Interactive HTML Dashboard
        │
        ▼
CSV Upload, Extraction, Search, and Export
```

---

# 🧪 NLP Pipeline

## Step 1: Data Inspection

The dataset was inspected for:

- Shape
- Columns
- Missing values
- Duplicate records
- Empty questions
- Empty answers
- Question type distribution

---

## Step 2: Text Cleaning

Text cleaning included:

- Combining `Question` and `Answer`
- Converting text to lowercase
- Removing unwanted characters
- Removing extra spaces
- Removing newline characters
- Preserving medical terms such as `x-ray`, `type-2`, and `covid-19`

---

## Step 3: Text Preprocessing

Text preprocessing included:

- Tokenization
- Stop-word removal
- Clinical term preservation
- Lemmatization
- Final preprocessed text generation

---

## Step 4: Vocabulary Analysis

Vocabulary analysis generated:

- Word-frequency tables
- Keyword-frequency tables
- Bar charts
- Word cloud visualizations
- Common healthcare entity summaries

---

## Step 5: Keyword Extraction

Keyword extraction was performed using:

- TF-IDF for statistically important terms
- RAKE for phrase-level keyword extraction
- KeyBERT for semantic keyword extraction on sample records

---

## Step 6: Entity Extraction

Entity extraction mapped medical terms into:

- Disease
- Symptom
- Medication
- Procedure
- Lab Test

The output was saved as a structured clinical entity dataset.

---

# 💻 Dashboard

The project includes two dashboard options.

## 🌐 HTML Dashboard

The main dashboard is available at:

```text
interface/index.html
```

HTML dashboard modules:

- Home overview
- Dataset snapshot
- Entity category summary
- Keyword frequency section
- Sample report tester
- Structured output viewer
- CSV extraction tool
- Entity explorer
- Searchable concept database
- Export buttons
- Dark mode and light mode

---

## 📂 CSV Extraction Interface

The dashboard allows users to upload a CSV file and extract medical entities directly in the browser.

Supported CSV columns:

- `medical_report`
- `medical_text`
- `text`
- `report`
- `Question`
- `Answer`

After uploading the CSV, click:

```text
Extract From CSV
```

The dashboard extracts:

- Diseases
- Symptoms
- Medications
- Procedures
- Lab tests

Exported output:

```text
uploaded_csv_extracted_entities.csv
```

---

## 📊 Streamlit Dashboard

The project also includes a Streamlit dashboard.

Run:

```bash
streamlit run dashboard.py
```

The Streamlit dashboard reads processed outputs from:

```text
data/processed/
```

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/your-username/medical-report-keyword-extractor.git
```

Move into the project folder:

```bash
cd medical-report-keyword-extractor
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the virtual environment on Windows:

```bash
.\.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# ▶️ How to Run

## Run the Python Pipeline

```bash
python run_pipeline.py
```

Generated files are saved in:

```text
data/processed/
```

---

## Run the Streamlit Dashboard

```bash
streamlit run dashboard.py
```

---

## Open the HTML Dashboard

Open this file in any browser:

```text
interface/index.html
```

No server is required for the standalone HTML dashboard.

---

## Run Tests

```bash
python -m unittest discover tests
```

---

# 🧾 Example Input and Output

## Input Medical Report

```text
Patient reports chest pain and shortness of breath. Troponin is elevated.
Started aspirin 81 mg daily and scheduled coronary angiography.
```

## Extracted Structured Output

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

# 📷 Dashboard Screenshots

Add your GitHub-uploaded dashboard screenshots here.

## Dashboard Home

```text
Add screenshot link here
```

## CSV Extraction Page

```text
Add screenshot link here
```

## Entity Explorer

```text
Add screenshot link here
```

## Searchable Concept Database

```text
Add screenshot link here
```

---

# 🎯 Learning Outcomes

Through this project, the following concepts were implemented:

- Medical text preprocessing
- NLP pipeline development
- Tokenization and normalization
- Stop-word removal
- Keyword extraction
- TF-IDF implementation
- RAKE keyword extraction
- KeyBERT keyword extraction
- Clinical entity extraction
- Medical concept tagging
- Searchable knowledge-base creation
- Train-test dataset preparation
- Dashboard development using HTML, CSS, and JavaScript
- CSV upload and export functionality
- Healthcare data visualization

---

# ⚠️ Limitations

- The clinical entity extraction system is rule-based.
- It depends on predefined healthcare terms.
- It may miss complex medical terms not present in the dictionary.
- KeyBERT was applied to sample records because full-dataset transformer processing is time-consuming.
- The project is not suitable for real clinical decision-making without expert validation.

---

# 🔮 Future Enhancements

- Add advanced medical NER models
- Add PDF medical report upload
- Add medical spelling correction
- Map entities to ICD, SNOMED CT, RxNorm, or LOINC codes
- Add patient-wise medical history tracking
- Add confidence scoring for extracted concepts
- Add more dashboard charts
- Deploy dashboard as a web application
- Add authentication and secure data handling
- Integrate a medical AI chatbot

---

# 👩‍💻 Author

**K. Kavya Sree**

Internship Project

Medical Report Keyword Extractor and Clinical NLP Dashboard

---

# 📄 License

This project is developed for **educational and internship purposes**.

---

# ⭐ If you found this project useful

Please consider giving this repository a **Star** on GitHub.

---

# 🩺 Medical Disclaimer

This project is for educational use only. It does not provide medical advice, diagnosis, or treatment recommendations. Any healthcare-related use must be reviewed and validated by qualified medical professionals.
