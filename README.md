# BANKNIFTY

## Description
This project involves analyzing and processing financial datasets in Parquet format for BANKNIFTY options. The dataset is stored in Cloudflare R2 and needs to be downloaded and processed for analysis.

## Installation

### Prerequisites
- Python 3.10+
- pip (Python package manager)
- Git (for cloning the repository)

### Required Python Packages
```bash
pip install pandas pyarrow s3cmd
```

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <repository_url>
cd <repository_folder>
```

### 2. Configure `s3cmd`

Create a file named `.s3cfg` in the project directory with the following content:

```
[default]
access_key = <YOUR_ACCESS_KEY>
secret_key = <YOUR_SECRET_KEY>
host_base = cbabd13f6c54798a9ec05df5b8070a6e.r2.cloudflarestorage.com
host_bucket = cbabd13f6c54798a9ec05df5b8070a6e.r2.cloudflarestorage.com
use_https = True
```

### 3. Download Dataset

Run the following command to download the dataset:
```bash
s3cmd sync s3://desiquant/data/candles/BANKNIFTY/2024-01-10/ ./data/candles/BANKNIFTY/2024-01-10/
```

## Notes
- Replace `<YOUR_ACCESS_KEY>` and `<YOUR_SECRET_KEY>` with actual credentials.
- Ensure correct file paths while uploading and reading files in Google Colab.


# Fibonacci Pivot Points and 5-Minute Candle Data Processing

## Project Overview

This project processes financial data for BANKNIFTY options to:

- Generate 5-minute candlestick data for 10th January 2024.
- Calculate Fibonacci Pivot Points for the same date.
- Export the results to CSV files.

## Project Structure

```
├── 5min_candles/
│   ├── 47100CE_5min_candles.csv
│   └── 47100CE_Fibonacci_Pivot_Points.csv
├── main.ipynb  # Google Colab notebook with the implementation
├── requirements.txt
└── README.md
```

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Open Google Colab

- Upload the `quant.ipynb` file to Google Colab.
- Upload your `.parquet` data files to Colab or connect Google Drive.

### 4. Run the Notebook

- Execute all cells to generate the 5-minute candles and Fibonacci Pivot Points.
- Processed CSV files will be saved in the `5min_candles` folder.

## Output Files

- **5-Minute Candles:** `5min_candles/47100CE_5min_candles.csv`
- **Fibonacci Pivot Points:** `5min_candles/47100CE_Fibonacci_Pivot_Points.csv`

## Calculations

### 5-Minute Candles

- **Open:** First price in each 5-minute interval.
- **High:** Maximum price in the interval.
- **Low:** Minimum price in the interval.
- **Close:** Last price in the interval.

### Fibonacci Pivot Points

- **Pivot Point (P):** (High + Low + Close) / 3
- **R1:** P + 0.382 × (High − Low)
- **R2:** P + 0.618 × (High − Low)
- **R3:** P + (High − Low)
- **S1:** P − 0.382 × (High − Low)
- **S2:** P − 0.618 × (High − Low)
- **S3:** P − (High − Low)

## Author

Pratham Shirol

## Contact
For any issues, contact [Pratham Shirol] at [prathamshirol53@gmail.com].
---


