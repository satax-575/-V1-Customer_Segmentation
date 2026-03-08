# Customer Segmentation Analysis - Online Retail

A comprehensive customer segmentation analysis project using the Online Retail dataset. This project performs exploratory data analysis (EDA), data preprocessing, outlier detection and treatment, feature engineering, and text preprocessing on retail transaction data.

## 📊 Project Overview

This notebook analyzes online retail transaction data to prepare it for customer segmentation. The analysis includes extensive data cleaning, outlier handling, and feature engineering to create meaningful customer segments.

## 🎯 Key Features

- **Data Cleaning & Preprocessing**
  - Handling missing values and duplicates
  - Feature engineering from transaction timestamps (Year, Month, Hour)
  - Log transformation for skewed numerical features
  - Advanced outlier detection and treatment using IQR and quantile-based capping

- **Exploratory Data Analysis**
  - Distribution analysis with histograms and KDE plots
  - Boxplot visualizations for outlier detection
  - Temporal analysis (monthly, hourly patterns)
  - Correlation analysis

- **Text Preprocessing (NLP)**
  - Text normalization and cleaning
  - Lemmatization using NLTK
  - Removal of special characters and Unicode normalization
  - Feature vectorization preparation

- **Feature Engineering**
  - Quantity aggregation ("Quantities Involved")
  - Temporal feature extraction
  - Price normalization and transformation

## 📦 Dataset

The project uses the **Online Retail** dataset, which contains transactions from a UK-based online retail company. The dataset includes:
- InvoiceNo: Transaction identifier
- StockCode: Product code
- Description: Product description
- Quantity: Number of items purchased
- InvoiceDate: Transaction timestamp
- UnitPrice: Price per unit
- CustomerID: Unique customer identifier
- Country: Customer's country

## 🛠️ Technologies Used

- **Python 3.x**
- **Libraries:**
  - `pandas` - Data manipulation and analysis
  - `numpy` - Numerical computing
  - `matplotlib` - Data visualization
  - `seaborn` - Statistical data visualization
  - `nltk` - Natural language processing
  - `scikit-learn` - Feature extraction and preprocessing

## 📁 Project Structure

```
.
├── _P2U_Cust_Segmentation.ipynb    # Main Jupyter notebook
├── Online Retail.xlsx               # Dataset (not included)
└── README.md                        # Project documentation
```

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas numpy matplotlib seaborn nltk scikit-learn openpyxl
```

### NLTK Data Dependencies

```python
import nltk
nltk.download('wordnet')
```

### Running the Analysis

1. Clone the repository
2. Place the `Online Retail.xlsx` file in the project directory
3. Open and run the Jupyter notebook:
```bash
jupyter notebook _P2U_Cust_Segmentation.ipynb
```

## 📈 Analysis Pipeline

### 1. Data Loading & Initial Exploration
- Load data from Excel
- Check data structure, shape, and data types
- Identify missing values and duplicates

### 2. Data Cleaning
- Remove duplicate records
- Drop unique identifiers (CustomerID, InvoiceNo)
- Handle missing values in Description field
- Extract temporal features from InvoiceDate

### 3. Outlier Detection & Treatment
- **Initial Detection:**
  - Visualize distributions with boxplots and histograms
  - Identify negative prices and extreme values
  
- **Treatment Strategy:**
  - Remove negative prices
  - Apply log transformation to reduce skewness
  - Use quantile-based capping (0.01 - 0.99 percentiles)
  - Further refinement with 0.01 - 0.95 percentiles for remaining outliers

### 4. Feature Engineering
- Create "Quantities Involved" aggregate feature
- Extract Year, Month, and Hour from timestamps
- Round numerical features to appropriate precision

### 5. Text Preprocessing
- Convert descriptions to lowercase
- Remove special characters and punctuation
- Apply Unicode normalization (NFC)
- Lemmatize words using WordNet lemmatizer
- Prepare for text vectorization

## 🔍 Key Insights

- **Data Quality:** The dataset required extensive cleaning with duplicate removal and outlier treatment
- **Temporal Patterns:** Analysis reveals shopping patterns across different months and hours
- **Price Distribution:** Highly skewed, requiring log transformation and capping
- **Quantity Distribution:** Contains outliers and return transactions (negative quantities)

## 📊 Visualizations

The notebook includes comprehensive visualizations:
- Distribution plots for all numerical features
- Boxplots for outlier detection
- Temporal analysis plots (price/quantity by month and hour)
- Before/after comparisons for outlier treatment

## 🎯 Next Steps

This preprocessing pipeline prepares the data for:
- Customer segmentation using clustering algorithms (K-Means, DBSCAN, Hierarchical)
- RFM (Recency, Frequency, Monetary) analysis
- Customer lifetime value prediction
- Market basket analysis

## 📝 Notes

- The analysis uses aggressive outlier treatment to ensure data quality
- Text preprocessing is optimized for English product descriptions
- Log transformations help normalize highly skewed distributions
- Quantile-based capping preserves data while controlling extreme values

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is available for educational and research purposes.

## 👤 Author

Data Science Project - Customer Segmentation Analysis

---

**Note:** This project is part of a customer segmentation initiative and focuses on the data preprocessing phase. The actual segmentation models will be implemented in subsequent phases.
