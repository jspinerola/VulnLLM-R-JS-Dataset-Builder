# VulnLLM-R-JS-Dataset-Builder

Contribution to VulnLLM-R. This tool maps the CVEfixes dataset to the format supported by VulnLLM-R, specifically targeting JavaScript vulnerabilities. It also enriches the dataset using Google Gemini AI to provide technical reasoning for each vulnerability.

Developed for the CSCI 4321 course at Texas A&M University-San Antonio.

## Getting Started

### Prerequisites

- Python 3.x
- A Google Gemini API Key (stored in a `.env` file as `GOOGLE_API_KEY`)
- Required libraries: `datasets`, `google-genai`, `python-dotenv`, `sqlite3`

### Installation

1. Clone this repository.
2. Install the required dependencies:
   ```console
   $ pip install datasets google-genai python-dotenv
   ```
3. Create a `.env` file in the root directory and add your Google API key:
   ```env
   GOOGLE_API_KEY=your_api_key_here
   ```

## Usage

The main logic is contained within the `app.ipynb` Jupyter Notebook. 

1. Open `app.ipynb` in your preferred environment (Jupyter Lab, VS Code, or Google Colab).
2. Run the cells in order.

The notebook performs the following steps:
1. **Data Loading**: Automatically downloads the `hitoshura25/cvefixes` dataset from Hugging Face.
2. **Filtering**: Extracts JavaScript snippets that have both vulnerable and fixed code versions.
3. **Database Population**: Stores the processed data in a local SQLite database (`processed_cvefixes.db`).
4. **Semantic Enrichment**: Uses Gemini AI to generate a "reason" field explaining why the code is vulnerable and how the patch fixes it.
5. **Export**: Generates a `js_vulnllm_dataset.jsonl` file formatted for use with VulnLLM-R.

## Output Files

- `processed_cvefixes.db`: A SQLite database containing the processed samples and generated reasons.
- `js_vulnllm_dataset.jsonl`: The final dataset file in JSONL format, ready for use with VulnLLM-R.
