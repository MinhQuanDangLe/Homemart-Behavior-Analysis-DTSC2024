# Homemart Behavior Analysis - DSTC 2024

This project analyzes customer behavior in retail environments using various machine learning and data analysis techniques. The goal is to understand item interactions such as picking up, looking at, and purchasing items, and to provide actionable insights for shelf layout optimization.


### 1. **Data Preprocessing**
- **Trim all columns**: Removed leading and trailing whitespaces from column headers and all string-type values.
- **Handling missing values with Machine Learning**: Missing values in key columns, including "Putting item into bag", "Taking item out of bag", and "Putting item into bag in the 2nd time", were handled using machine learning models.

### 2. **Handling Missing Values with Machine Learning**
To handle missing values, we applied machine learning models to predict and impute missing data points. Two models were tested and compared:
 
- **Random Forest Classifier**: A robust ensemble method using multiple decision trees to predict the missing values. It performed well by capturing complex relationships between features.
  
- **Decision Tree Classifier**: A simpler model that creates a single tree based on feature splits. While faster and easier to interpret, it showed less accuracy compared to the Random Forest.

**Comparison of Results:**
- **Random Forest** outperformed Decision Tree in terms of prediction accuracy for missing values in the key columns, with better generalization due to the ensemble nature of the algorithm.
- **Decision Tree** was faster to train but tended to overfit on certain features, leading to less reliable predictions in some cases.

Based on this comparison, **Random Forest** was used for final missing data imputation.

### 3. **Exploratory Data Analysis (EDA)**
- **Interaction Counts**: Calculated total interactions for each combination of Shelf ID and Item ID.
- **Pick Up Rate**: Determined the rate of customers picking up items by comparing the number of times items were picked up with the total number of interactions.

### 4. **Looking and Holding Time**
- **Summarizing Time**: Calculated the total and average time customers spent looking at and holding items.
- **Quartile Classification**: Items were classified into quartiles (Q1, Q2, Q3, Q4) based on looking and holding time to determine which items received more or less customer attention.

### 5. **Purchase Ratio Calculation**
- **Purchase Ratio**: Computed the ratio of items purchased by comparing purchase counts to total interactions.

### 6. **Shelf Analysis**
- **Shelf-Specific Insights**: Special attention was given to items on shelf 6, identifying items that had higher customer interest (Q4 for both looking and holding times) and those that were less interacted with (Q1). Suggestions were made to adjust item placement for optimal visibility.
