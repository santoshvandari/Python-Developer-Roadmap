# Data Analysis Dashboard Project

Build an interactive data visualization dashboard to analyze and present data insights.

## Project Overview

**What you'll build**: A data dashboard that loads datasets, performs analysis, creates visualizations, and presents insights through an interactive interface.

**What you'll learn**:
- Data manipulation with pandas
- Data visualization with matplotlib and plotly
- Statistical analysis and insights
- Dashboard creation with Streamlit or Dash
- Data cleaning and preprocessing
- Interactive plotting and filtering

## Project Features

### Core Features
- Load data from CSV, JSON, and Excel files
- Basic data exploration and statistics
- Create charts and graphs
- Filter and sort data
- Export visualizations
- Simple dashboard layout

### Advanced Features
- Real-time data updates
- Interactive filtering and drilling down
- Multiple data source integration
- Advanced statistical analysis
- Custom visualization types
- Dashboard sharing and deployment

## Implementation Guide

### Phase 1: Data Loading and Exploration
**Time**: 3-4 hours

Start with basic data operations:
- Load and display datasets
- Basic statistics and summaries
- Data cleaning and preprocessing
- Simple matplotlib charts

**Key concepts**: pandas basics, data exploration, basic plotting

### Phase 2: Interactive Visualizations
**Time**: 4-5 hours

Create dynamic charts:
- Interactive plots with plotly
- Multiple chart types
- Data filtering and selection
- Chart customization

**Key concepts**: Interactive plotting, data filtering, visualization design

### Phase 3: Dashboard Interface
**Time**: 4-5 hours

Build dashboard framework:
- Streamlit or Dash setup
- Layout design and organization
- User controls and widgets
- Multi-page navigation

**Key concepts**: Dashboard frameworks, UI components, layout design

### Phase 4: Advanced Analytics
**Time**: 5-6 hours

Add sophisticated analysis:
- Trend analysis and forecasting
- Correlation and regression analysis
- Statistical significance testing
- Machine learning insights

**Key concepts**: Statistical analysis, machine learning, advanced visualization

## Getting Started

### Required Libraries
```bash
pip install pandas matplotlib plotly streamlit seaborn scikit-learn numpy
```

### Basic Setup
```python
import pandas as pd
import matplotlib.pyplot as plt
import plotly.express as px
import plotly.graph_objects as go
import streamlit as st
import seaborn as sns
import numpy as np
from datetime import datetime, timedelta

class DataDashboard:
    def __init__(self):
        self.data = None
        self.charts = {}
        self.filters = {}
    
    def load_data(self, file_path):
        # Load data from various file formats
        pass
    
    def create_chart(self, chart_type, x_col, y_col, **kwargs):
        # Generate different types of charts
        pass
```

## Data Loading and Processing

### Data Loader Class
```python
class DataLoader:
    @staticmethod
    def load_csv(file_path, **kwargs):
        try:
            return pd.read_csv(file_path, **kwargs)
        except Exception as e:
            st.error(f"Error loading CSV: {e}")
            return None
    
    @staticmethod
    def load_excel(file_path, **kwargs):
        try:
            return pd.read_excel(file_path, **kwargs)
        except Exception as e:
            st.error(f"Error loading Excel: {e}")
            return None
    
    @staticmethod
    def load_json(file_path, **kwargs):
        try:
            return pd.read_json(file_path, **kwargs)
        except Exception as e:
            st.error(f"Error loading JSON: {e}")
            return None

class DataProcessor:
    @staticmethod
    def clean_data(df):
        # Remove duplicates
        df = df.drop_duplicates()
        
        # Handle missing values
        numeric_columns = df.select_dtypes(include=[np.number]).columns
        df[numeric_columns] = df[numeric_columns].fillna(df[numeric_columns].median())
        
        # Handle categorical missing values
        categorical_columns = df.select_dtypes(include=['object']).columns
        df[categorical_columns] = df[categorical_columns].fillna('Unknown')
        
        return df
    
    @staticmethod
    def detect_data_types(df):
        type_info = {}
        for column in df.columns:
            if pd.api.types.is_numeric_dtype(df[column]):
                type_info[column] = 'numeric'
            elif pd.api.types.is_datetime64_any_dtype(df[column]):
                type_info[column] = 'datetime'
            else:
                type_info[column] = 'categorical'
        return type_info
```

