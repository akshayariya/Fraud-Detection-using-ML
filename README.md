Below is a detailed README file for your fraud detection project, following the structure you provided. This README will include an overview, a description of the files, usage instructions, column descriptors, and additional notes.

# Fraud Detection System

## Overview
This repository contains a machine learning project that detects fraudulent transactions using a given dataset. The project includes the main script for data preprocessing and model training, the dataset used for analysis, and a data dictionary describing the dataset.

## Files
- **Fraud.csv** - The dataset containing transaction details.
- **File1.py** - The main script that includes data preprocessing, model training, and evaluation.
- **Data Dictionary.txt** - A text file describing each column in the dataset.

## Usage
1. **Download the repository:**
   ```sh
   git clone https://github.com/akshayariya/Fraud-Detection-using-ML.git
   ```
2. **Navigate to the project directory:**
   ```sh
   cd fraud-detection-system
   ```
3. **Ensure the dataset file (Fraud.csv) and the script (File1.py) are in the project directory.**
4. **Install the required Python packages:**
   ```sh
   pip install pandas numpy scikit-learn xgboost
   ```
5. **Run the script:**
   ```sh
   python File1.py
   ```
   The script will preprocess the data, train the model, and print evaluation metrics.

## Column Descriptors
- **step**: Maps a unit of time in the real world. In this case, 1 step is 1 hour of time. Total steps are 744 (30 days simulation).
- **type**: The type of transaction. Possible values are CASH-IN, CASH-OUT, DEBIT, PAYMENT, and TRANSFER.
- **amount**: The amount of the transaction in local currency.
- **nameOrig**: The customer who initiated the transaction.
- **oldbalanceOrg**: The initial balance before the transaction for the customer who initiated the transaction.
- **newbalanceOrig**: The new balance after the transaction for the customer who initiated the transaction.
- **nameDest**: The customer who is the recipient of the transaction.
- **oldbalanceDest**: The initial balance before the transaction for the recipient. Note that there is no information for customers whose names start with 'M' (Merchants).
- **newbalanceDest**: The new balance after the transaction for the recipient. Note that there is no information for customers whose names start with 'M' (Merchants).
- **isFraud**: Indicates whether the transaction is fraudulent (1) or not (0). Fraudulent transactions are made by agents attempting to profit by taking control of customers' accounts and emptying funds.
- **isFlaggedFraud**: Indicates whether the transaction was flagged as fraud (1) or not (0). Transactions are flagged if they attempt to transfer more than 200,000 in a single transaction.

## How the Script Works
1. **Load the dataset**: The script loads `Fraud.csv` into a pandas DataFrame.
2. **Data Cleaning**: Remove outliers using the Z-score method.
3. **Data Encoding**: Convert the 'type' column to numerical format using one-hot encoding.
4. **Data Splitting**: Split the data into training and testing sets.
5. **Model Training**: Train a Random Forest classifier with hyperparameter tuning using GridSearchCV.
6. **Model Evaluation**: Evaluate the model's performance using accuracy, precision, recall, and F1-score.
7. **Feature Importance**: Identify key features predicting fraudulent transactions.

## Notes
- Ensure you have Python installed along with the necessary libraries (`pandas`, `numpy`, `scikit-learn`, and `xgboost`).
- The script `File1.py` contains all the necessary steps for data preprocessing, model training, and evaluation.
- The dataset (`Fraud.csv`) should be placed in the same directory as the script for proper execution.
