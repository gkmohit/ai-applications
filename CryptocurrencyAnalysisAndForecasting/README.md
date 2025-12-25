# Cryptocurrency Analysis and Forecasting

A comprehensive research project exploring machine learning algorithms for cryptocurrency price prediction and portfolio optimization.

## Overview

This project is a deep dive into applying state-of-the-art machine learning and statistical techniques to analyze and forecast cryptocurrency prices. It demonstrates research into quantitative finance, time series analysis, and deep learning applications in the crypto market.

## Key Features

- **Multi-Model Forecasting**: Compares 5 different algorithms for price prediction
  - ARIMA (AutoRegressive Integrated Moving Average)
  - XGBoost (eXtreme Gradient Boosting)
  - LSTM (Long Short-Term Memory)
  - GRU (Gated Recurrent Unit)
  - TimeGPT/Prophet (Foundation Models)

- **Comprehensive Analysis**
  - Dynamic cryptocurrency selection for analysis
  - Exploratory data analysis and visualization
  - Correlation analysis across cryptocurrencies
  - Moving average strategy backtesting
  - Volatility analysis and risk metrics
  - Seasonal pattern detection
  - Portfolio optimization using Modern Portfolio Theory

- **Automated Workflow**
  - Seamless Kaggle dataset integration
  - Google Drive cloud storage integration
  - Feature engineering and data preparation
  - Model training and evaluation
  - Comparative performance analysis

## Research Questions Addressed

1. Can we predict cryptocurrency prices using historical patterns?
2. Which cryptocurrencies have the best risk-adjusted returns?
3. Do moving average strategies work in crypto markets?
4. How correlated are different cryptocurrencies?
5. What is the optimal portfolio allocation using historical data?
6. Can volatility predict future price movements?
7. Do altcoins follow Bitcoin's trends?
8. What seasonal patterns exist in crypto markets?

## Getting Started

### Prerequisites

- Python 3.10 or higher
- Google Colab (recommended) or Jupyter Notebook
- Kaggle account with API credentials
- Google Drive account (optional, for cloud storage)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/cryptocurrency-analysis.git
cd cryptocurrency-analysis
```

2. Install required packages (automatically handled in notebook):
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost tensorflow statsmodels kaggle
```

3. Configure Kaggle API:
   - Download your API credentials from https://www.kaggle.com/settings/account
   - Place `kaggle.json` in `~/.kaggle/` directory
   - Run the notebook and upload the file when prompted

### Usage

1. Open the notebook in Google Colab or Jupyter
2. Follow the guided steps:
   - Connect to Google Drive (optional)
   - Upload Kaggle credentials
   - Select your cryptocurrency of interest
   - Run analysis cells in sequence
3. View results and visualizations
4. Access generated reports in output directory

## Project Structure

```
cryptocurrency-analysis/
├── Cryptocurrency_Analysis_and_Forecasting.ipynb  # Main analysis notebook
├── README.md                                       # This file
├── LICENSE                                         # MIT License
└── .gitignore                                      # Git ignore file
```

## Data Source

Data is sourced from Kaggle:
- **Dataset**: Top 100 Cryptocurrencies Daily Price Data 2025
- **URL**: https://www.kaggle.com/datasets/mihikaajayjadhav/top-100-cryptocurrencies-daily-price-data-2025

## Model Comparison

The notebook trains and compares five different models:

| Model | Type | Strengths | Weaknesses |
|-------|------|-----------|-----------|
| ARIMA | Statistical | Interpretable, works well for univariate data | Assumes stationarity, limited multivariate capability |
| XGBoost | Gradient Boosting | Handles complex patterns, fast training | Requires feature engineering |
| LSTM | Deep Learning | Captures temporal dependencies, handles sequences | Computationally expensive, overfitting risk |
| GRU | Deep Learning | Similar to LSTM with fewer parameters | Similar computational considerations |
| TimeGPT/Prophet | Foundation Model | Transfer learning, robust to data variations | May require API access |

## Results

The notebook generates:
- Price trend visualizations
- Correlation heatmaps
- Strategy performance comparisons
- Volatility analysis charts
- Portfolio efficient frontier plots
- Model performance rankings
- Comprehensive analysis reports

## Key Insights

- Deep learning models (LSTM, GRU) effectively capture temporal price patterns
- Feature engineering significantly improves traditional ML model performance
- Strong cryptocurrency correlations limit diversification benefits
- Moving average strategies show mixed results depending on market conditions
- Historical volatility has moderate predictive power for future movements
- Seasonal patterns exist but are relatively weak in crypto markets

## Performance Metrics

Models are evaluated using:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)
- Directional accuracy

## Customization

Users can modify:
- Cryptocurrency selection (supports all 100 in dataset)
- Moving average windows (currently 50/200-day)
- Model parameters (epochs, learning rates, etc.)
- Visualization settings
- Output directory paths

## Author

**Mohit Kishore**

Website: https://www.mohitkishore.com

This project represents ongoing research into quantitative finance and machine learning applications.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Disclaimer

This project is for educational and research purposes only. It should not be used for actual trading or investment decisions. Cryptocurrency markets are highly volatile and unpredictable. Past performance does not guarantee future results.

## Contributing

Contributions, feedback, and discussions are welcome! Feel free to:
- Open issues for bugs or suggestions
- Submit pull requests with improvements
- Share your research findings and insights

## Acknowledgments

- Kaggle for providing cryptocurrency price data
- Google Colab for cloud computing resources
- Open source communities for excellent ML libraries
- Research community for time series forecasting methodologies

## Contact

For questions, suggestions, or collaboration opportunities:
- Website: https://www.mohitkishore.com
- GitHub: [Your GitHub Profile]

---

**Last Updated**: December 2025

*This is a research project. It is actively being developed and refined.*
