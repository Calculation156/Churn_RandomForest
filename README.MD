# Training random forest model to predict clients who would churn

## Business context summary

### Situation
PowerCo is a power supply company who serves thousand of SMEs. Currently, it is facing the fiercer competition and clients are more likely to switch the alternative choices than ever.
The initial data exploratory reveals that the churn rate is indeed high, which is around 9.7%.

### Problem
PowerCo needs to take initatives to improve its offering to compete, which would include discount program. However, the discount program implementation would be costly and inefficient if it targets all clients. PowerCo needs a way to recognize the high value clients who are likely to churn, and give only those clients special treatment.

### Solution
We develop a churn predicting model using the Random Forest algorithm to predict who are likely to churn within 3 months

## Methodology
### Data
The given data include 2 CSV files:
  - Client_data.csv  contains the attributes of clients
  - Price_data.csv contains the price data for each clients
### The process
First, first the data is clean by changing the modrf
