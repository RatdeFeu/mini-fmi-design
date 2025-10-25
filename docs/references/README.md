# Reference Diagrams

This folder contains sequence and flow diagrams illustrating the key settlement flows in a financial market infrastructure system.

## Settlement Flows Overview
[euroclear_settlement_flows.md](euroclear_settlement_flows.md) provides a high-level flowchart showing:
- Interaction between market participants (buyers and sellers)
- Core Euroclear system components
- External connections (Local Markets/CSDs and Bridge System)

## Detailed Settlement Sequences

### Internal Settlement
[euroclear_sequence_internal.md](euroclear_sequence_internal.md) illustrates the internal Delivery-versus-Payment (DvP) settlement:
- Trade instruction validation
- Position checking
- Atomic settlement with simultaneous cash and securities movements
- Final confirmation to participants

### External Settlement
[euroclear_sequence_external.md](euroclear_sequence_external.md) shows settlement with external market entities:
- Provisional debit in transit account
- Interaction with local market agents
- Final settlement confirmation
- Updates to internal ledgers

### Bridge Settlement
[euroclear_sequence_bridge.md](euroclear_sequence_bridge.md) demonstrates interoperability with other CSDs:
- Bridge instruction processing between Euroclear and Clearstream
- Risk validation on both sides
- Synchronized settlement across systems
- Final status updates to participants

### Simplified state transition

| State         | Meaning                                      | Trigger                                |
| ------------- | -------------------------------------------- | -------------------------------------- |
| `RECEIVED`    | Instruction validated and accepted           | API submission                         |
| `POSITIONED`  | Positions checked and blocked                | Pre-settlement                         |
| `EXECUTING`   | DvP process started                          | Settlement engine picks up instruction |
| `SETTLED`     | DvP success (internal or confirmed external) | Ledger update successful               |
| `PROVISIONAL` | Waiting for external confirmation            | Awaiting local market result           |
| `FAILED`      | Validation or execution failed               | Risk, limits, or cash shortfall        |
| `CANCELLED`   | Stale or unmatched                           | Bridge cleaning or expiration          |


### Euroclear key takeaways:
- Internal = book-entry only, atomic finality.
- Bridge = coordinated dual-ledger finality (Euroclear + Clearstream).
- External = provisional entries awaiting external confirmation.
- All flows rely on cash & securities ledgers and DvP atomicity.
-- notes:
--- Definition: “atomic” means that the securities and cash legs are processed as one indivisible event — there is no partial settlement where only one side completes
--- Purpose: To eliminate principal risk, i.e., the risk that one party delivers securities (or cash) but does not receive the corresponding payment (or securities).touch
- Each instruction follows the RECEIVED → POSITIONED → EXECUTING → SETTLED/PROVISIONAL state machine.
