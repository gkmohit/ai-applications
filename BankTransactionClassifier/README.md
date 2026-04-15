# ContractorLens: Canadian Transaction Classification for Tax Compliance

A comparative research project evaluating machine learning algorithms for cross-platform identification of business vs. personal expenses for Canadian contractors.

## Overview

This project explores the intersection of financial technology and Canadian tax compliance. It focuses on training and deploying models that can accurately classify raw bank transaction strings into CRA-approved T1 General (T2125) expense lines. The primary goal is to identify the most efficient algorithm capable of running locally on both Next.js (Web/ONNX) and iOS (Mobile/CoreML) environments to ensure user privacy and low latency.

### Key Capability: Multi-Transaction Classification

The system classifies transactions in two stages:
1. **Generic Classification**: Maps transaction descriptions to 10 generic financial categories (Food & Dining, Transportation, etc.)
2. **CRA Tax Mapping**: Converts generic categories to specific CRA T2125 expense lines (e.g., Line 8810 for Office Supplies, Line 9281 for Motor Vehicle Expenses)

This allows business owners and contractors to automatically categorize expenses for tax compliance purposes.

## Key Features

### Multi-Model Research

Compares 5 distinct algorithms to determine the optimal balance between accuracy and edge-device performance:

- **LightGBM**: Gradient boosting optimized for tabular features and high speed.
- **Linear SVM**: High-precision baseline for text-based classification.
- **Logistic Regression**: Robust statistical model using N-gram feature extraction.
- **DistilBERT**: A compressed Transformer model for deep semantic understanding.
- **MobileBERT**: Apple-optimized architecture for the iOS Neural Engine.

### Canadian Compliance Focus

- **T1 General Alignment**: Maps transactions directly to T2125 lines with CRA-accurate descriptions
- **Two-Stage Classification**: Generic category (what it is) → CRA Line (tax treatment)
- **Deductibility Rules**: Includes CRA deductibility percentages and business-use requirements
- **Global Transaction Support**: Handles transactions from any country; business owners using international cards are supported
- **10 Generic Categories**: Food & Dining, Transportation, Shopping & Retail, Entertainment, Healthcare, Utilities & Services, Financial Services, Income, Government & Legal, Charity & Donations

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

## Tech StackMulti-country: USA, UK, Canada, Australia, India)
- **Training**: Python (Scikit-Learn, LightGBM, Hugging Face Transformers)
- **Hugging Face Dataset**: https://huggingface.co/datasets/mitulshah/transaction-categorization (Gated - requires HF token)
- **Authentication**: Hugging Face token-based access via Colab secrets
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
### Step 1: Get Your Hugging Face Token
1. Visit https://huggingface.co/settings/tokens
2. Create a new token with "Read" permission
3. Copy the token (starts with `hf_`)

### Step 2: Run the Notebook
1. Open [CanadianTransactionClassifier-CTC.ipynb](./CanadianTransactionClassifier-CTC.ipynb) in Google Colab
2. In Colab sidebar, click the 🔑 **Secrets** icon
3. Add a new secret with:
   - **Name**: `HF_TOKEN`
   - **Value**: Your Hugging Face token
4. Click "Add secret" and restart the session
5. Follow the notebook cells to:
   - Install dependencies
   - Download and authenticate with Hugging Face
   - Preprocess the dataset with CRA T2125 mappings
   - Train and evaluate all 5 models
   - Compare performance metrics
   - Export the best model to ONNX format
6. Results are automatically saved to your Google Drive

### CRA T2125 Mapping
The notebook automatically maps transactions to CRA expense lines:
- GCRA T2125 Expense Lines Reference

The notebook maps to these common CRA T2125 expense lines:
- **Line 8720**: Professional Fees (legal, accounting, consulting)
- **Line 8800**: Office Expenses (utilities, insurance, general office)
- **Line 8810**: Office Supplies and Equipment
- **Line 8850**: Meals and Entertainment (50% deductible)
- **Line 9281**: Motor Vehicle Expenses

## Important Notes

- **Hugging Face API**: The dataset is gated and requires authentication. See Quick Start section.
- **Global Transactions**: The dataset and model support international transactions. Business owners using corporate cards abroad will have transactions properly classified.
- **Deductibility**: All mappings include CRA deductibility rules. Consult a tax professional for edge cases.
- **Personal vs. Business**: Users must still manually verify that transactions are for business purposes before deducting.

## References

- [Hugging Face Transaction Categorization Dataset](https://huggingface.co/datasets/mitulshah/transaction-categorization)
- [CRA T1 General Form - Schedule 8](https://www.canada.ca/taxes/individuals/topics/about-your-tax-return/tax-return/completing-a-tax-return/personal-income/line-10400-gross-self-employment-income)
- [CRA T2125 (Statement of Business Activities)](https://www.canada.ca/taxes/individuals/topics/about-your-tax-return/tax-return/completing-a-tax-return/personal-income/business-and-professional-income)
- [ONNX Runtime Web](https://github.com/microsoft/onnxruntime-web)
- [CoreML Specification](https://github.com/apple/coreml-community-models)
- [Hugging Face Tokens Documentation](https://huggingface.co/docs/hub/security-token

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
