# 🏦 Financial Market Infrastructure (FMI) Ecosystem

> A comprehensive overview of how participants, infrastructures, and regulators interact within the global financial market ecosystem.

---

## 📊 Overview

The FMI ecosystem is composed of:
1. **Market Participants** — issuers, intermediaries, and investors  
2. **Core FMIs** — payment, settlement, and risk management systems  
3. **Supporting Infrastructure** — banks, service providers, and registrars  
4. **Regulatory Authorities** — central banks, supervisors, and market regulators  

All entities are interconnected to ensure the smooth, secure, and resilient functioning of financial markets.

---

## 🧩 1. MARKET PARTICIPANTS
<details>
<summary><b>Expand Market Participants</b></summary>

| **Entity** | **Examples** | **Role / Function** | **Notes** |
|-------------|--------------|----------------------|------------|
| **Issuers** | Corporates, Governments, SPVs | • Issue securities <br>• Provide corporate actions | Foundational source of financial instruments |
| **Direct Participants** | Banks, Broker-Dealers, Custodians, Clearing Members | • Maintain direct FMI access <br>• Meet participation rules <br>• Post margins <br>• Manage client risk | Must meet membership, credit, and operational standards |
| **Indirect Participants** | Hedge Funds, Asset Managers, Pension Funds, Insurance Companies, Corporates | • Access FMIs through direct participants <br>• Act as ultimate risk takers | Rely on intermediaries for clearing/settlement access |
| **Trading Venues** | Stock Exchanges, Derivatives Exchanges, OTC Platforms, MTFs/ATSs | • Execute trades <br>• Price discovery <br>• Feed trades to CCPs and TRs | Subject to market regulator oversight |

</details>

---

## 💰 2. CORE FMIs – PAYMENT SYSTEMS
<details>
<summary><b>Expand Payment Systems</b></summary>

| **Aspect** | **Details** |
|-------------|-------------|
| **Types** | RTGS (Real-Time Gross Settlement), DNS (Deferred Net Settlement), Hybrid (liquidity-saving), Retail (high-volume/low-value) |
| **Role** | • Transfer funds between institutions <br>• Settlement finality <br>• Support monetary policy <br>• Manage intraday liquidity |
| **Examples** | Fedwire (US), TARGET2 (EU), CHAPS (UK), BOJ-NET (Japan) |
| **Risks** | Credit exposure, liquidity timing mismatches, operational risk, settlement bank default |
| **Requirements** | Settlement finality, preference for central bank money, same-day completion, DNS must cover two largest exposures |

</details>

---

## 📈 3. CORE FMIs – SECURITIES INFRASTRUCTURE
<details>
<summary><b>Expand Securities Infrastructure</b></summary>

### 🗃️ Central Securities Depositories (CSDs)

| **Aspect** | **Details** |
|-------------|-------------|
| **Types** | Domestic (DTC, Euroclear BE) <br>International (Euroclear Bank, Clearstream) |
| **Role** | • Securities custody and safekeeping <br>• Immobilization/dematerialization <br>• Asset servicing (corporate actions) <br>• Daily reconciliation with issuers |
| **Holding Models** | Direct (owner known) <br>Indirect (multi-tier custody) |
| **Risks** | Custody loss/theft, operational failures, legal enforceability issues |
| **Requirements** | No overdrafts, daily reconciliation, segregation, immobilized/dematerialized form |

---

### 🔄 Securities Settlement Systems (SSSs)

| **Aspect** | **Details** |
|-------------|-------------|
| **Models** | Model 1: Gross/Gross (real-time) <br>Model 2: Gross/Net (securities real-time) <br>Model 3: Net/Net (batch) |
| **Role** | • Transfer securities by book entry <br>• Match and coordinate cash/securities <br>• Delivery vs Payment (DvP) <br>• Manage fails |
| **Risks** | Principal risk (no DvP), credit/ liquidity, operational mismatch |
| **Requirements** | DvP mandatory, value date finality, real-time preferred |

</details>

---

## 🛡️ 4. CORE FMIs – RISK MANAGEMENT
<details>
<summary><b>Expand Risk Management FMIs</b></summary>

### ⚖️ Central Counterparties (CCPs)

| **Aspect** | **Details** |
|-------------|-------------|
| **Products** | Exchange-traded & OTC derivatives, securities, commodities, repos |
| **Role** | • Buyer to seller / seller to buyer <br>• Multilateral netting <br>• Margin collection & risk mutualization <br>• Default management |
| **Legal Mechanisms** | Novation, Open Offer |
| **Risk Tools** | Initial Margin (99%+ conf.), Variation Margin, Default Fund, Stress Tests |
| **Default Waterfall** | 1. Defaulter IM <br>2. Defaulter DF <br>3. CCP “skin-in-game” <br>4. Non-defaulter DF <br>5. Assessment powers <br>6. Loss allocation (VM haircut, tear-up) |
| **Examples** | LCH, CME, Eurex, ICE Clear, JSCC, OCC, NSCC |
| **Requirements** | Cover 1–2 largest defaults, daily stress tests, 2-hour recovery, segregation & portability |

---

### 🧾 Trade Repositories (TRs)

| **Aspect** | **Details** |
|-------------|-------------|
| **Examples** | DTCC SDR, REGIS-TR |
| **Role** | • Centralized transaction database <br>• Regulatory reporting <br>• Lifecycle tracking <br>• Market transparency |
| **Data Elements** | LEIs, UPIs, Notional values, Collateral info, Lifecycle events |
| **Users** | Regulators, Central Banks, Public (aggregated), Participants |
| **Risks** | Operational, data integrity, security/confidentiality |
| **Requirements** | Accurate data, robust IT, business continuity, standardized formats |

