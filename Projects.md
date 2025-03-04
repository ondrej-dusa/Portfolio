---
layout: default
---
# Projects

Here you can explore all the project I have been working on during my studies or personal research.

This project classifies emails using a Multinomial Naive Bayes model to predict labels (e.g., spam or not spam).

## [1. Email Classification Using Multinomial Naive Bayes](.Projects/Email Classification Using Multinomial Naive Bayes.html)

### Key Steps:

- **Data Collection**: Loads email dataset and prepares text data.
- **Preprocessing**: Cleans text by removing stopwords and applying stemming.
- **Feature Extraction**: Converts text into numerical features using CountVectorizer.
- **Model Training**: Trains the Multinomial Naive Bayes model on the data.
- **Evaluation**: Assesses model performance using a classification report.

Technologies: `Python`, `Pandas`, `NLTK`, `Scikit-learn`, `Google Colab`

Key Insight: Utilizes a probabilistic model to classify emails, with room for improvement in handling class imbalance and model accuracy.

## [2. Value at Risk (VaR) Analysis of AAPL Stock](./Projects/Risk Analysis and Value at Risk (VaR).html)

This project analyzes the Value at Risk (VaR) of Apple Inc. (AAPL) stock using historical, parametric, and Monte Carlo methods. 

### Key Steps:
- **Data Collection:** Fetches AAPL stock prices from Yahoo Finance and calculates log returns.
- **VaR Calculation:** Computes historical and parametric VaR at a 95% confidence level.
- **Monte Carlo Simulation:** Generates 10,000 return simulations to estimate risk.
- **Backtesting:** Counts exceptions to evaluate VaR model accuracy.
- **Visualization:** Plots return distribution with VaR thresholds.

Technologies: `R`, `quantmod`, `PerformanceAnalytics`, `ggplot2`, `dplyr`

**Key Insight**: A comparative analysis of different risk estimation techniques to assess potential losses.

## [3. Descriptive Statistics and Data Visualization of MPG Dataset](./Projects/Exploratory Data Analysis (EDA) of MPG Dataset.html)

This project explores the MPG dataset through descriptive statistics and visualization techniques to analyze acceleration and other key attributes.

### Key Steps:

- **Data Collection:** Loads and cleans the MPG dataset to ensure accurate analysis.
- **Descriptive Statistics:** Computes mean, standard deviation, skewness, kurtosis, and other statistical measures.
- **Histogram Analysis:** Plots acceleration distribution with KDE overlay and statistical annotations.
- **Boxplot & Grouped Histograms:** Visualizes acceleration across different cylinder configurations.  

Technologies: `Python`, `pandas`, `matplotlib`, `seaborn`, `scipy`

**Key Insight**: Statistical and visual exploration of vehicle acceleration patterns, highlighting distribution characteristics and differences by engine type.

### [Back](./)
