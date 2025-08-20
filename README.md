# 🏦 Loan Approval Predictor

[![Python Version](https://img.shields.io/badge/python-3.7%2B-blue.svg)](https://python.org)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> An intelligent machine learning system for predicting loan approval decisions with 97%+ accuracy.

## Features

- **Automated Analysis**: Complete end-to-end ML pipeline from data loading to model evaluation
- **Smart Data Handling**: Auto-detects target columns, handles missing values, and removes ID columns
- **Class Imbalance Solution**: Uses SMOTE for handling imbalanced datasets
- **Multiple Models**: Compares Logistic Regression, Decision Tree, and Random Forest
- **Comprehensive EDA**: Automated exploratory data analysis with visualizations

## Quick Start

### Installation
```bash
git clone https://github.com/yourusername/loan-approval-predictor.git
cd loan-approval-predictor
pip install -r requirements.txt
```

### Usage
```python
from loan_approval_predictor import LoanApprovalPredictor

# Initialize and run complete analysis
predictor = LoanApprovalPredictor()
results = predictor.run_complete_analysis(file_path="loan_data.csv")

# Or use with DataFrame
results = predictor.run_complete_analysis(df=your_dataframe)
```

## Results

Tested on 4,269 loan applications:

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| **Decision Tree** | **97.89%** | **97.51%** | **96.90%** | **97.20%** |
| Random Forest | 97.66% | 97.79% | 95.98% | 96.88% |
| Logistic Regression | 93.21% | 90.77% | 91.33% | 91.05% |

## Data Format

Your CSV should have:
- A target column named `loan_status` (or similar) with values like `Approved/Rejected`
- Any mix of numerical and categorical features
- The system automatically handles data preprocessing

Example:
```csv
loan_id,education,income_annum,loan_amount,cibil_score,loan_status
L001,Graduate,500000,100000,750,Approved
L002,Not Graduate,300000,50000,650,Rejected
```

## What It Does

1. **Data Loading**: Loads CSV and performs initial exploration
2. **EDA**: Creates visualizations for data understanding
3. **Preprocessing**: Handles missing values, encodes categories, scales features
4. **Model Training**: Trains multiple ML models with SMOTE for class balance
5. **Evaluation**: Compares models and selects the best performer

## Requirements

```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
imbalanced-learn>=0.8.0
```

## Key Features

- **Auto Target Detection**: Finds target column automatically
- **Missing Value Handling**: Smart imputation strategies
- **Class Imbalance**: Adaptive SMOTE with fallback to undersampling
- **Model Comparison**: Visual charts comparing model performance
- **Error Handling**: Robust error messages and edge case handling

## File Structure

```
loan-approval-predictor/
├── loan_approval_predictor.py    # Main prediction system
├── requirements.txt              # Dependencies
├── README.md                    # This file
└── data/                        # Your datasets
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License - see [LICENSE](LICENSE) file for details.