</details>

---

## 🧱 5. SUPPORTING INFRASTRUCTURE
<details>
<summary><b>Expand Supporting Infrastructure</b></summary>

| **Entity** | **Examples / Types** | **Role / Function** | **Risks / Requirements** |
|-------------|----------------------|----------------------|---------------------------|
| **Settlement Banks** | Central Banks (preferred) <br>Commercial Banks | • Hold settlement accounts <br>• Execute fund transfers <br>• Provide intraday credit | **Risks:** Credit, concentration, operational <br>**Reqs:** Monitoring, diversification, collateralization |
| **Custodian Banks** | Global: BNY Mellon, State Street <br>Local / Sub-custodians | • Securities safekeeping & settlement <br>• Corporate actions, tax, lending <br>• Collateral management | **Risks:** Insolvency, fraud, commingling <br>**Protection:** Segregation, insurance, oversight |
| **Liquidity Providers** | Commercial & Central Banks, Repo/FX Swap Counterparties | • Provide committed credit lines <br>• Backup & intraday liquidity | **Requirements:** Reliable under stress, CB access, tested drawdowns |
| **Critical Service Providers (CSPs)** | Tech vendors, Cloud, SWIFT, Telecom, Power, Market Data | • Essential IT and communication services <br>• Operational support | **Risks:** Single point of failure, dependency <br>**Reqs:** Security, resilience, due diligence, SLAs |
| **Securities Registrars** | Integrated with or separate from CSDs | • Maintain ownership records <br>• Process transfers, corporate actions, proxy voting | **Requirements:** Daily reconciliation <br>**Models:** Direct (known owners) / Indirect (tiered) |

</details>

---

## ⚖️ 6. REGULATORY & OVERSIGHT AUTHORITIES
<details>
<summary><b>Expand Regulatory Authorities</b></summary>

| **Authority** | **Examples** | **Roles / Functions** | **Notes** |
|----------------|--------------|------------------------|------------|
| **Central Banks** | Federal Reserve, ECB, Bank of England, Bank of Japan | 1. Monetary policy via payment systems <br>2. FMI oversight & systemic monitoring <br>3. Operate RTGS / settlement systems <br>4. Provide liquidity (intraday, LoLR) | Risk-based and cooperative oversight; crisis management |
| **Market Regulators** | SEC, FCA, ESMA, CFTC | 1. Authorize FMIs (CSDs, CCPs, TRs) <br>2. Maintain market integrity <br>3. Ensure transparency (reporting, limits) | Powers: inspections, enforcement, emergency measures <br>Cooperation: central banks & cross-border MoUs |
| **Banking Supervisors** | OCC, FDIC, Federal Reserve, PRA, SSM, OSFI | 1. Prudential supervision (capital, liquidity) <br>2. FMI-related oversight (bank exposures to CCPs) | Coordinate with market regulators; joint crisis management |
| **Resolution Authorities** | Emerging post-2008 bodies | • Develop FMI resolution plans <br>• Ensure continuity of critical functions <br>• Protect client assets | **Powers:** Loss allocation, bridge FMIs, recovery enforcement <br>**Challenges:** Legal frameworks, cross-border recognition |

</details>

---

## 🔗 7. KEY INTERCONNECTIONS

<details>
<summary><b>Expand FMI Relationship Map</b></summary>

| **From** | **To** | **Relationship / Flow** |
|-----------|---------|--------------------------|
| Issuers | CSD | Issue securities |
| Trading Venues | CCP | Trade execution for clearing |
| Trading Venues | TR | Trade data reporting |
| Indirect Participants | Direct Participants | Access FMIs via intermediaries |
| Direct Participants | PS / CSD / CCP | Direct FMI access |
| Direct Participants | TR | Regulatory reporting |
| CCP | SSS | Settlement instructions |
| CCP | PS | Cash settlement |
| SSS ↔ PS | DvP coordination |
| SSS ↔ CSD | Securities transfer |
| CCP | Direct Participants | Margin calls |
| PS ↔ Settlement Banks | Settlement accounts |
| CSD ↔ Custodian Banks | Custody services |
| CCP ↔ Liquidity Providers | Liquidity facilities |
| All FMIs ↔ CSPs | IT & infrastructure dependencies |
| CSD ↔ Registrars | Register synchronization |
| Central Banks | PS / LP / CCP / SSS | Oversight, liquidity, operations |
| Market Regulators | CSD / CCP / TR / Venues | Regulatory supervision |
| Banking Supervisors | DPs / SBs / CBs | Prudential oversight |
| Resolution Authorities | CCP / CSD | Resolution frameworks |
| All Authorities | Each Other | Cooperative oversight and crisis management |

</details>

---

## 🧭 Summary

| **Layer** | **Primary Focus** | **Systemic Importance** |
|------------|--------------------|--------------------------|
| Market Participants | Trading & issuance | Market functioning |
| Payment Systems | Cash settlement & liquidity | High |
| Securities Infrastructure | Custody & delivery | High |
| Risk Management FMIs | Clearing & reporting | Very High |
| Supporting Infrastructure | Operational resilience | Moderate–High |
| Regulators & Authorities | Oversight & stability | Critical |
