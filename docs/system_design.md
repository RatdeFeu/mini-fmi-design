# Mini FMI Trade Engine — System Design

## 1. Overview
The **Mini FMI Trade Engine** is an educational simulation platform that models the post-trade lifecycle in capital markets — from trade capture to settlement. It demonstrates how key components of financial market infrastructures (FMIs) such as Euroclear or Euronext interact through APIs, databases, and event-driven workflows.

### Objectives
- Capture and validate trades between counterparties.
- Match trades bilaterally.
- Clear matched trades through netting and exposure computation.
- Settle cleared trades via delivery-versus-payment (DvP) simulation.
- Provide observability through APIs and monitoring dashboards.

### Tech Stack
- **Backend:** FastAPI (Python)
- **Database:** PostgreSQL
- **Infrastructure:** Docker & Docker Compose
- **Schema Migration:** Alembic
- **Testing:** Pytest
- **Future Extensions:** Kafka / RabbitMQ for async messaging

---

## 2. Repository Description
**Name:** `mini-fmi-trade`

**Short Description:**  
> Educational prototype of a financial market infrastructure (FMI) system simulating trade capture, matching, clearing, and settlement workflows.

**Long Description:**  
> The Mini FMI Trade Engine is a modular, containerized simulation environment built with FastAPI and PostgreSQL. It replicates the post-trade processes found in market infrastructures — focusing on trade capture, matching, clearing, and settlement. The project is designed for learners and engineers seeking to understand FMI workflows through real code, APIs, and data flows.

**Features:**
- REST API for trade capture and monitoring
- Bilateral matching logic for counterparties
- Simplified clearing module with netting
- DvP (Delivery-versus-Payment) settlement simulation
- Dockerized for reproducibility and modularity
- Extendable to event-driven workflows and dashboards

---

## 3. System Architecture

### Core Components
| Component | Function |
|------------|-----------|
| **Trade Capture Service** | Receives trade submissions, validates input, and stores in DB |
| **Matching Engine** | Matches buy/sell trades based on counterparties and security ID |
| **Clearing Engine** | Nets matched trades, computes exposures, and prepares instructions |
| **Settlement Engine** | Executes delivery-versus-payment logic and updates ledgers |
| **Ledger Service** | Maintains account balances and securities positions |
| **Monitoring Layer** | Provides API and dashboard visibility into trade states |

### Data Flow (Simplified)
```
Trader API → Trade Capture → Matching Engine → Clearing → Settlement → Ledger → Reports
```

### Deployment Diagram (conceptual)
```
+------------------+        +------------------+
| FastAPI Service  | <----> | PostgreSQL DB    |
| (Trade Engine)   |        | (Persistent Store)|
+------------------+        +------------------+
        |                           
        | REST API / Events         
        v                           
   [CLI or Dashboard]               
```

---

## 4. Achievable Project Goals

### Primary Objectives
| Phase | Goal | Deliverable |
|--------|------|--------------|
| **1. Trade Capture & Matching** | Implement API for trade submission and bilateral matching | `Trade Capture Service`, `Matching Engine` |
| **2. Clearing Module** | Add netting and margin calculation | `Clearing Engine`, `Exposure Report` |
| **3. Settlement Engine** | Implement DvP logic with linked cash/securities accounts | `Settlement Service`, `Ledger` |
| **4. Monitoring & Reporting** | Build APIs and basic dashboards | `Reporting API`, `Audit Log` |
| **5. Infrastructure Hardening** | Dockerize and orchestrate services | `docker-compose.yml`, integration tests |

### Secondary (Stretch) Goals
- Introduce async message bus (Kafka/RabbitMQ) for inter-service events.
- Support multiple asset classes (Equities, Bonds, FX).
- Add a simple React dashboard for trade status visualization.
- Implement basic anomaly detection for unmatched or failed trades.

---

## 5. Data Models (Canonical Entities)

### Trade
| Field | Type | Description |
|--------|------|--------------|
| id | UUID | Internal identifier |
| trade_id | String | External trade reference |
| buyer | String | Buyer participant ID |
| seller | String | Seller participant ID |
| security | String | ISIN or security symbol |
| price | Float | Trade price |
| quantity | Integer | Number of units traded |
| status | Enum(NEW, MATCHED, CLEARED, SETTLED) | Trade lifecycle status |

### Participant, Security, Accounts
Additional models define counterparties, securities, and both cash and securities accounts for settlement simulation.

---

## 6. API Overview (OpenAPI v1)
**Endpoints**
- `POST /api/v1/trades` — Submit a new trade
- `GET /api/v1/trades` — List all trades
- `GET /api/v1/participants/{id}` — Fetch participant details
- `GET /api/v1/positions/{participant_id}` — Retrieve participant positions

---

## 7. Learning Outcomes
- Understand the **post-trade lifecycle** and FMI architecture.
- Design **robust backend APIs and data models** for financial systems.
- Learn **microservice orchestration** and containerized deployment.
- Gain exposure to **event-driven architectures** used in FMIs.
- Produce a **portfolio-ready capstone** in financial systems engineering.

---

## 8. Success Criteria
✅ Trade submissions persist and validate correctly  
✅ Matching logic pairs counterparties correctly  
✅ Clearing nets exposures accurately  
✅ Settlement updates ledger balances atomically  
✅ All services run and integrate via Docker Compose  
✅ Documentation and diagrams explain system lifecycle clearly  

---

## 9. Roadmap
| Month | Focus | Milestones |
|--------|--------|-------------|
| **1** | Foundations & Design | Data models, OpenAPI spec, base schema, diagrams |
| **2** | Core Engine | Build capture, matching, and DB integration |
| **3** | Clearing & Settlement | Add netting, margining, DvP simulation |
| **4** | Reporting & Extensions | Dashboard, async messaging, deployment polish |

---

## 10. License & Contribution
Licensed under the MIT License. Contributions, pull requests, and documentation improvements are welcome. The repository is intended for **educational and research purposes only**.

