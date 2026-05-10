# Data

This folder contains the prepared complaint dataset used in the project:

```text
consumer_complaints_small.csv
```

The file is a prepared subset of consumer complaint narratives derived from the Consumer Financial Protection Bureau complaint data.

## Task

The task is product classification. The input is a free-text complaint narrative, and the target is the financial product category.

The project uses five product categories:

- Bank account or service
- Credit card
- Credit reporting
- Debt collection
- Mortgage

## Experimental setup

For the main experiment, the notebook caps the dataset at 1200 examples per class to keep the setup balanced and computationally manageable.

The data is split into train, validation, and test sets using stratification. The final test set contains 900 examples, with 180 examples per class.

The validation set is used for checkpoint selection and model configuration during development. The test set is reserved for the final reported results.

## Loading behavior

The notebook first loads the local CSV file from this folder:

```text
data/consumer_complaints_small.csv
```

If the local file is unavailable, the notebook can fall back to the remote CSV URL specified in the configuration cell.

## Notes

The dataset is used as a controlled experimental subset rather than as a complete representation of the full CFPB complaint taxonomy. A deployed complaint-triage system would need to handle more product categories, class imbalance, and distribution shift over time.
