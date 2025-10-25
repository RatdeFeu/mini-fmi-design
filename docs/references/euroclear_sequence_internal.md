```mermaid
   sequenceDiagram
    participant Buyer
    participant Seller
    participant Euroclear as Euroclear System
    participant Ledger

    Seller->>Euroclear: Deliver instruction (SELL)
    Buyer->>Euroclear: Receive instruction (BUY)
    Euroclear->>Euroclear: Validate instructions (ISIN, quantity, eligibility)
    Euroclear->>Ledger: Check cash & securities positions
    Ledger-->>Euroclear: OK (positions sufficient)

    Euroclear->>Ledger: 
        atomic DvP {
            Debit Seller securities
            Credit Buyer securities
            Debit Buyer cash
            Credit Seller cash
        }
    Ledger-->>Euroclear: Transaction committed
    Euroclear->>Buyer: Confirmation (SETTLED)
    Euroclear->>Seller: Confirmation (SETTLED)
```