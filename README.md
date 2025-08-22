This repository contains a project analyzing credit card user behavior based on transaction datasets, user data, and card data. The process includes preprocessing, data integration, analysis, and visualization using BigQuery & Looker Studio.

**Dataset**
The dataset used is divided into three main sources:
1. `transactions_data`
Contains transaction details (ID, date, amount, chip usage, merchant, MCC, etc.).
2. `users_data`
Contains user profiles (gender, age, income, credit score, total debt, etc.).
3. `cards_data`
Contains card information (brand, type, credit limit, expiry date, etc.).

**Data Pipeline**
1. Data Ingestion
   - Import raw datasets (transactions_data, users_data, cards_data) into BigQuery.
   - The datasets still contain various inconsistent formats, such as dates still in string format.
2. Data Preprocessing/Cleaning
   - Do the data type standardization: credit_limit, yearly_income, total_debt → integer/numeric; expiration_date → DATE; has_chip → boolean.
   - Do the format normalization (remove $ symbols, commas, non-numeric characters).
3. Query Aggregation
   - Create new tables `prep_cards` and `prep_transactions` from the preprocessing results.
   - Join the three datasets (`transactions_data`, `users_data`, `cards_data`) into a single analysis table `transactions_analysis`.

This is the link of Dashboard : https://lookerstudio.google.com/reporting/d1bae04e-a3b7-4f1b-8083-ef824ee9913e
