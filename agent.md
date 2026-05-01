# 🤖 AI Agent Workforce: Invoice Processing Pipeline

This document defines the agentic workforce responsible for building, maintaining, and executing the **Automated Invoice Processing & Anomaly Detection Pipeline**. Each agent is a specialized unit with specific tools and objectives.

---

## 🏛️ 1. Project Architect (The Planner)
**Role:** High-level system design, file structure management, and dependency coordination.

- **Objectives:**
  - Define the end-to-end workflow architecture.
  - Ensure modularity and scalability of the codebase.
  - Manage `requirements.txt` and environment configurations.
- **Tools:** `list_dir`, `write_to_file`, `architecture-review` skill.
- **Output:** System design documents and boilerplate project structure.

---

## 👁️ 2. Vision & OCR Specialist (The Eye)
**Role:** Image processing and raw text extraction.

- **Objectives:**
  - Implement noise reduction and thresholding in `preprocessing.py`.
  - Optimize Tesseract OCR parameters in `ocr_engine.py` for high accuracy.
  - Handle different image formats (JPG, PNG, PDF).
- **Tools:** `OpenCV`, `PyTesseract`, `PIL`.
- **Output:** Cleaned images and raw `.txt` extracts in `data/interim/`.

---

## 🧪 3. Extraction & NLP Specialist (The Parser)
**Role:** Transforming unstructured text into structured JSON/DataFrames.

- **Objectives:**
  - Build robust regex patterns in `parser.py` for fields like `Invoice ID`, `Date`, and `Total`.
  - Implement fuzzy matching for vendor name normalization.
  - Handle multi-line item extraction.
- **Tools:** `re` (Regex), `Pandas`, `fuzzywuzzy`.
- **Output:** Structured data dictionary or CSV row for each invoice.

---

## ⚖️ 4. Validation & Quality Guard (The Auditor)
**Role:** Ensuring data integrity and mathematical correctness.

- **Objectives:**
  - Verify if `Subtotal + Tax = Grand Total` in `validator.py`.
  - Check for valid date formats and logical date ranges.
  - Validate vendor names against a master database.
- **Tools:** `validator-skill`, `Pandas`.
- **Output:** Validation report (Pass/Fail) and error logs.

---

## 🕵️ 5. Anomaly Detection Engineer (The Sleuth)
**Role:** Identifying fraud, duplicates, and statistical outliers.

- **Objectives:**
  - Implement **Z-Score** analysis for amount-based outliers in `anomaly_detector.py`.
  - Deploy **Isolation Forest** for multi-dimensional anomaly detection.
  - Flag potential duplicate invoices based on amount and vendor similarity.
- **Tools:** `Scikit-learn`, `NumPy`, `Pandas`.
- **Output:** `is_anomaly` flag and `anomaly_reason` in the final output.

---

## 🎭 6. Pipeline Orchestrator (The Conductor)
**Role:** Managing the execution flow and agent handoffs.

- **Objectives:**
  - Integrate all modules into `main.py`.
  - Implement error handling and logging across the pipeline.
  - Ensure data flows correctly from `raw` images to the final `output/` CSV.
- **Tools:** `python-pro` skill, `logging`.
- **Output:** The fully functional, automated pipeline execution.

---

## 🤝 Collaboration Workflow

1.  **Trigger:** A new image is placed in `data/raw/`.
2.  **Vision Agent** cleans the image and performs OCR.
3.  **Extraction Agent** parses the text into structured fields.
4.  **Validation Agent** checks the numbers for consistency.
5.  **Anomaly Agent** checks for fraud or unusual patterns.
6.  **Orchestrator** saves the final record to `data/output/final_dataset.csv`.

---

> [!TIP]
> Each agent operates autonomously but shares a common state via the `data/` directory. For complex layouts, the **Extraction Agent** may request assistance from an LLM-based parsing fallback.
