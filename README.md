# Automated-Invoice-Processing
Here is your **README.md file in proper Markdown format** (ready to copy-paste into GitHub):

```md
# 📄 Invoice Processing & Anomaly Detection Pipeline

## 🚀 Project Overview

This project builds an end-to-end **invoice automation pipeline** that:

- Extracts text from invoice images using OCR  
- Converts unstructured text into structured data  
- Validates invoice integrity using rule-based checks  
- Detects anomalies and potential fraud using machine learning  

The goal is to simulate a real-world **Accounts Payable (AP) automation system**.

---

## 🧠 Problem Statement

Manual invoice processing is:

- Time-consuming  
- Error-prone  
- Vulnerable to fraud  

This system automates the pipeline from **image → structured data → anomaly detection**, improving efficiency and reliability.

---

## ⚙️ Pipeline Architecture

```

Invoice Image
↓
[Preprocessing - OpenCV]
↓
[OCR - Tesseract]
↓
[Text Parsing - Regex]
↓
[Structured Data - Pandas]
↓
[Validation Rules]
↓
[Anomaly Detection - ML]
↓
Final Output CSV

```

---

## 📂 Project Structure

```

invoice_automation_project/
│
├── data/
│   ├── raw/            # Original invoice images
│   ├── processed/      # Cleaned images
│   ├── interim/        # OCR extracted text
│   ├── output/         # Final CSV output
│
├── src/
│   ├── preprocessing.py
│   ├── ocr_engine.py
│   ├── parser.py
│   ├── validator.py
│   ├── anomaly_detector.py
│   ├── utils.py
│
├── notebooks/
│   └── experiments.ipynb
│
├── main.py
├── requirements.txt
└── README.md

```

---

## 🔄 Workflow Explanation

### 1. Preprocessing (`preprocessing.py`)
- Convert image to grayscale  
- Remove noise  
- Apply thresholding  

👉 Improves OCR accuracy  

---

### 2. OCR Extraction (`ocr_engine.py`)
- Uses Tesseract OCR  
- Converts images into raw text  

---

### 3. Parsing (`parser.py`)
Extracts key fields using Regex:

- Invoice Number  
- Invoice Date  
- Vendor Name  
- Total Amount  
- Line Items  

---

### 4. Validation (`validator.py`)
Applies rule-based checks:

- ✔ Mathematical consistency  
- ✔ Date validation (future / outdated)  

---

### 5. Anomaly Detection (`anomaly_detector.py`)

Techniques used:

- Z-Score (statistical outliers)  
- Isolation Forest (unsupervised ML)  
- Duplicate detection (fuzzy matching)  

---

## 📊 Output

Final dataset (`final_dataset.csv`) contains:

| Column | Description |
|--------|------------|
| invoice_number | Unique ID |
| vendor | Vendor name |
| date | Invoice date |
| amount | Total amount |
| is_anomaly | True/False |
| anomaly_reason | Explanation |

---

## 🧪 Sample Output

```

invoice_number,vendor,date,amount,is_anomaly,reason
INV001,ABC Ltd,01-01-2024,500,False,None
INV002,XYZ Ltd,05-01-2024,50000,True,Outlier
INV003,ABC Ltd,10-01-2024,1000,True,Math Error

````

---

## 🛠️ Tech Stack

- Python  
- OpenCV  
- PyTesseract  
- Pandas, NumPy  
- Scikit-learn  
- Regex (`re`)  

---

## 📥 Installation

```bash
git clone https://github.com/your-username/invoice-automation.git
cd invoice-automation

pip install -r requirements.txt
````

### Install Tesseract OCR

**Ubuntu:**

```bash
sudo apt install tesseract-ocr
```

**Windows:**
Download from official installer and set environment path.

---

## ▶️ Usage

Run the pipeline:

```bash
python main.py
```

Output will be generated in:

```
data/output/final_dataset.csv
```

---

## 📈 Future Improvements

* Use deep learning OCR (TrOCR / Donut)
* Improve table extraction
* Add Streamlit dashboard
* Deploy as API

---

## ⚠️ Limitations

* OCR accuracy depends on image quality
* Regex parsing may fail on complex layouts
* Limited dataset size

---

## 📚 Learning Outcomes

* Computer Vision basics
* OCR pipeline design
* Data cleaning & structuring
* Unsupervised anomaly detection

---

## 👨‍💻 Author

Your Name
(Data Science / ML Intern Project)

---

## ⭐ Contribution

Feel free to fork, improve, and raise pull requests.
