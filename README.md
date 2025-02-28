# Starbucks Offer Optimization Project

## Project Overview
This project analyzes simulated data from the Starbucks rewards mobile app to determine which demographic groups respond best to different types of promotional offers. Using machine learning techniques, the analysis identifies patterns in customer behavior and provides recommendations for targeting specific offers to maximize effectiveness.

## Business Problem
Starbucks regularly sends offers to users of their mobile app, but not all customers respond to offers in the same way. Some offers may be more effective for certain demographic groups, while others may not be influential or may be wasted on customers who would make purchases regardless of receiving offers.

The goal is to optimize the offer-sending strategy by identifying which demographic groups respond best to which offer types, allowing for more targeted and effective promotional campaigns.

## Datasets

The project uses three JSON files:

1. **portfolio.json** - Contains offer metadata including:
   - id (offer id)
   - offer_type (BOGO, discount, informational)
   - difficulty (minimum required spend)
   - reward (reward for completing an offer)
   - duration (offer validity period in days)
   - channels (web, email, mobile, social)

2. **profile.json** - Contains customer demographic data:
   - age
   - became_member_on (membership date)
   - gender
   - id (customer id)
   - income

3. **transcript.json** - Contains customer event records:
   - event (transaction, offer received, offer viewed, offer completed)
   - person (customer id)
   - time (hours since start of test)
   - value (offer id or transaction amount)

## Requirements

- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook

## Installation

1. Clone this repository:
```
git clone https://github.com/yourusername/starbucks-capstone.git
cd starbucks-capstone
```

2. Install the required packages:
```
pip install -r requirements.txt
```

3. Download the data files (`portfolio.json`, `profile.json`, and `transcript.json`) and place them in a `/data` directory within the project folder.

## Repository Structure

```
starbucks-capstone/
│
├── data/                          # Data directory
│   ├── portfolio.json             # Offer metadata
│   ├── profile.json               # Customer demographic data
│   └── transcript.json            # Transaction and offer event data
│
├── notebooks/
│   └── Starbucks_Capstone_notebook.ipynb  # Main analysis notebook
│
├── src/                           # Source code
│   ├── data_processing.py         # Data cleaning and preparation functions
│   ├── feature_engineering.py     # Feature creation functions
│   ├── modeling.py                # Model training and evaluation
│   └── visualization.py           # Functions for creating visualizations
│
├── models/                        # Saved model files
│   └── offer_response_model.pkl   # Trained Random Forest model
│
├── blog_post.md                   # Blog post describing the project and findings
├── requirements.txt               # Project dependencies
└── README.md                      # Project overview and instructions
```

## Running the Analysis

1. Open the Jupyter Notebook:
```
jupyter notebook notebooks/Starbucks_Capstone_notebook.ipynb
```

2. Run all cells to reproduce the analysis.

Alternatively, you can run the analysis in script form:

```
python src/main.py
```

## Key Findings

### Demographic Patterns

- **Gender Impact**: Female customers show significantly higher offer completion rates (58.9%) compared to male customers (43.6%)
- **Age Effect**: Older customers (60+) respond better to offers, with completion rates of 53.3% vs. 41.3% for customers under 30
- **Income Influence**: Higher income brackets ($80K+) complete offers at nearly twice the rate of customers in the lowest income group

### Offer Effectiveness

- BOGO (Buy One Get One) offers show the highest completion rates among viewed offers
- Discount offers perform well across most demographics
- Informational offers have lower direct completion rates but still influence purchasing behavior

### Feature Importance

The most important features for predicting offer completion are:
1. Whether the offer was viewed
2. Gender (with females more responsive)
3. Membership tenure (longer = better response)
4. Income (higher = better response)

## Strategic Recommendations

Based on the analysis, the project recommends a segmented targeting strategy:

1. **High-Value Completers**: Target females 50+ with income >$80K with BOGO offers and higher reward values
2. **Responsive Mid-Value Customers**: Target middle-aged customers with a mix of discount and BOGO offers
3. **Price-Sensitive Customers**: Target lower income brackets with discount offers and lower thresholds
4. **New or Low-Engagement Customers**: Implement a progressive engagement approach starting with informational offers

## Future Work

- Explore deep learning approaches for sequence modeling of customer journeys
- Incorporate time-series features to capture evolving customer preferences
- Develop a reinforcement learning system for dynamic offer optimization
- Expand the model to account for multiple products and seasonal effects

## Acknowledgments

- Data provided by Udacity as part of the Data Science Nanodegree Program
- This project uses simulated data that mimics customer behavior on the Starbucks rewards mobile app

## Blog post
Here is the link to the blogpost: https://medium.com/@manamelatsholofelo2/starbucks-offer-optimization-a-machine-learning-approach-43f4bad01ec3

