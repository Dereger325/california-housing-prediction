# California Housing Price Prediction

Predicting median house prices in California using machine learning.

##  Results

| Model | MAE | Improvement |
|-------|-----|-------------|
| Baseline (mean) | $82,551 | - |
| Linear Regression | $50,670 | 38.6% |
| Ridge Regression | $50,727 | 38.5% |
| **XGBoost** | **$29,562** | **64.2%**  |

**Final Model:** XGBoost with feature engineering  
**Error Rate:** 14.3% on average $207k house

##  Dataset

- **Source:** California Housing Prices (1990 Census)
- **Size:** 20,640 houses
- **Features:** 10 original + 3 engineered

##  Key Features

**Engineered Features:**
- `rooms_per_household` - Distinguishes apartments from houses
- `bedrooms_per_room` - House layout indicator
- `population_per_household` - Density metric

**Most Important (XGBoost):**
1. `ocean_proximity_INLAND` (51.2%) - Location dominates
2. `median_income` (24.3%) - Wealth proxy
3. `population_per_household` (6.0%) - Our engineered feature!

##  What I Learned

1. **Location > Everything** - Being inland drops price ~$40k
2. **Model choice matters** - XGBoost beat Linear Regression by 41.7%
3. **Feature engineering helps** - But only with the right model
4. **Data quality is critical** - Price censoring at $500k caused major errors

##  Technologies

- Python, Pandas, NumPy
- Scikit-learn (Linear/Ridge Regression)
- XGBoost
- Matplotlib, Seaborn

## Project Structure
```
├── exploration.ipynb          # Main analysis notebook
├── housing.csv               # Dataset (not in repo - too large)
├── README.md                 # This file
└── requirements.txt          # Dependencies
```

## Usage
```bash
# Install dependencies
pip install -r requirements.txt

# Download dataset
# [https://www.kaggle.com/c/titanic/data?utm_source=chatgpt.com&select=test.csv]

# Run notebook
jupyter notebook exploration.ipynb
```

## 📈 Next Steps

- [ ] Deploy as FastAPI endpoint
- [ ] Add hyperparameter tuning
- [ ] Handle $500k censored data
- [ ] Incorporate external features (schools, crime)

## 👤 Author

**[Dereger325]**  
Learning ML through project-based approach  
 2026/02/15

---

*Portfolio project - 7 days, ~6 hours total*