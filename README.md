# AI Applications Research

A collection of research projects exploring different applications and implementations of artificial intelligence across various domains.

## About Me

I'm **Mohit Kishore**, an AI researcher and developer passionate about exploring practical applications of machine learning and artificial intelligence. Through these projects, I investigate how AI can solve real-world problems, optimize processes, and provide valuable insights across different industries.

**Website**: https://www.mohitkishore.com

## Project Goal

The goal of this workspace is to research and experiment with different applications of AI. Each project in this repository represents an exploration into specific AI use cases, methodologies, and implementations. These projects serve as both learning tools and demonstrations of AI capabilities in action.

## Projects

### BankTransactionClassifier - ContractorLens
A comparative research project evaluating machine learning algorithms for cross-platform identification of business vs. personal expenses for Canadian contractors with focus on CRA T2125 tax compliance.

- **Location**: `./BankTransactionClassifier/`
- **Main Notebook**: `ContractorLens_Training.ipynb` (Google Colab)
- **Technologies**: Logistic Regression, Linear SVM, LightGBM, DistilBERT, MobileBERT
- **Input Data**: Mitul Shah Transaction Categorization Dataset (Hugging Face)
- **Output Formats**: ONNX (for Next.js/Web), CoreML (for iOS/macOS)
- **Key Features**:
  - Multi-model comparative analysis (5 different algorithms)
  - Automated Google Drive integration for results storage
  - Canadian CRA T2125 category mappings
  - ONNX model export for web deployment
  - Comprehensive performance metrics and visualizations
- **Description**: Trains and compares 5 ML algorithms to classify bank transactions. Exports the best model to ONNX format for privacy-first browser-side inference, supporting deployment on both web and mobile platforms.

### CryptocurrencyAnalysisAndForecasting
A comprehensive analysis and forecasting system exploring machine learning algorithms for cryptocurrency price prediction and portfolio optimization.

- **Location**: `./CryptocurrencyAnalysisAndForecasting/`
- **Main Notebook**: `Cryptocurrency_Analysis_and_Forecasting.ipynb`
- **Technologies**: ARIMA, XGBoost, LSTM, GRU, TimeGPT/Prophet
- **Description**: Demonstrates time series forecasting, feature engineering, and comparative model evaluation in the cryptocurrency domain.

## Getting Started

Each project within this workspace is self-contained with its own documentation. Navigate to the specific project folder to:

1. Read the project-specific README
2. Review the Jupyter notebooks
3. Understand the methodology and results
4. Reproduce or extend the analysis

## Workspace Structure

```
AIApplications/
├── BankTransactionClassifier/
│   ├── README.md
│   ├── ContractorLens_Training.ipynb       # Google Colab notebook
│   ├── models/                             # Saved models and ONNX exports
│   ├── results/                            # Performance metrics and summaries
│   └── comparison_charts/                  # Visualization outputs
├── CryptocurrencyAnalysisAndForecasting/
│   └── Cryptocurrency_Analysis_and_Forecasting.ipynb
├── README.md                    # This file
├── LICENSE                      # MIT License
└── .gitignore
```

## License

All projects in this workspace are licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact & Collaboration

For questions, suggestions, or collaboration opportunities:
- **Website**: https://www.mohitkishore.com
- Feel free to reach out through the website

---

**Last Updated**: April 2026

*This is an ongoing research initiative exploring AI applications and methodologies.*
