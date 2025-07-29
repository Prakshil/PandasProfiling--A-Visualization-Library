# Pandas Profiling - A Visualization Library

This project demonstrates the use of **ydata-profiling** (formerly pandas-profiling), a powerful Python library that generates comprehensive exploratory data analysis (EDA) reports from pandas DataFrames with just a few lines of code.

## 📊 About Pandas Profiling (ydata-profiling)

**ydata-profiling** is an open-source Python library that automatically generates detailed statistical reports for datasets. It provides:

- **Comprehensive Overview**: Dataset statistics, missing values, data types
- **Variable Analysis**: Distribution plots, descriptive statistics for each column
- **Correlation Analysis**: Pearson, Spearman, and Kendall correlation matrices
- **Missing Data Visualization**: Patterns and heatmaps of missing values
- **Duplicate Detection**: Identification of duplicate rows
- **Data Quality Warnings**: Alerts for potential data quality issues

### Key Features:
- ✅ One-line report generation
- ✅ Interactive HTML reports
- ✅ Support for large datasets
- ✅ Customizable report configurations
- ✅ Integration with Jupyter notebooks
- ✅ Export to multiple formats (HTML, JSON)

## 🚀 Getting Started

### Prerequisites

```bash
pip install ydata-profiling pandas
```

### Basic Usage

```python
import pandas as pd
from ydata_profiling import ProfileReport

# Load your dataset
df = pd.read_csv('your_dataset.csv')

# Generate the profile report
profile = ProfileReport(df, title='Your Dataset Profiling Report', explorative=True)

# Save to HTML file
profile.to_file("report.html")
```

## 📁 Project Structure

```
├── pandasprofiling.ipynb    # Main Jupyter notebook with profiling code
├── train.csv               # Sample dataset (Titanic dataset)
├── output.html            # Generated profiling report
└── README.md              # This file
```

## 🔧 Step-by-Step Tutorial

### Step 1: Install Required Libraries

```bash
pip install ydata-profiling pandas jupyter
```

### Step 2: Import Libraries

```python
import pandas as pd
from ydata_profiling import ProfileReport
```

### Step 3: Load Your Dataset

```python
# Replace 'train.csv' with your dataset file
df = pd.read_csv('train.csv')
```

### Step 4: Generate Profile Report

```python
# Basic report
profile = ProfileReport(df)

# Advanced report with customizations
profile = ProfileReport(
    df, 
    title='Dataset Profiling Report',
    explorative=True,          # Enable advanced features
    dark_mode=True,           # Dark theme (optional)
    orange_mode=True          # Orange color scheme (optional)
)
```

### Step 5: Export Report

```python
# Save as HTML file
profile.to_file("output.html")

# Display in Jupyter notebook
profile.to_widgets()

# Save as JSON
profile.to_file("report.json")
```

## 📚 Advanced Configuration

### Customizing Reports

```python
from ydata_profiling import ProfileReport

# Custom configuration
profile = ProfileReport(
    df,
    title="Advanced Profiling Report",
    explorative=True,
    config_file="config.yaml"  # Use custom config file
)

# Disable specific sections
profile = ProfileReport(
    df,
    title="Minimal Report",
    minimal=True,              # Generate minimal report
    correlations={
        "auto": {"calculate": False}
    },
    missing_diagrams={
        "heatmap": False
    }
)
```

### Performance Optimization

```python
# For large datasets
profile = ProfileReport(
    df,
    minimal=True,              # Faster processing
    samples={"head": 1000, "tail": 1000},  # Sample data
    correlations={"auto": {"calculate": False}}  # Skip correlations
)
```

## 🎯 Use Cases

### 1. **Initial Data Exploration**
- Quickly understand dataset structure
- Identify data quality issues
- Discover patterns and anomalies

### 2. **Data Quality Assessment**
- Find missing values and patterns
- Detect duplicates
- Identify outliers

### 3. **Feature Engineering Insights**
- Understand variable distributions
- Find correlations between features
- Identify highly cardinality variables

### 4. **Report Generation for Stakeholders**
- Create professional EDA reports
- Share insights with non-technical team members
- Document data exploration process

## 🛠️ Troubleshooting

### Common Issues:

1. **Installation Issues**
   ```bash
   pip install --upgrade ydata-profiling
   ```

2. **Memory Issues with Large Datasets**
   ```python
   profile = ProfileReport(df, minimal=True)
   ```

3. **Slow Performance**
   ```python
   # Use sampling for large datasets
   sample_df = df.sample(n=10000)
   profile = ProfileReport(sample_df)
   ```

## 📖 Additional Resources

### Official Documentation
- [ydata-profiling Documentation](https://docs.profiling.ydata.ai/)
- [GitHub Repository](https://github.com/ydataai/ydata-profiling)

### Example Datasets to Try
- Titanic Dataset (included in this project)
- Iris Dataset
- Boston Housing Dataset
- Any CSV dataset

### Alternative Libraries
- **Sweetviz**: Another automated EDA library
- **AutoViz**: Automatic visualization library
- **DataPrep**: Data preparation and exploration

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is open source and available under the MIT License.

## 📞 Support

If you encounter any issues or have questions:
- Check the [official documentation](https://docs.profiling.ydata.ai/)
- Open an issue on the [GitHub repository](https://github.com/ydataai/ydata-profiling/issues)
- Join the community discussions

---

**Happy Data Exploration! 🎉**

> *This project demonstrates the power of automated EDA tools in accelerating the data science workflow.*
