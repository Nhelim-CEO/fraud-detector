Fraud Detection System
    
    Overview
This project is a machine learning system designed to detect fraudulent financial transactions using behavioral patterns in transaction data. It is built as a cybersecurity-focused anomaly detection system for financial fraud identification.

    Problem Statement
Financial fraud is rare but highly impactful. The dataset is highly imbalanced, making it difficult to detect fraudulent transactions accurately. The goal is to identify fraud based on transaction behavior rather than just raw values.

    Approach
The problem is treated as a behavioral anomaly detection task rather than a standard classification problem.

    The system analyzes:
Transaction patterns
Account balance changes
Unusual transaction types
Abnormal financial behavior

    Key Findings
Fraudulent transactions were found to occur only in:
TRANSFER
CASH_OUT

Fraud behavior is typically associated with:
Complete account balance depletion
Abnormal transfer patterns
Inconsistent balance updates
Feature Engineering

The following features were created to capture fraudulent behavior:
error_balance_orig: difference in sender balance before and after transaction
error_balance_dest: difference in receiver balance before and after transaction
is_full_drain: indicates full account depletion
is_new_destination: identifies previously unseen destination accounts
is_transfer: flag for transfer transactions
is_cashout: flag for cash-out transactions
high_value_txn: identifies unusually large transactions

    Model
Random Forest Classifier was used for training.
Reason:
Handles non-linear relationships
Works well with mixed feature types
Performs reliably on imbalanced datasets when class weighting is applied

Class imbalance was handled using class weighting.

    Evaluation
Model performance is evaluated using:
Precision
Recall (primary metric for fraud detection)
F1-score
Confusion matrix

Recall is prioritized because missing fraudulent transactions is a critical failure.

    Tech Stack
Python
Pandas
NumPy
Scikit-learn