## Visualization Components

### Chart Generator
```python
class ChartGenerator:
    def __init__(self, data):
        self.data = data
    
    def create_line_chart(self, x_col, y_col, color_col=None, title=None):
        fig = px.line(
            self.data, 
            x=x_col, 
            y=y_col, 
            color=color_col,
            title=title or f'{y_col} over {x_col}'
        )
        return fig
    
    def create_bar_chart(self, x_col, y_col, color_col=None, title=None):
        fig = px.bar(
            self.data,
            x=x_col,
            y=y_col,
            color=color_col,
            title=title or f'{y_col} by {x_col}'
        )
        return fig
    
    def create_scatter_plot(self, x_col, y_col, size_col=None, color_col=None, title=None):
        fig = px.scatter(
            self.data,
            x=x_col,
            y=y_col,
            size=size_col,
            color=color_col,
            title=title or f'{y_col} vs {x_col}'
        )
        return fig
    
    def create_histogram(self, column, bins=30, title=None):
        fig = px.histogram(
            self.data,
            x=column,
            nbins=bins,
            title=title or f'Distribution of {column}'
        )
        return fig
    
    def create_box_plot(self, x_col, y_col, title=None):
        fig = px.box(
            self.data,
            x=x_col,
            y=y_col,
            title=title or f'{y_col} distribution by {x_col}'
        )
        return fig
    
    def create_correlation_heatmap(self, columns=None):
        if columns:
            correlation_data = self.data[columns].corr()
        else:
            numeric_data = self.data.select_dtypes(include=[np.number])
            correlation_data = numeric_data.corr()
        
        fig = px.imshow(
            correlation_data,
            title='Correlation Heatmap',
            color_continuous_scale='RdBu',
            aspect='auto'
        )
        return fig
```

## Streamlit Dashboard

