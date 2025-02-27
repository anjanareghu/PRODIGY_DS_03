# Bank Marketing Campaign Analysis

This project analyzes the effectiveness of a bank's marketing campaign. The dataset used in this project contains information about customers and whether they subscribed to a term deposit. The goal is to predict whether a customer will subscribe to the term deposit using various machine learning techniques.

## Table of Contents

1. [Dataset](#dataset)
2. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
3. [Data Preprocessing](#data-preprocessing)
4. [Model Building](#model-building)
5. [Evaluation](#evaluation)
6. [Improving the Model](#improving-the-model)
7. [Conclusion](#conclusion)

## Dataset

The dataset used is a CSV file named `train.csv`, which contains customer information, including age, job, marital status, education, and the target variable `deposit`. The `deposit` variable indicates whether the customer subscribed to the term deposit (yes or no).

- **Importing Libraries**: The necessary libraries such as `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn` are imported at the beginning.
  
- **Loading the Dataset**: The dataset is loaded using `pd.read_csv()` and displayed using `display()` to understand its structure.

## Exploratory Data Analysis (EDA)

### 1. Understanding the Data Structure
- **Renaming Columns**: The target column `y` is renamed to `deposit` for clarity.
- **Displaying Dataset Information**: Column names, non-null counts, and data types are displayed to understand the dataset's structure and identify any potential issues.

### 2. Handling Missing Values
- **Null Value Counts**: A count of missing values in each column is displayed to check for any missing data.

### 3. Visualizing Data
- **Distribution of the Target Variable**: A count plot is created to visualize the distribution of the target variable `deposit`.
- **Age Distribution**: A histogram with a KDE plot is used to visualize the distribution of customer ages.
- **Education Levels**: A count plot is used to visualize the distribution of customer education levels.
- **Contact Methods**: A pie chart is used to display the distribution of contact methods.
- **Marital Status vs. Deposit**: A count plot with hue is used to visualize the impact of marital status on deposit subscriptions.
- **Job Distribution**: A count plot with hue is used to visualize the distribution of jobs and their impact on deposit subscriptions.

### 4. Feature Exploration
- **Categorical Features**: The impact of various categorical features (e.g., `marital`, `education`, `default`, `housing`, `loan`, `contact`, `month`, `poutcome`) on deposit subscriptions is explored using count plots.

### 5. Correlation Analysis
- **Correlation Matrix**: A heatmap of the correlation matrix is created to understand the relationships between numerical features.

### 6. Box Plots for Numerical Features
- **Box Plots**: Box plots are used to visualize the distribution of numerical features (`age`, `balance`, `day`, `duration`, `campaign`, `pdays`, `previous`) by deposit.

## Data Preprocessing

### 1. Handling Missing Values
- **Replacing Missing Values**: Missing values in columns like `job`, `education`, and `contact` are replaced with the mode of the respective column.

### 2. Encoding Categorical Variables
- **Binary Encoding**: Binary categorical features such as `default`, `housing`, and `loan` are encoded into numerical values (1 for yes, 0 for no).
- **Target Variable Encoding**: The target variable `deposit` is encoded into numerical values (1 for yes, 0 for no).
- **Previous Campaign Outcome**: The `previous` column is modified to have binary values (1 for contacted, 0 for not contacted).
- **Dropping Unnecessary Columns**: The `pdays` column is dropped as it may not be relevant for the analysis.
- **Ordinal Encoding**: The `education` and `month` columns are encoded ordinally based on the level of education and the order of months, respectively.
- **One-Hot Encoding**: Categorical features such as `job`, `marital`, `poutcome`, and `contact` are one-hot encoded, with the first category being dropped to avoid multicollinearity.

### 3. Feature Scaling
- **MinMax Scaling**: The features are scaled using `MinMaxScaler()` to bring them into a uniform range.

## Model Building

### 1. Splitting the Data
- **Training and Test Split**: The data is split into training and test sets using `train_test_split()` with a test size of 20%.

### 2. Balancing the Data
- **SMOTE**: The training data is balanced using Synthetic Minority Over-sampling Technique (SMOTE) to handle class imbalance.

### 3. Decision Tree Model
- **Model Training**: A `DecisionTreeClassifier` is trained on the balanced training data.
- **Prediction**: The model makes predictions on the test data.

## Evaluation

### 1. Accuracy
- **Accuracy Score**: The accuracy of the model is calculated using `accuracy_score()` and displayed.

### 2. Classification Report
- **Classification Report**: A detailed classification report is generated using `classification_report()` and displayed in an HTML table.

### 3. Confusion Matrix
- **Confusion Matrix**: A confusion matrix is generated and visualized using a heatmap to understand the model's performance.

### 4. Decision Tree Visualization
- **Plotting the Tree**: The decision tree is plotted using `plot_tree()` to visualize the structure of the model.

### 5. Cross-Validation
- **Cross-Validation Scores**: The model's performance is validated using 5-fold cross-validation, and the scores are displayed.

### 6. ROC-AUC Score
- **ROC-AUC Score**: The ROC-AUC score is calculated to evaluate the model's performance in distinguishing between classes.

### 7. Precision-Recall Curve
- **Precision-Recall Curve**: A precision-recall curve is plotted to understand the trade-off between precision and recall.

## Improving the Model

### 1. Optimizing Hyperparameters
- **Entropy Criterion**: A second decision tree model is built using the entropy criterion, with max depth and minimum samples split specified.
- **Model Training and Visualization**: The model is trained and visualized similarly to the first model.

## Conclusion

This project demonstrates how to analyze a bank marketing dataset using machine learning. Through exploratory data analysis, data preprocessing, model building, and evaluation, we were able to build a predictive model for customer subscriptions to term deposits. Further improvements can be made by fine-tuning the model's hyperparameters or trying different algorithms.
