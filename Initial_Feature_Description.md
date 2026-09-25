# UCI Bank Marketing Dataset — Feature Description

The `bank-full.csv` dataset contains information about customers, their financial situation, interactions during the current marketing campaign, previous campaign history, and whether they subscribed to a term deposit.

## Feature Descriptions

| Column | Type | Description |
|---|---|---|
| `age` | Numerical | Age of the customer. |
| `job` | Categorical | Type of job or occupation of the customer. |
| `marital` | Categorical | Marital status of the customer. |
| `education` | Categorical | Education level of the customer. |
| `default` | Categorical | Whether the customer has credit in default (`yes`/`no`). A default indicates that the customer has failed to meet a required credit repayment obligation; it does not necessarily mean the customer will fail to repay in the future. |
| `balance` | Numerical | Average yearly balance of the customer's account, measured in euros. The dataset documentation does not specify the exact calculation method used to obtain this average. |
| `housing` | Categorical | Whether the customer has a housing loan (`yes`/`no`). |
| `loan` | Categorical | Whether the customer has a personal loan (`yes`/`no`). |
| `contact` | Categorical | Communication method used to contact the customer. |
| `day` | Numerical | Day of the month when the customer was last contacted. |
| `month` | Categorical | Month when the customer was last contacted. |
| `duration` | Numerical | Duration of the customer's last contact, measured in seconds. |
| `campaign` | Numerical | Number of contacts made with the customer during the current marketing campaign, including the last contact. |
| `pdays` | Numerical | Number of days since the customer was last contacted as part of a previous campaign. A value of `-1` means the customer was not previously contacted. |
| `previous` | Numerical | Number of contacts made with the customer before the current campaign. |
| `poutcome` | Categorical | Outcome of the previous marketing campaign. |
| `y` | Categorical — Target | Whether the customer subscribed to a term deposit (`yes`/`no`). |

## Feature Groups

### 1. Customer Characteristics

These features describe the customer's personal characteristics:

- `age`
- `job`
- `marital`
- `education`

### 2. Financial Information

These features provide information about the customer's financial situation:

- `default`
- `balance`
- `housing`
- `loan`

### 3. Current Marketing Campaign

These features describe the bank's current interaction with the customer:

- `contact`
- `day`
- `month`
- `duration`
- `campaign`

### 4. Previous Marketing Campaign

These features describe the customer's previous interactions with the bank's marketing campaigns:

- `pdays`
- `previous`
- `poutcome`

### 5. Target Variable

- `y` — Indicates whether the customer subscribed to the term deposit.

## Important Notes

### `default`

`default = yes` means the customer has credit in default. In practical terms, this indicates a failure to meet a required credit repayment obligation. It should not be interpreted as a guarantee that the customer will not repay in the future.

### `balance`

`balance` represents the customer's average yearly account balance in euros. A negative value is possible because an account can have a negative balance, for example when an overdraft is allowed.

The dataset documentation does not explain the exact calculation used to obtain the yearly average. Therefore, we should not assume that it was calculated simply by averaging the closing balance of each of the 12 months.

### `pdays`

`pdays = -1` has a specific meaning: the customer was not previously contacted as part of a previous campaign. Therefore, `-1` should not automatically be treated as an ordinary numerical value during preprocessing.

## Target

The classification target is:

```text
y = yes  → Customer subscribed to a term deposit
y = no   → Customer did not subscribe to a term deposit
```