### Main Dashboard App
```python
def main():
    st.set_page_config(
        page_title="Data Analysis Dashboard",
        page_icon="📊",
        layout="wide"
    )
    
    st.title("📊 Data Analysis Dashboard")
    st.sidebar.title("Navigation")
    
    # Sidebar navigation
    page = st.sidebar.selectbox(
        "Choose a page",
        ["Data Upload", "Data Overview", "Visualizations", "Analysis", "Export"]
    )
    
    # Initialize session state
    if 'data' not in st.session_state:
        st.session_state.data = None
    
    if page == "Data Upload":
        data_upload_page()
    elif page == "Data Overview":
        data_overview_page()
    elif page == "Visualizations":
        visualizations_page()
    elif page == "Analysis":
        analysis_page()
    elif page == "Export":
        export_page()

def data_upload_page():
    st.header("📁 Data Upload")
    
    upload_method = st.radio(
        "Choose upload method:",
        ["File Upload", "Sample Datasets"]
    )
    
    if upload_method == "File Upload":
        uploaded_file = st.file_uploader(
            "Choose a file",
            type=['csv', 'xlsx', 'json']
        )
        
        if uploaded_file is not None:
            try:
                if uploaded_file.name.endswith('.csv'):
                    df = pd.read_csv(uploaded_file)
                elif uploaded_file.name.endswith('.xlsx'):
                    df = pd.read_excel(uploaded_file)
                elif uploaded_file.name.endswith('.json'):
                    df = pd.read_json(uploaded_file)
                
                st.session_state.data = df
                st.success(f"Successfully loaded {df.shape[0]} rows and {df.shape[1]} columns")
                
                # Show preview
                st.subheader("Data Preview")
                st.dataframe(df.head())
                
            except Exception as e:
                st.error(f"Error loading file: {e}")
    
    else:
        # Sample datasets
        dataset_choice = st.selectbox(
            "Choose a sample dataset:",
            ["Sales Data", "Stock Prices", "Weather Data"]
        )
        
        if st.button("Load Sample Data"):
            df = load_sample_data(dataset_choice)
            st.session_state.data = df
            st.success(f"Loaded sample dataset: {dataset_choice}")
            st.dataframe(df.head())

def data_overview_page():
    st.header("📋 Data Overview")
    
    if st.session_state.data is None:
        st.warning("Please upload data first!")
        return
    
    df = st.session_state.data
    
    # Basic info
    col1, col2, col3, col4 = st.columns(4)
    
    with col1:
        st.metric("Rows", df.shape[0])
    with col2:
        st.metric("Columns", df.shape[1])
    with col3:
        st.metric("Memory Usage", f"{df.memory_usage(deep=True).sum() / 1024:.1f} KB")
    with col4:
        st.metric("Missing Values", df.isnull().sum().sum())
    
    # Data types
    st.subheader("Column Information")
    col_info = pd.DataFrame({
        'Column': df.columns,
        'Data Type': df.dtypes,
        'Non-Null Count': df.count(),
        'Null Count': df.isnull().sum()
    })
    st.dataframe(col_info)
    
    # Statistical summary
    st.subheader("Statistical Summary")
    st.dataframe(df.describe())
    
    # Data quality issues
    st.subheader("Data Quality Check")
    duplicates = df.duplicated().sum()
    if duplicates > 0:
        st.warning(f"Found {duplicates} duplicate rows")
    else:
        st.success("No duplicate rows found")

def visualizations_page():
    st.header("📈 Visualizations")
    
    if st.session_state.data is None:
        st.warning("Please upload data first!")
        return
    
    df = st.session_state.data
    chart_gen = ChartGenerator(df)
    
    # Chart type selection
    chart_type = st.selectbox(
        "Select Chart Type",
        ["Line Chart", "Bar Chart", "Scatter Plot", "Histogram", "Box Plot", "Correlation Heatmap"]
    )
    
    if chart_type == "Line Chart":
        col1, col2 = st.columns(2)
        with col1:
            x_col = st.selectbox("X-axis", df.columns)
        with col2:
            y_col = st.selectbox("Y-axis", df.select_dtypes(include=[np.number]).columns)
        
        if st.button("Generate Chart"):
            fig = chart_gen.create_line_chart(x_col, y_col)
            st.plotly_chart(fig, use_container_width=True)
    
    elif chart_type == "Bar Chart":
        col1, col2 = st.columns(2)
        with col1:
            x_col = st.selectbox("X-axis", df.columns)
        with col2:
            y_col = st.selectbox("Y-axis", df.select_dtypes(include=[np.number]).columns)
        
        if st.button("Generate Chart"):
            fig = chart_gen.create_bar_chart(x_col, y_col)
            st.plotly_chart(fig, use_container_width=True)
    
    elif chart_type == "Correlation Heatmap":
        numeric_cols = df.select_dtypes(include=[np.number]).columns.tolist()
        selected_cols = st.multiselect("Select columns for correlation", numeric_cols, default=numeric_cols[:5])
        
        if st.button("Generate Heatmap") and selected_cols:
            fig = chart_gen.create_correlation_heatmap(selected_cols)
            st.plotly_chart(fig, use_container_width=True)
```

## Advanced Analytics

### Statistical Analysis
```python
class StatisticalAnalysis:
    def __init__(self, data):
        self.data = data
    
    def trend_analysis(self, date_col, value_col):
        # Simple trend analysis using linear regression
        from scipy import stats
        
        df_sorted = self.data.sort_values(date_col)
        x = np.arange(len(df_sorted))
        y = df_sorted[value_col]
        
        slope, intercept, r_value, p_value, std_err = stats.linregress(x, y)
        
        return {
            'slope': slope,
            'r_squared': r_value**2,
            'p_value': p_value,
            'trend': 'increasing' if slope > 0 else 'decreasing'
        }
    
    def correlation_analysis(self, columns=None):
        if columns:
            data_subset = self.data[columns]
        else:
            data_subset = self.data.select_dtypes(include=[np.number])
        
        correlation_matrix = data_subset.corr()
        
        # Find strongest correlations
        strong_correlations = []
        for i in range(len(correlation_matrix.columns)):
            for j in range(i+1, len(correlation_matrix.columns)):
                corr_value = correlation_matrix.iloc[i, j]
                if abs(corr_value) > 0.5:  # Threshold for strong correlation
                    strong_correlations.append({
                        'var1': correlation_matrix.columns[i],
                        'var2': correlation_matrix.columns[j],
                        'correlation': corr_value
                    })
        
        return strong_correlations
    
    def outlier_detection(self, column):
        Q1 = self.data[column].quantile(0.25)
        Q3 = self.data[column].quantile(0.75)
        IQR = Q3 - Q1
        
        lower_bound = Q1 - 1.5 * IQR
        upper_bound = Q3 + 1.5 * IQR
        
        outliers = self.data[
            (self.data[column] < lower_bound) | 
            (self.data[column] > upper_bound)
        ]
        
        return outliers
```

