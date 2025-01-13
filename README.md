
# 5-Minute Candlestick Data Processor

## Project Overview
This project processes options trading data for BANKNIFTY to generate 5-minute candlestick data and calculate Fibonacci Pivot Points for January 10, 2024.

## Features
- **5-Minute Candlestick Generation:**
  - Calculates Open, High, Low, Close (OHLC) values for 5-minute intervals.
- **Fibonacci Pivot Points Calculation:**
  - Computes Pivot, R1, R2, R3, S1, S2, S3 using daily high, low, and close values.

## Project Structure
```
├── 5min_candles/              # Folder for storing generated CSV files
│   ├── 47100CE_5min_candles.csv
│   └── 47100CE_Fibonacci_Pivot_Points.csv
├── data/                      # Raw input data (Parquet files)
│   └── BANKNIFTY
│       └── 2024-01-10
├── scripts/                   # Python scripts for data processing
│   └── process_data.py
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies
```

## Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Script:**
   ```bash
   python scripts/process_data.py
   ```

## Script Details

### 5-Minute Candlestick Calculation
- Open: First value in the 5-minute window
- High: Maximum value in the 5-minute window
- Low: Minimum value in the 5-minute window
- Close: Last value in the 5-minute window

### Fibonacci Pivot Points Formula
- Pivot Point (P) = (High + Low + Close) / 3  
- R1 = P + 0.382 × (High - Low)  
- R2 = P + 0.618 × (High - Low)  
- R3 = P + (High - Low)  
- S1 = P - 0.382 × (High - Low)  
- S2 = P - 0.618 × (High - Low)  
- S3 = P - (High - Low)

## Output
- **5min_candles/47100CE_5min_candles.csv**: Contains 5-minute OHLC data.
- **5min_candles/47100CE_Fibonacci_Pivot_Points.csv**: Contains daily Fibonacci pivot points.

## Contributing
Feel free to submit pull requests or open issues for improvements.

## License
This project is licensed under the MIT License.

---

**Author:** Pratham Shirol

**Contact:** prathamshirol@example.com

