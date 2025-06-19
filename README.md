# Geopolitics-oil-price-model
Predicting next-month crude oil price movements using historical data and geopolitical conflict signals between israel and iran.

- **Data**: Monthly oil prices from 1983 to 2025 from https://www.kaggle.com/datasets/sc231997/crude-oil-price/data
- **Features**:
  - Historical price
  - Monthly price change
  - Conflict indicator (binary feature: 1 if known conflict occurred during the month)
- **Target**:
  - `0`: Price drops >3%
  - `1`: Price remains within ±3%
  - `2`: Price rises >3%

The model predicts the **next month's price trend**, which is visualized alongside historical data.

## 📈 Model

We use a `RandomForestClassifier` to classify the next-month price trend into three categories. The model is trained and evaluated using a time-series-aware split (no shuffling), and performance is measured using precision, recall, and F1-score.

## 🔮 Prediction Visualization

The most recent known price is extended with a **forecasted price point for July 2025**, based on the predicted trend class:
- Drop → -5%
- Stable → ±0%
- Rise → +5%

This predicted point is visualized on a line chart, preserving historical context and highlighting known conflict months.

The model predicts price to be at 78.62, it currently sits at 74. I will get back to it to see the accuracy