## Sample Data Generators

### Generate Sample Datasets
```python
def load_sample_data(dataset_type):
    if dataset_type == "Sales Data":
        dates = pd.date_range('2023-01-01', '2023-12-31', freq='D')
        np.random.seed(42)
        
        return pd.DataFrame({
            'date': dates,
            'sales': np.random.normal(1000, 200, len(dates)) + 
                    50 * np.sin(np.arange(len(dates)) * 2 * np.pi / 365),
            'region': np.random.choice(['North', 'South', 'East', 'West'], len(dates)),
            'product': np.random.choice(['A', 'B', 'C'], len(dates)),
            'customer_satisfaction': np.random.uniform(1, 5, len(dates))
        })
    
    elif dataset_type == "Stock Prices":
        dates = pd.date_range('2023-01-01', '2023-12-31', freq='D')
        price = 100
        prices = []
        
        for _ in dates:
            price += np.random.normal(0, 2)
            prices.append(max(price, 10))  # Ensure positive prices
        
        return pd.DataFrame({
            'date': dates,
            'price': prices,
            'volume': np.random.normal(1000000, 200000, len(dates)),
            'company': np.random.choice(['AAPL', 'GOOGL', 'MSFT'], len(dates))
        })
    
    elif dataset_type == "Weather Data":
        dates = pd.date_range('2023-01-01', '2023-12-31', freq='D')
        
        return pd.DataFrame({
            'date': dates,
            'temperature': 20 + 10 * np.sin(np.arange(len(dates)) * 2 * np.pi / 365) + 
                          np.random.normal(0, 3, len(dates)),
            'humidity': np.random.uniform(30, 90, len(dates)),
            'rainfall': np.random.exponential(2, len(dates)),
            'city': np.random.choice(['New York', 'London', 'Tokyo'], len(dates))
        })
```

## Dashboard Deployment

### Running the Dashboard
```bash
# Save your main code as dashboard.py
streamlit run dashboard.py

# The dashboard will be available at http://localhost:8501
```

### Configuration File
```toml
# .streamlit/config.toml
[theme]
base = "light"
primaryColor = "#1f77b4"
backgroundColor = "#ffffff"
secondaryBackgroundColor = "#f0f2f6"
textColor = "#262730"

[server]
port = 8501
maxUploadSize = 200
```

## Testing Your Dashboard

### Test Scenarios
- Upload different file formats and sizes
- Test with missing or corrupted data
- Verify chart generation with various data types
- Test filtering and interactive features
- Check performance with large datasets

## Extensions and Improvements

### Beginner Extensions
- Add more chart types (pie charts, area charts)
- Implement data filtering widgets
- Add export functionality for charts
- Create data summary reports

### Intermediate Extensions
- Real-time data streaming
- Machine learning model integration
- Advanced statistical tests
- Custom color themes and styling

### Advanced Extensions
- Multi-user authentication and sharing
- Database integration for large datasets
- Advanced forecasting and prediction models
- Integration with BI tools and APIs

## Learning Outcomes

After completing this project, you'll understand:
- Data manipulation and analysis with pandas
- Data visualization principles and techniques
- Interactive dashboard development
- Statistical analysis and interpretation
- User interface design for data applications
- Data storytelling and presentation

## File Structure

```
data_dashboard/
├── dashboard.py          # Main Streamlit app
├── components/
│   ├── data_loader.py    # Data loading utilities
│   ├── chart_generator.py # Visualization components
│   └── analytics.py      # Statistical analysis
├── sample_data/
│   ├── sales.csv         # Sample datasets
│   ├── stocks.csv
│   └── weather.csv
├── .streamlit/
│   └── config.toml       # Streamlit configuration
├── requirements.txt      # Dependencies
└── README.md             # Project documentation
```

## Next Steps

Once you've completed your data dashboard:
1. Deploy it to Streamlit Cloud or Heroku
2. Add your own datasets and create custom analyses
3. Share with colleagues and get feedback
4. Explore advanced machine learning integrations
5. Consider building specialized dashboards for specific domains

Fantastic work on building a comprehensive data analysis tool!