# Project description

This project ingests the Kaggle "Book Recommendation Dataset" and transforms it from raw CSVs into a structured format.

# Architecture

The Medallion Architecture is used to ensure data reliability and quality.

- Bronze: Landing zone for Kaggle CSVs. Data is stored "as-is" with ingestion metadata.

- Silver: Joins, data type casting, and schema enforcement.

- Gold: Business-level aggregates (e.g., avg_rating_per_book) optimized for recommendation models.

# Setup and security

1. Open your terminal or command prompt and run:

`pip install databricks-cli`

2. Set up the CLI:

`databricks configure --token`

3. Create a secret scope called jdbc:

`databricks secrets create-scope --scope jdbc`

4. Add the secrets username and password. Run the following commands and enter the secret values in the opened editor:
```
databricks secrets put --scope jdbc --key username

databricks secrets put --scope jdbc --key password
```
5. Check the secrets list:

`databricks secrets list --scope jdbc`
