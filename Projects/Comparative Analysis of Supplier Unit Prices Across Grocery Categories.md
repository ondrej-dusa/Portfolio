# **Comparative Analysis of Supplier Unit Prices Across Grocery Categories**

### **Project Overview**

The Analysis question I will be exploring for this project is to compare prices of different suppliers to see if there is a significant difference between supplier unit prices in the different grocery categories. This analysis will be important not only for the stores business decision makers, supply chain management and operations team to see if some suppliers are over charging them compared to others, but also for the customers to know why some products might be more expensive than others while the quality is assumed constant.

![Interaction Plot](https://raw.githubusercontent.com/ondrej-dusa/Portfolio/main/assets/Grocery_Interaction.png)

# Data Overview

**Source**: Grocery Inventory Dataset from Kaggle

**Link:** https://www.kaggle.com/datasets/willianoliveiragibin/grocery-inventory 

### Variables Analyzed:

- Unit_Price: Numeric unit price of each grocery item (cleaned and converted from string to numeric)
- Category: Product category (factorized)
- Supplier_Name: Supplier identifier (factorized)

### Preprocessing Steps:

- Removed missing values
- Standardized column names and data types

### Statistical Methods

**ANOVA (Analysis of Variance):**
- Used to test for significant differences in unit prices between suppliers and across categories, as well as their interaction.

### Assumptions Checked:

- Normality: Residuals tested with Shapiro-Wilk and QQ plots
- Homogeneity of Variance: Levene’s Test

## **Key Analysis Steps**

- **Data Cleaning & Processing:** Handle missing values, rename columns, and correct inconsistencies in data like removing $ from unit prices.
- **Interaction Plot:** Build and analyze the interaction of Unit Price and Product Category by Supplier names to look for spikes and inconsistencies.
- **ANOVA:** Run an ANOVA model to compare mean Unit Price for each category across the suppliers.
- **Assumptions:** Check the ANOVA asusmptions of linearity, homogeneity of variances and a post-hoc test.
- **Interpretation & Vizualization:** Interpret and vizualize the findings of my analysis.

## ANOVA Results

![Anova Results](https://raw.githubusercontent.com/ondrej-dusa/Portfolio/main/assets/Grocery_Anova.png)

## Interpretation:

- **Category:** Significant effect on unit price (p < 0.001)
- **Supplier_Name:** No significant effect (p ≈ 0.99)
- **Interaction (Supplier x Category):** Not significant (p = 1.00)

### Assumption Checks

- Normality: Residuals approximately normal (Shapiro-Wilk p = 0.967), supported by QQ plot
- Homogeneity: Levene’s Test p = 0.839, indicating equal variances across groups

![QQ plot Residuals](https://raw.githubusercontent.com/ondrej-dusa/Portfolio/main/assets/Grocery_Residuals.png)

## Key Findings

**Product Category is the Main Driver:**
- There are significant differences in unit prices between product categories, but not between suppliers within a category.

**Supplier Effect is Minimal:**
- No evidence that any supplier consistently charges more or less than others for the same category.

**No Significant Interaction:**
- The relationship between supplier and category does not significantly affect unit price.

## Implications

**For Businesses:**
- Focus negotiation and procurement strategies on high-cost categories rather than on switching suppliers within a category.

**For Customers:**
- Price differences between products are primarily due to category, not supplier markup.

**For Supply Chain:**
- Supplier selection may prioritize factors other than price (e.g., reliability, delivery time) within each category.

### Technologies Used

- `R Studio`: A statistical software used for this analysis
- `ggplot2`: Library for highly presentable vizualizations
- `pastect`: For descriptive statistics and other analytical tools

## Sample R Code Used

### Data cleaning
```r
grocery$Unit_Price <- as.numeric(gsub("[$]", "", grocery$Unit_Price))
grocery <- na.omit(grocery)
grocery$Category <- as.factor(grocery$Category)
grocery$Supplier_Name <- as.factor(grocery$Supplier_Name)
```

### ANOVA
```r
anovamodel <- aov(Unit_Price ~ Supplier_Name * Category, data=grocery)
anova(anovamodel)
```

### Assumption checks
```r
grocery$resid <- anovamodel$residuals
shapiro.test(grocery$resid)
leveneTest(grocery$Unit_Price ~ grocery$Supplier_Name * grocery$Category)
```
## Conclusion

This analysis demonstrates that while grocery product categories have a significant impact on unit price, supplier choice within a category does not. Therefore, pricing strategies and cost-saving efforts should be directed toward managing category costs rather than focusing on supplier differences within categories.



### [Back](https://ondrej-dusa.github.io/Portfolio/Projects.html)
