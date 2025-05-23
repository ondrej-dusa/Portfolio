---
layout: default
---
# Projects

My expertise in data showcases my ability to extract valuable insights from complex datasets and drive data-informed decision-making. Throughout my career, I've worked on a diverse range of projects utilizing cutting-edge technologies and methodologies. From developing predictive machine learning models in Python and R to crafting intricate SQL queries for data manipulation, my work demonstrates a comprehensive approach to data analysis. I've also created dynamic visualizations and interactive dashboards using industry-standard BI tools such as Power BI and Tableau, translating raw data into actionable business intelligence. Below, you'll find a selection of my most impactful projects, highlighting my proficiency in statistical analysis, predictive modeling, and data visualization across various industries and applications.

## [Multilingual Customer Support Ticket Classification Using SVM](./Projects/Multilingual Customer Support Ticket Classification Using SVM.html)

This project classifies multilingual customer support tickets using Support Vector Machines (SVM) to predict ticket types.

### Key Steps:

- **Data Collection:** Downloaded a multilingual customer support ticket dataset from Kaggle.
- **Data Cleaning & Transformation:** Preprocessed text data using TF-IDF, one-hot encoded categorical features, and balanced classes with SMOTE.
- **Model Training:** Trained SVM models for English and German ticket classification.
- **Model Evaluation:** Assessed model performance using accuracy, precision, recall, and F1-score.
- **Analysis:** Compared performance across languages and identified areas for improvement.

**Technologies:** `Python`, `scikit-learn`, `pandas`, `imblearn`, `matplotlib`, `seaborn`

**Key Insight:** SVMs can effectively classify customer support tickets, with performance varying by language due to data characteristics and linguistic complexities. Further improvements are needed to enhance cross-linguistic generalizability.

## [E-commerce Sales Analysis](./Projects/E-commerce Sales Analysis.html)

This project classifies emails using a Multinomial Naive Bayes model to predict labels (e.g., spam or not spam).

### Key Steps:

- **Data Collection**: Imported sales data and prepared it for analysis in Power BI.
- **Data Cleaning & Transformation**: Processed missing values, standardized formats, and created calculated fields.
- **Visualization & Analysis**: Built interactive dashboards to analyze sales trends, customer behavior, and product performance.
- **Insights Extraction**: Identified seasonal sales patterns, market expansion opportunities, and pricing strategies.
- **Recommendations**: Proposed data-driven strategies for inventory optimization, targeted marketing, and revenue growth.

**Technologies**: `Power BI`, `SQL`, `Excel`

**Key Insight**: Utilizes a probabilistic model to classify emails, with room for improvement in handling class imbalance and model accuracy.

## [Banknote Authentication Using PCA and KNN](./Projects/PCA-Optimized KNN Classification for Banknote Authentication.html)

This project uses K-Nearest Neighbors (KNN) with PCA for banknote authentication, optimizing accuracy and fraud detection.

### Key Steps:

 - **Dimensionality Reduction**: Applied PCA to extract key features related to banknote dimensions.
 - **Model Selection**: Identified the best k=6 for KNN based on recall optimization.
 - **Training & Testing**: Classified banknotes into genuine or counterfeit using KNN.
 - **Evaluation**: Achieved 99% accuracy, with perfect recall for counterfeit detection.

**Technologies**: `Python`, `Scikit-learn`, `PCA`, `KNN`, `Pandas`, `Numpy`, `Google Colab`

**Key Insight**: The model effectively detects counterfeit banknotes with near-perfect recall, minimizing false negatives in fraud detection.

## [Email Classification Using Multinomial Naive Bayes](./Projects/Email Classification Using Multinomial Naive Bayes.html)

### Key Steps:

- **Data Collection**: Loads email dataset and prepares text data.
- **Preprocessing**: Cleans text by removing stopwords and applying stemming.
- **Feature Extraction**: Converts text into numerical features using CountVectorizer.
- **Model Training**: Trains the Multinomial Naive Bayes model on the data.
- **Evaluation**: Assesses model performance using a classification report.

**Technologies**: `Python`, `Pandas`, `NLTK`, `Scikit-learn`, `Google Colab`

**Key Insight**: Utilizes a probabilistic model to classify emails, with room for improvement in handling class imbalance and model accuracy.

## [Value at Risk (VaR) Analysis of AAPL Stock](./Projects/Risk Analysis and Value at Risk (VaR).html)

This project analyzes the Value at Risk (VaR) of Apple Inc. (AAPL) stock using historical, parametric, and Monte Carlo methods. 

### Key Steps:
- **Data Collection:** Fetches AAPL stock prices from Yahoo Finance and calculates log returns.
- **VaR Calculation:** Computes historical and parametric VaR at a 95% confidence level.
- **Monte Carlo Simulation:** Generates 10,000 return simulations to estimate risk.
- **Backtesting:** Counts exceptions to evaluate VaR model accuracy.
- **Visualization:** Plots return distribution with VaR thresholds.

**Technologies**: `R`, `quantmod`, `PerformanceAnalytics`, `ggplot2`, `dplyr`,

**Key Insight**: A comparative analysis of different risk estimation techniques to assess potential losses.

## [Descriptive Statistics and Data Visualization of MPG Dataset](./Projects/Exploratory Data Analysis (EDA) of MPG Dataset.html)

This project explores the MPG dataset through descriptive statistics and visualization techniques to analyze acceleration and other key attributes.

### Key Steps:

- **Data Collection:** Loads and cleans the MPG dataset to ensure accurate analysis.
- **Descriptive Statistics:** Computes mean, standard deviation, skewness, kurtosis, and other statistical measures.
- **Histogram Analysis:** Plots acceleration distribution with KDE overlay and statistical annotations.
- **Boxplot & Grouped Histograms:** Visualizes acceleration across different cylinder configurations.  

**Technologies**: `Python`, `pandas`, `matplotlib`, `seaborn`, `scipy`

**Key Insight**: Statistical and visual exploration of vehicle acceleration patterns, highlighting distribution characteristics and differences by engine type.

### [Back](./)
