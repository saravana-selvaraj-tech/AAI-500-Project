# Project Title:
Predicting Household Power Consumption Analysis for Smarter Decisions

### Project Status:
Preprocessing Complete | EDA Complete | Baseline Models Complete
USD - MS - Course - AA1-500 subject - Project work

## Project Overview

This project is a part of the AAI-500 course in the Applied Artificial Intelligence Program at the University of San Diego (USD). 
It analyzes household electric power consumption data to identify patterns, perform preprocessing, and build predictive models for energy consumption forecasting. The analysis covers almost 4 years of minute-level data from a single household (Dec 2006 - Nov 2010).

## Project Structure

```
AAI-500-Project/
├── data/
│   ├── raw/                      # Original dataset
│   │   └── household_power_consumption.txt
│   └── processed/                # Cleaned and processed data
│       ├── df_loaded.pkl
│       ├── df_cleaned.pkl
│       ├── df_features.pkl
│       └── feature_list.csv
├── notebooks/
│   ├── 00_main.ipynb            # Main orchestration notebook
│   ├── 01_data_loading.ipynb    # Data loading and initial exploration
│   ├── 02_data_cleaning.ipynb   # Data cleaning and preprocessing
│   ├── 03_exploratory_analysis.ipynb  # EDA with visualizations
│   ├── 04_bayesian_network_model_inference.ipynb   # Bayesian Model based evaluation and inference
│   ├── 05_linear_regression_model_analysis.ipynb # Regression model based prediction and best model selection
│   └── 06_conclusions_and_recommendations.ipynb  # Conclusions & recommendations
├── outputs/
│   ├── figures/                 # Generated visualizations (20+ plots)
│   ├── baseline_results.csv     # Model performance metrics
│   ├── feature_importance.csv   # Feature importance rankings
│   ├── rf_baseline_model.pkl    # Trained Random Forest model
│   └── scaler.pkl              # Feature scaler
├── src/                         # Python modules (future development)
├── reports/                     # Analysis reports
│   ├── PROJECT_SUMMARY.md       # Complete project summary
│   └── REPORT_STRUCTURE_GUIDE.md # Guide for creating technical report
├── requirements.txt             # Python dependencies
├── LICENSE
└── README.md                    # This file
```

## Installation

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab

### Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd AAI-500-Project
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Launch Jupyter:
```bash
jupyter notebook
```

## Usage

### Option 1: Run Complete Pipeline
Open and execute `notebooks/00_main.ipynb` - this provides an overview and guides you through the entire analysis.

### Option 2: Run Individual Notebooks
Execute notebooks in sequence:

1. **01_data_loading.ipynb** - Load and examine the dataset
   - Initial data exploration
   - Missing value detection
   - Date range verification
   
2. **02_data_cleaning.ipynb** - Clean and preprocess data
   - Handle missing values (imputation/removal)
   - Remove duplicates
   - Detect and treat outliers
   - Create basic time features
   
3. **03_exploratory_analysis.ipynb** - Perform EDA
   - Statistical analysis
   - Statistical hypothesis testing (t-tests, chi-squared)
   - Confidence intervals (95% CI)
   - Distribution visualization
   - Temporal pattern discovery
   - Correlation analysis
   - Sub-metering comparison
   - Anomaly detection
   
4. **04_bayesian_network_model_inference.ipynb** - Inferences
   - Dataset preparation and remove highly correlated columns
   - Data variables discretization
   - Train/test dataset split - 70/30
   - Evaluating using TreeSearch and HillClimbSearch Bayesian Network modesl
   - Estimation and model fitting
   - Creating CPDs and model validity checking 
   - Inference from both models based estimations
   - Compute BIC and K2 score for better model determination
   
5. **05_linear_regression_model_analysis.ipynb** - Build baseline models and selection
   - Identify dependent and independent variables
   - Find out high co-related independent varaibles and remove them (if any) before analysis
   - Perform Multi-Linear regression analysis for different models 
     - Model1 : Electrical Variables
     - Model 2 : Electrical + Time Variables
     - Model 3 : Electrical + Time + Season Variables
     - Target: Global_active_power
  - Select the model that performs better on results obtained from all model analysis

## Dataset

**Individual Household Electric Power Consumption Dataset**
- **Records**: ~2 million measurements
- **Frequency**: 1-minute sampling rate
- **Features**: 9 variables including:
  - Global active/reactive power
  - Voltage and current intensity
  - Sub-metering for 3 different zones (Kitchen, Laundry, Water Heater & AC)
- **Size of dataset**: 120 MB
- **Dataset source**: UCI Machine Learning Repository

## Key Features

### Data Processing
- Comprehensive missing value handling
- Outlier detection using IQR and winsorization
- Duplicate removal
- Time-based feature extraction

### Visualizations
The project generates 25+ plots including:
- Distribution plots
- Temporal patterns (hourly, daily, monthly, seasonal)
- Statistical test results (confidence intervals, error bars)
- Correlation heatmaps
- Sub-metering comparisons
- Feature importance charts
- Model performance comparisons
- Prediction vs actual plots
- Residual analysis

### Modeling
- Multiple baseline models for comparison
- Comprehensive evaluation metrics (MAE, RMSE, R², MAPE)
- Feature importance ranking
- Residual analysis
- Time series cross-validation ready

## Methodology

### Techniques Implemented
- Time series preprocessing
- Statistical imputation
- Statistical hypothesis testing
  - Independent t-tests (weekend vs weekday, seasonal comparisons)
  - Chi-squared tests for independence
  - 95% confidence intervals
  - Bonferroni correction for multiple comparisons
- Outlier treatment (winsorization)
- Feature engineering (domain-knowledge driven)
- Feature scaling (StandardScaler)
- Multiple baseline models
- Comprehensive evaluation framework

## Results

### Key Insights
- **Peak consumption**: Evening hours (6-9 PM)
- **Low consumption**: Early morning (2-5 AM)
- **Seasonal variation**: Winter months show higher consumption
- **Weekend vs Weekday**: Weekend consumption is **statistically significantly higher** (p < 0.000001)
  - Weekend mean: 1.22 kW (95% CI: [1.22, 1.22])
  - Weekday mean: 1.03 kW (95% CI: [1.03, 1.03])
  - Difference: 0.19 kW
- **Temporal Independence**: Season and Time of Day are independent (χ² test, p = 0.999)
- **Sub-metering**: Kitchen and Water Heater/AC are major consumers
- **Unmetered power**: Significant portion not captured by sub-meters

### Model Performance
- Bayesian Network model based inferences - Using TreeSearch and ClimbSearch techniques
- Baseline models established Multi Linear Regressions
- Further improvements possible with advanced techniques

## Future Enhancements

### Advanced Modeling
- Gradient Boosting (XGBoost, LightGBM)
- LSTM/GRU networks for sequence modeling
- ARIMA/Prophet for time series forecasting
- Ensemble methods

### Feature Selection
- Recursive Feature Elimination (RFE)
- LASSO regularization
- SHAP value analysis

### Deployment
- Model packaging for production
- Real-time prediction API
- Anomaly detection system
- Energy optimization recommendations

## Contributors
- Vivek Shivaram
- Saravana S

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the terms specified in the LICENSE file.

## Acknowledgments

- Dataset source: UCI Machine Learning Repository
- Individual Household Electric Power Consumption Dataset
- Anuj S for the support

## Contact

For questions or suggestions, please open an issue in the repository.

---


