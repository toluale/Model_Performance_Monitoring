# Model_Performance_Monitoring
This project involves monitoring a financial fraud detection model using machine learning techniques.

## reference.csv and analysis.csv

| Column     | Description              |
|------------|--------------------------|
| `'timestamp'` | Date of the transaction. |
| `'time_since_login_min'` | Time since the user logged in to the app. |
| `'transaction_amount'` | The amount of Pounds(£) that users sent to another account. |
| `'transaction_type'` | Transaction type: <ul><li>`CASH-OUT` - Withdrawing money from an account.</li><li>`PAYMENT` - Transaction where a payment is made to a third party.</li><li>`CASH-IN` - This is the opposite of a cash-out. It involves depositing money into an account.</li><li>`TRANSFER` - Transaction which involves moving funds from one account to another.</li> |
| `'is_first_transaction'` | A binary indicator denoting if the transaction is the user's first (1 for the first transaction, 0 otherwise). |
| `'user_tenure_months'` | The duration in months since the user's account was created or since they became a member. |
| `'is_fraud'` | A binary label indicating whether the transaction is fraudulent (1 for fraud, 0 otherwise). |
| `'predicted_fraud_proba'` | The probability assigned by a detection model indicates the likelihood of a fraudulent transaction. |
| `'predicted_fraud'` |  The predicted classification label is calculated based on predicted fraud probability by the detection model (1 for predicted fraud, 0 otherwise). |

The primary objective is to identify the causes of the model's decreasing accuracy and understand how data drift might be contributing to this issue.

  1. Identify Performance Issues: Determine the months where the estimated and realized accuracy of the model dropped.

  2. Detect Feature Drift: Identify which features experienced the most drift between the reference (test data) and analysis (production data) sets.

  3. Analyze Performance Drop: Understand why the accuracy of the fraud detection model decreased and propose a hypothesis.

The primary tool used in this project is the nannyml library, which provides functionality for monitoring and analyzing machine learning model performance in a production environment. 

Techniques such as the Kolmogorov-Smirnov test for continuous features and the Chi-square test for categorical features were employed to detect feature drift.
