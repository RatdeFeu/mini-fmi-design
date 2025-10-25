```mermaid
  sequenceDiagram
    participant Participant
    participant Euroclear
    participant Transit as Transit Account
    participant Market as Local Market / Agent Bank
    participant Ledger

    Participant->>Euroclear: Settlement instruction (External)
    Euroclear->>Transit: Debit securities (Provisional)
    Euroclear->>Market: Send delivery/receipt order
    Market-->>Euroclear: Confirmation (executed locally)
    Euroclear->>Transit: Move from Transit to Ledger (Final)
    Euroclear->>Ledger: Credit/Debit cash & securities
    Euroclear-->>Participant: Settlement status updated (Final)
```
