# 🚚 Supply Chain Late Delivery Risk Predictor

> **Capstone Project** — Francis Amojelar | BuiltSmart AI Cohort, September 2026

An AI-powered classifier that predicts whether a shipment will be delayed — enabling procurement teams to act before disruptions stall critical infrastructure projects.

🌐 **Live Project Website:** [https://www.vouchya.com/capstone](https://www.vouchya.com/capstone)  
🤖 **JotForm AI Agent:** [https://agent.jotform.com/01a068014d98700080c8c7a4ca4e868f860c](https://agent.jotform.com/01a068014d98700080c8c7a4ca4e868f860c)

---

## 🎯 Problem Statement

Late deliveries are one of the most costly and customer-damaging events in supply chain operations. This project builds a **binary classification model** to flag high-risk shipments before they depart, enabling proactive interventions by procurement teams and site managers.

- **Target variable:** `Late_delivery_risk` (0 = On-time, 1 = Late)
- **Dataset:** [DataCo Smart Supply Chain](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis) — 177,519 records, 29 columns
- **Platform:** [BrainToy MLOS](https://braintoy.ai)
- **Model:** DecisionTreeClassifier v.3 — **81.93% accuracy, 0.82 ROC AUC**

---

## 🧠 Model Development

### Data Preparation
- Uploaded DataCoSupplyChain CSV (177,519 records, 29 columns) into BrainToy MLOS
- Locked `Late_delivery_risk` as the binary target variable with an 80/20 train/validation split
- Applied Categorical-to-Numeric transformation to 11 high-cardinality features including `Type`, `Category_Name`, `Shipping_Mode`, `Market`, and `Customer_Segment`

### Model Selection

| Model | Accuracy | ROC AUC | Hamming Loss |
|---|---|---|---|
| **DecisionTreeClassifier v.3** ✅ | **81.93%** | **0.82** | **0.18** |
| ExtraTreesClassifier v.1 | Lower | — | 0.24 |

DecisionTreeClassifier v.3 selected as the deployment candidate — outperforming ExtraTreesClassifier on accuracy and Hamming Loss.

### Governance
Model container submitted to **fariha@braintoy.ai** for third-party ethical validation per BuiltSmart AI governance requirements — verifying the model's logic is mathematically stable and free of critical biases before deployment.

---

## 🖥️ Live Prediction App

**CapstoneML v.3** is deployed on BrainToy MLOS as a no-code interactive interface. Non-technical users — site managers, procurement officers — can input shipment parameters and receive an instant Late/On-Time risk label.

👉 [Try the live predictor](https://www.vouchya.com/capstone)

---

## 🧠 Model Inputs

| Feature | Type | Description |
|---|---|---|
| `Type` | Categorical | Payment type (DEBIT, TRANSFER, CASH, PAYMENT) |
| `Days_for_shipment_scheduled` | Numeric | Planned shipment days |
| `Benefit_per_order` | Numeric | Profit per order |
| `Sales_per_customer` | Numeric | Revenue per customer |
| `Category_Name` | Categorical | Product category |
| `Customer_Segment` | Categorical | Consumer, Corporate, Home Office |
| `Department_Name` | Categorical | Store department |
| `Latitude` / `Longitude` | Numeric | Delivery geo-coordinates |
| `Market` | Categorical | Geographic market region |
| `Order_City` / `Order_Country` | Categorical | Delivery location |
| `Order_Item_Discount` | Numeric | Discount amount |
| `Order_Item_Discount_Rate` | Numeric | Discount rate (0–1) |
| `Order_Item_Product_Price` | Numeric | Unit product price |
| `Order_Item_Profit_Ratio` | Numeric | Item-level profit ratio |
| `Order_Item_Quantity` | Numeric | Units ordered |
| `Sales` | Numeric | Total sales value |
| `Order_Item_Total` | Numeric | Line total |
| `Order_Profit_Per_Order` | Numeric | Order-level profit |
| `Order_Region` | Categorical | Sub-region |
| `Order_State` | Categorical | Delivery state |
| `Product_Name` | Categorical | Product identifier |
| `Product_Price` | Numeric | Listed product price |
| `Product_Status` | Numeric | 0 = Active, 1 = Inactive |
| `Shipping_Mode` | Categorical | Standard, Second, First, Same-day |
| `Order_Month` | Numeric | Month of order (1–12) |
| `Order_DayOfWeek` | Numeric | Day of week (0=Mon, 6=Sun) |

---

## 📊 SDG Alignment

| Goal | Relevance |
|---|---|
| **SDG 9** — Industry, Innovation & Infrastructure | Improves supply chain efficiency through AI |
| **SDG 12** — Responsible Consumption & Production | Reduces waste from failed/delayed deliveries |
| **SDG 8** — Decent Work & Economic Growth | Supports logistics workforce planning |

---

## 📂 Project Structure

```
supply-chain-delay-predictor/
├── README.md                    # Project overview (this file)
├── predictor-app.html           # Interactive web predictor UI
├── notebook/
│   └── supply_chain_eda.ipynb   # EDA + model training notebook
└── data/
    └── .gitkeep                 # Place DataCoSupplyChainDataset.csv here
```

---

## 👤 Author

**Francis Amojelar** — [@ciscel](https://github.com/ciscel)  
BuiltSmart AI Cohort · Calgary, AB · [vouchya.com](https://www.vouchya.com)

---

## 📄 License

MIT License
