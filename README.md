\# invofilter 📄✨



An invoice extractor automated Python pipeline designed to capture the billing data (like invoice numbers, totals, and line items) from messy PDF invoices using the \*\*PdfPlumber\*\* and \*\*Mistral AI\*\* (`mistral-large-latest`) LLM.



\## 🚀 Features

\* \*\*PDF Text Extraction\*\*: Extracts raw content cleanly using `pdfplumber` from invoice pdf.

\* \*\*Clean Text\*\*: Features a line-by-line cleaning mechanism to Strip whitespace from each line AND remove empty lines.

\* \*\*LLM-Powered Parsing\*\*: Leverages Mistral AI's structured JSON output mode to guarantee predictable data schemas.

\* \*\*Security First\*\*: Fully integrated with `python-dotenv` to keep proprietary API keys completely out of public source control.



\## 📁 Project Structure

```text

invofilter/

├── invoices/                 # Source directory for storing invoice pdfs

├── outputs/                  # It is directory which stores automatically generated extraction results (JSON) files

├── invofilter\\\\\\\_pipeline.ipynb # It is ipynb file for core interactive execution notebook

├── .gitignore                # Protects secrets (.env) and local Jupyter caches

├── requirements.txt          # It stores project dependencies

└── README.md                 # Project documentation

```



\## 🛠️ Setup Instructions



\### 1. Clone the Repository

```bash

git clone https://github.com

cd invofilter

```



\### 2. Install Dependencies

Ensure your workspace is updated with the required runtime libraries:

```bash

pip install -r requirements.txt

```



\### 3. Configure Local Environment

Create a `.env` file in the root directory of the project to securely house your credentials:

```text

MISTRAL\\\\\\\_API\\\\\\\_KEY=your\\\\\\\_secret\\\\\\\_mistral\\\\\\\_api\\\\\\\_key\\\\\\\_here

```

\*(Note: The `.gitignore` policy explicitly blocks this file from ever leaking into public GitHub trees).\*



\## 📊 Pipeline Logic Flow

1\. \*\*Ingest\*\*: The pipeline loops through target files located in the `./invoices/` directory.

2\. \*\*Clean\*\*: Extracts text data and isolates content blockages using structured row-stripping rules.

3\. \*\*Analyze\*\*: Hands off the sanitized text block directly to Mistral's structural endpoints.

4\. \*\*Export\*\*: Decodes response items to save machine-readable files into the `./outputs/` folder.

