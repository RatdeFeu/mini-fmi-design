```mermaid
---
config:
  layout: elk
---
flowchart LR
 subgraph Participants["Participants"]
        A1["Buyer Participant"]
        A2["Seller Participant"]
  end
 subgraph subGraph1["Euroclear System"]
        B1["Trade Capture & Instruction Validation"]
        B2["Position Check & Blocking"]
        B3["Settlement Engine"]
        B4["Ledger - Cash & Securities"]
        B5["Transit Account"]
  end
 subgraph subGraph2["External Entities"]
        C1["Local Market or CSD"]
        C2["Bridge System - Clearstream"]
  end
    A1 -- Trade Instruction --> B1
    A2 -- Trade Instruction --> B1
    B1 --> B2
    B2 -- Eligible for settlement --> B3
    B3 -- Internal DvP: Debit/Credit --> B4
    B3 -- Bridge Instruction --> C2
    C2 -- Confirmation / Matched --> B4
    B3 -- External Instruction --> C1
    C1 -- Local Market Confirmation --> B5
    B5 -- Transit → Final --> B4
    B4 -- Final Updates --> A1 & A2
```
