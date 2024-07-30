

# IEC-BIOPHARM Machine Anomaly Prediction

## CHALLENGE-BIOPHARM: Predicting Anomalies in Machine Logs

## Overview

### Start
- May 9, 2024

### Close
- May 11, 2024


## Description

This challenge focuses on the analysis of Audit trails, a major compliance requirement of the FDA, through the use of advanced Machine Learning techniques. Participants are invited to explore a dataset containing machine logs. Each entry in the dataset corresponds to an event, with information such as the type of event that occurred, the time of the incident, the location, and other relevant characteristics.

### Objective

The objective of this challenge is to develop Machine Learning models capable of accurately predicting the type of event that occurred from the machine logs. Participants will need to explore and preprocess the data, identify the most significant features, and train robust classification models. These models should be able to generalize to new log entries to aid in the early detection of errors and proactive decision-making in a production environment.

This challenge offers a unique opportunity to apply advanced semi-supervised Machine Learning techniques to a concrete regulatory compliance problem.

### Evaluation

Submissions are evaluated using the multi-class logarithmic loss (log loss). Each index is labeled with a unique error type. For each row, you must submit a set of predicted probabilities (one for each error type). The formula is:

\[ \text{logloss} = -\frac{1}{N} \sum_{i=1}^{N} \sum_{j=1}^{M} y_{ij} \log(p_{ij}) \]

## Submission File

The first line of the file contains the column names - "LOG i" and the different events. Each subsequent line corresponds to predictions (probabilities from 0 to 1), ensuring that the sum of probabilities for a log equals 1 (one true label).

You can refer to the `SampleSubmission.csv` file in the data section.

```
index  Emergency_Stop  Warning  Critical_Warning  Error
log1   0.0001          0.0001   0.999             0.0001
log2   0.0001          0.0001   0.0001            0.0001
log3   0.0001          0.0001   0.0001            0.0001
```

## Citation

ADC IEC (2024). Machine Anomaly Prediction. Kaggle.  
[https://www.kaggle.com/competitions/iec-biopharm-prediction-des-anomalies-machines](https://www.kaggle.com/competitions/iec-biopharm-prediction-des-anomalies-machines)

## Dataset Description

The dataset consists of approximately 54,000 rows, with a partially unlabeled portion (21,746 rows = 40%), making this a semi-supervised ML challenge!

### Files

- `train.csv` - the training set
- `test.csv` - the test set
- `sample_submission.csv` - a sample submission file in the correct format

### Data fields

- `index` : Log identifier
- `Date` : The date and time the event was recorded.
- `Location` : The location where the event occurred on the machine.
- `Value` : The value associated with the event, which can be a measure, a state, etc.
- `New Value` : The new value recorded after the event (if applicable).
- `Old Value` : The old value recorded before the event (if applicable).
- `Event Type (target)` : The type of error or event recorded, such as:
  1. Emergency_Stop
  2. Warning
  3. Critical_Warning
  4. Reserve_Warning
  5. Error
  6. Rapid_Stop_Error
  7. Info
  8. Protection_Information
  9. Connection_Interruption
  10. Value
  11. Start
  12. Login
  13. Process_Limit
  14. Logout

