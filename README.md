## Analyzing Weekly Stock Prices from Yahoo Finance: A Step-by-Step Python Guide

### Introduction:

Financial data analysis is crucial for making informed investment decisions. In this tutorial, we will analyze historical weekly stock prices of various companies obtained from Yahoo Finance. We will use Python along with popular libraries such as pandas, matplotlib, and seaborn to clean, analyze, and visualize the data to uncover insights.

Follow the steps below to analyze your own stock data:

### Prerequisites

Before you begin, make sure you have Python installed, along with pandas, matplotlib, and seaborn libraries. You can install them using pip:

```
pip install pandas matplotlib seaborn
```

### Step 1: Import necessary libraries

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

### Step 2: Load and explore the data

Replace `your_file.csv` with the actual path of your CSV file:

```python
df = pd.read_csv("your_file.csv")
print(df.head())
```

### Step 3: Clean and preprocess the data

Check for missing values:

```python
print(df.isnull().sum())
```

If there are missing values, you can decide whether to drop or fill them:

```python
# Drop missing values
df = df.dropna()

# Or fill missing values (e.g., with the mean)
df = df.fillna(df.mean())
```

### Step 4: Perform exploratory data analysis (EDA)

Get a summary of the data:

```python
print(df.describe())
```

### Step 5: Calculate descriptive statistics

Calculate the correlation between the weekly prices of different companies:

```python
correlation_matrix = df.corr()
print(correlation_matrix)
```

### Step 6: Visualize the data

Create a heatmap to visualize the correlation between the companies:

```python
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.show()
```

Plot the weekly prices of a specific company (replace 'company_name' with the column name of the company you're interested in):

```python
plt.plot(df['company_name'])
plt.xlabel('Week')
plt.ylabel('Price')
plt.title('Weekly Price of Company Name')
plt.show()
```

### Conclusion

With this step-by-step guide, you can easily analyze and visualize historical weekly stock prices of different companies from Yahoo Finance. By adapting the provided code, you can further explore other aspects of the data and gain insights into stock price trends and correlations.

Happy analyzing!