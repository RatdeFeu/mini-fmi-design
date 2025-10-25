```mermaid
    A1 -->|Trade Instruction| B1
    A2 -->|Trade Instruction| B1
    B1 --> B2
    B2 -->|Eligible for settlement| B3

    %% Internal Flow
    B3 -->|Internal DvP: Debit/Credit| B4

    %% Bridge Flow
    B3 -->|Bridge Instruction| C2
    C2 -->|Confirmation / Matched| B4

    %% External Flow
    B3 -->|External Instruction| C1
    C1 -->|Local Market Confirmation| B5
    B5 -->|Transit → Final| B4

    B4 -->|Final Updates| A1
    B4 -->|Final Updates| A2
```