
# Pricing Intelligence AI Workbench

A lightweight **AI-powered pricing analysis tool** designed to explore pricing strategy for a **B2B digital voucher marketplace**.

This project demonstrates how product managers, analysts, and builders can combine **structured pricing data + AI reasoning** to discover pricing opportunities, supplier trade‑offs, and margin optimization strategies.

The system combines:

- A **pricing intelligence workbook**
- A **browser-based HTML interface**
- Optional **AI API integration**

The goal is to simulate how **AI product systems assist pricing decisions** in real digital marketplaces.

---

# Problem Context

Digital marketplaces often sell products such as:

- Gift cards
- Gaming credits
- Mobile top‑ups
- Prepaid vouchers
- Digital subscriptions

Each product (SKU) can be sourced from **multiple suppliers**, each offering:

- Different prices
- Different fees
- Different reliability
- Different availability

At the same time, the marketplace sells to **B2B clients**, where pricing decisions impact:

- Revenue
- Profit margin
- Competitiveness
- Demand
- Operational risk

In many companies, these decisions are still handled using **spreadsheets and manual analysis**.

This project explores how **AI can assist pricing intelligence** using structured signals from marketplace data.

---

# Repository Structure

pricing-ai-workbench
│
├ index.html
├ ai_pricing_machine_workbook_public_demo.xlsx
└ README.md

### index.html

A browser-based interface that:

- Loads the pricing workbook
- Displays pricing tables
- Allows natural language AI queries
- Performs pricing analysis
- Optionally connects to an AI API

No backend server is required.

---

# Workbook Overview

The workbook simulates a **pricing intelligence data model**.

All names are **fully anonymized for public use**.

Example aliases:

Client_001  
Supplier_Atlas  
Supplier_Nova  

---

# Workbook Sheets

## orders_fact

Raw order-level transaction data.

Contains:

- client_name
- brand
- supplier_name
- sell_price
- supplier_cost
- currency
- region
- order timestamp

This is the primary transactional dataset.

---

## sku_master

Product catalog metadata.

Fields include:

- sku_id
- brand
- product_name
- denomination
- region
- strategic_flag

---

## supplier_offers

Supplier pricing and supply options.

Includes:

- supplier_cost
- supplier_fee
- reliability_score
- inventory

---

## sku_day_sales

Daily aggregated demand signals.

Fields:

- order_date
- sku_id
- units
- revenue
- avg_sell_price

Used for demand trend analysis.

---

## market_signals

Market behavior indicators.

Includes:

- demand_trend
- competitor_price
- price_sensitivity
- seasonality_index

Some values are simulated placeholders.

---

## operations_signals

Operational cost indicators.

Fields:

- refund_rate
- support_cost

These represent hidden operational costs affecting profitability.

---

# Pricing Intelligence Metrics

## Gross Margin

gross_margin = sell_price - supplier_cost

---

## Refund Cost

refund_cost = sell_price * refund_rate

---

## True Margin

true_margin = gross_margin - refund_cost - support_cost

This represents real economic profitability.

---

## Price Gap vs Competitor

price_gap_vs_competitor = sell_price - competitor_price

If positive → product may be overpriced.

---

# Pricing Simulation

The workbook includes a simulation engine to evaluate pricing scenarios.

## Simulated Price

simulated_price = sell_price * (1 + price_change_pct)

---

## Demand Drop

demand_drop_pct = price_sensitivity * price_change_pct

A simplified elasticity assumption.

---

## Simulated Margin

simulated_margin =
simulated_price
- supplier_cost
- refund_cost
- support_cost

---

## Simulated Profit Index

simulated_profit_index =
simulated_margin * demand_multiplier

This metric helps rank pricing opportunities.

---

# AI Query Dataset

The sheet **ai_query_view** is designed as the primary dataset for AI reasoning.

Each row represents:

SKU + Supplier combination

Important fields include:

- sell_price
- supplier_cost
- competitor_price
- true_margin
- price_gap_vs_competitor
- price_sensitivity
- demand_drop_pct
- simulated_profit_index

This allows AI to reason about pricing trade‑offs efficiently.

---

# Example Business Questions

The system is designed to explore questions such as:

- Which SKUs can increase price by 5% while demand drop stays below 1%?
- Which SKUs are overpriced versus competitors?
- Which suppliers offer the best margin potential?
- Which products are margin traps due to refunds or support cost?
- Which SKUs have the highest simulated profit opportunity?
- Which brands generate revenue but weak margins?

---

# Running the Application

Step 1 — Download the repository.

Step 2 — Open:

index.html

in your browser.

Step 3 — Upload the workbook:

ai_pricing_machine_workbook_public_demo.xlsx

Step 4 — Explore pricing data and run analysis.

---

# Optional AI Integration

You can connect the interface to an AI API.

Example configuration:

Endpoint:
https://api.openai.com/v1/responses

Model:
gpt-4o

Provide your API key in the settings panel.

---

# Local Analysis Mode

Even without AI integration the tool can perform analysis such as:

- ranking SKUs by simulated profit
- detecting overpriced products
- identifying low margin SKUs
- flagging refund-risk products

---

# Why This Project Exists

This project demonstrates how **AI product managers can approach real business problems**:

1. Understand the domain
2. Model business signals
3. Build decision systems
4. Add AI reasoning on top

It is designed as an **AI product management learning project**.

---

# Important Data Note

All data in this repository is **synthetic or anonymized**.

Signals like:

- competitor_price
- price_sensitivity
- refund_rate
- support_cost
- supplier_fee
- reliability_score
- inventory

are simulated placeholders.

---

# License

This project is provided for educational and experimentation purposes.

Feel free to fork and experiment.
