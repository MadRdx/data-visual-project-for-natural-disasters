# Installation & Local Run Guide

This guide will help you set up the **US Disaster Analytics & Prediction Dashboard** locally.

## 1. Prerequisites

Ensure you have the following installed:
*   **Python 3.8+**
*   **pip** (Python package manager)
*   **Git**

## 2. Clone the Repository

```bash
git clone <repository_url>
cd cs6242_team11
```

## 3. Install Dependencies

Install the required Python packages using the provided `requirements.txt`:

```bash
pip install -r requirements.txt
```

## 4. Environment Setup

The dashboard features an AI Chatbot that requires a **Groq API Key**.

1.  Get a free API key from [console.groq.com](https://console.groq.com/).
2.  Set the environment variable:

    **Windows (PowerShell):**
    ```powershell
    $env:GROQ_API_KEY = "your_api_key_here"
    ```

    **Windows (CMD):**
    ```cmd
    set GROQ_API_KEY=your_api_key_here
    ```

    **Mac/Linux:**
    ```bash
    export GROQ_API_KEY="your_api_key_here"
    ```

## 5. Data Setup

The dashboard relies on preprocessed JSON data. You have two options:

### Option A: Use Existing Data (Easiest)
If the `datasets/` folder already contains `noaa_data.json`, `nri_data.json`, and `predictions_data.json`, you can skip to step 6.

### Option B: Generate Data from Scratch
If you need to regenerate the data (e.g., to fetch the latest NOAA updates), follow these steps:

1.  **Download Raw Data:**
    Open `DataInstaller.ipynb` in Jupyter Notebook or VS Code and run the cells to download the raw NOAA CSV files (2000-2024). This script handles the downloading and initial merging of the raw data.

2.  **Run Preprocessing Scripts:**
    Once raw data is available, run the preprocessing scripts to generate the optimized JSON files for the dashboard.

    ```bash
    # Process NOAA historical data
    python preprocessing/preprocess_noaa_data.py

    # Process National Risk Index (NRI) data
    python preprocessing/preprocess_nri_data.py

    # Process Prediction data (2025 projections)
    python preprocessing/preprocess_predictions.py
    ```

    *Note: Ensure the raw input files expected by these scripts are in the correct locations (check the scripts for specific input paths if they differ from `TrialData.ipynb` output).*

## 6. Run the Dashboard

Start the local server using the provided Python script. This handles both serving the static files and the backend API for the chatbot.

```bash
python serve_dashboard.py
```

*   The dashboard should automatically open in your default browser at `http://localhost:8000`.
*   If it doesn't open, manually visit `http://localhost:8000` in your browser.
*   **To stop the server:** Press `Ctrl+C` in the terminal.

## Troubleshooting

*   **Map not loading?** Ensure `datasets/us-states.json` and other JSON files are present in the `datasets/` directory.
*   **Chatbot not working?** Verify your `GROQ_API_KEY` is set correctly in the terminal *before* running `serve_dashboard.py`.
*   **Missing dependencies?** Double-check that `pip install -r requirements.txt` completed successfully.
