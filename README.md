# Aave Wallet Credit Scorer

This project analyzes historical DeFi transaction behavior from Aave V2 to assign a credit score (0–1000) to each wallet.

## How It Works

- Parses JSON file of user transactions
- Aggregates behavior (deposit, borrow, repay, liquidation, activity)
- Scores wallets using a rule-based weighted system
- Outputs scores to `wallet_scores.csv`

## Setup

```bash
pip install pandas
python main.py
```

## Input

- `user-wallet-transactions.json`: Raw transaction list (included in this repo)

## Output

- `wallet_scores.csv`: Wallets with assigned credit scores

## Scoring Formula

Score = weighted sum of:
- Total USD deposited
- Total USD repaid
- Days active
- Number of repayments
- Penalty for liquidation amount
