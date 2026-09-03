# 🚚 Supply Chain Late Delivery Risk Predictor

> **Capstone Project** — Francis Amojelar | Calgary, AB

A machine learning–powered web application that predicts whether a supply chain order will be delivered **late** based on order attributes such as shipping mode, product category, customer segment, discount rate, and geographic region.

---

## 🎯 Problem Statement

Late deliveries are one of the most costly and customer-damaging events in supply chain operations. This project builds a **binary classification model** to flag high-risk orders before they ship, enabling proactive interventions.

- **Target variable:** `Late_delivery_risk` (0 = On-time, 1 = Late)
- **Dataset:** [DataCo Smart Supply Chain for Big Data Analysis](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)
- **Model:** Random Forest Classifier (via MindsDB / Supervised ML)

---

## 📂 Project Structure

```
supply-chain-delay-predictor/
├── README.md                    # Project overview (this file)
├── predictor-app.html           # Interactive web predictor UI
├── notebook/
│   └── supply_chain_eda.ipynb   # EDA + model training notebook
├── data/
│   └── .gitkeep                 # Place DataCoSupplyChainDataset.csv here
└── assets/
    └── screenshots/             # UI screenshots
```

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

## 🖥️ Live Demo

Open `predictor-app.html` in your browser, enter your MindsDB API key and access token, fill in order details, and click **Predict**.

Alternatively, access the hosted JotForm agent demo:
👉 [https://agent.jotform.com/01a068014d98700080c8c7a4ca4e868f860c](https://agent.jotform.com/01a068014d98700080c8c7a4ca4e868f860c)

---

## ⚙️ Setup

### 1. Install dependencies
```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
```

### 2. Get the dataset
Download from Kaggle and place in `data/`:
```
data/DataCoSupplyChainDataset.csv
```

### 3. Run the notebook
```bash
jupyter notebook notebook/supply_chain_eda.ipynb
```

### 4. MindsDB API
To use the live predictor app, create a free account at [MindsDB Cloud](https://cloud.mindsdb.com), train your model, and copy your API key + access token into the app.

---

## 📊 SDG Alignment

| Goal | Relevance |
|---|---|
| **SDG 9** — Industry, Innovation & Infrastructure | Improves supply chain efficiency through AI |
| **SDG 12** — Responsible Consumption & Production | Reduces waste from failed/delayed deliveries |
| **SDG 8** — Decent Work & Economic Growth | Supports logistics workforce planning |

---

## 👤 Author

**Francis Amojelar** — [@ciscel](https://github.com/ciscel)  
Calgary, AB · [Vouchya](https://www.vouchya.com)

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
