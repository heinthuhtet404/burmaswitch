Database Initial Design
Central Switch Database

transactions
id
transaction_id
sender_identifier
receiver_identifier
source_wallet
target_wallet
amount
status
created_at
updated_at

routing_rules
id
prefix
wallet_name
endpoint
active

idempotency_records
id
idempotency_key
transaction_id
response
expires_at

Wallet Database

accounts
id
account_identifier
phone_number
status
created_at

ledger_entries
id
account_id
transaction_id
entry_type

DEBIT/CREDIT

amount
created_at