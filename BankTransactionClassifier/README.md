# ContractorLens: Canadian Transaction Classification for Tax Compliance

A comparative research project evaluating machine learning algorithms for cross-platform identification of business vs. personal expenses for Canadian contractors.

## Overview

This project explores the intersection of financial technology and Canadian tax compliance. It focuses on training and deploying models that can accurately classify raw bank transaction strings into CRA-approved T1 General (T2125) categories. The primary goal is to identify the most efficient algorithm capable of running locally on both Next.js (Web/ONNX) and iOS (Mobile/CoreML) environments to ensure user privacy and low latency.

## Key Features

### Multi-Model Research

Compares 5 distinct algorithms to determine the optimal balance between accuracy and edge-device performance:

- **LightGBM**: Gradient boosting optimized for tabular features and high speed.
- **Linear SVM**: High-precision baseline for text-based classification.
- **Logistic Regression**: Robust statistical model using N-gram feature extraction.
- **DistilBERT**: A compressed Transformer model for deep semantic understanding.
- **MobileBERT**: Apple-optimized architecture for the iOS Neural Engine.

### Canadian Compliance Focus

- **T1 General Alignment**: Maps transactions directly to T2125 lines (e.g., Line 8810 for Office Supplies, Line 9281 for Motor Vehicle).
- **Personal vs. Business Split**: Specialized binary classification to filter non-deductible personal expenses.
- **Merchant Normalization**: Cleaning noisy Canadian descriptors (e.g., stripping "407 ETR" from "2024-10-05407 etr").

### Cross-Platform Deployment

- **ONNX Integration**: Exported models ready for onnxruntime-web in Next.js.
- **CoreML Conversion**: Optimized .mlpackage files for native iOS/macOS performance.
- **Browser-Side Inference**: Privacy-first design where financial data never leaves the user's device.

## Research Questions Addressed

1. **The Efficiency Gap**: Does a Transformer model provide enough accuracy gain over Classical ML to justify the 10x increase in model size?
2. **Noise Resilience**: Which algorithm best handles the inconsistent string formats of Canadian banks (e.g., varying store numbers and city abbreviations)?
3. **Platform Consistency**: Can a single model maintain identical classification results when running in a WASM-based browser environment versus a native Swift environment?
4. **CRA Accuracy**: How effectively can machine learning distinguish between a "Grey Area" merchant (e.g., Amazon) being used for business vs. personal purposes?
5. **On-Device Latency**: What is the maximum number of transactions a model can classify per second before impacting the mobile user experience?

## Tech Stack

- **Data**: Mitul Shah Transaction Dataset (Canadian Subset)
- **Training**: Python (Scikit-Learn, LightGBM, Hugging Face Transformers)
- **Hugging Face Dataset**: https://huggingface.co/datasets/mitulshah/transaction-categorization
- **Deployment**: ONNX (Web), CoreML (iOS/macOS)
- **Environment**: Google Colab for training and experimentation

## Project Structure

```
BankTransactionClassifier/
├── README.md
├── ContractorLens_Training.ipynb (Google Colab Notebook)
├── models/
│   ├── best_model.onnx
│   ├── best_model.pkl
│   └── model_metadata.json
├── results/
│   ├── model_comparison.csv
│   ├── comparison_charts/
│   └── performance_summary.json
└── data/
    └── preprocessed_transactions.csv
```

## Quick Start

1. Open [ContractorLens_Training.ipynb](./ContractorLens_Training.ipynb) in Google Colab
2. Follow the notebook cells to:
   - Install dependencies
   - Download and preprocess the dataset
   - Train and evaluate all 5 models
   - Compare performance metrics
   - Export the best model to ONNX format
3. Results are automatically saved to your Google Drive

## Model Comparison Results

See the `results/` directory for:
- `model_comparison.csv`: Detailed metrics for all models
- `comparison_charts/`: Visualizations of accuracy, precision, recall, and F1 scores
- `performance_summary.json`: Summary statistics and recommendations

## Next Steps

- Deploy the ONNX model to your Next.js web application
- Convert the best model to CoreML format for iOS deployment
- Integrate with the tax compliance workflow

## References

- [Hugging Face Transaction Categorization Dataset](https://huggingface.co/datasets/mitulshah/transaction-categorization)
- [CRA T1 General Form](https://www.canada.ca/taxes/individuals/topics/about-your-tax-return/tax-return/completing-a-tax-return/personal-income/line-10400-gross-self-employment-income)
- [ONNX Runtime Web](https://github.com/microsoft/onnxruntime-web)
- [CoreML Specification](https://github.com/apple/coreml-community-models)

## License

See LICENSE file in the root directory
