# Customer Churn Prediction Project

## Project Overview
A machine learning project to predict customer churn for a subscription-based service using advanced feature engineering and ensemble models.
train.csv file link: https://drive.google.com/file/d/1lqmGEjxsz4aCiIS3sG9VUGdRIWE1Hrhs/view?usp=sharing

## Key Results
- **Model Performance**: 93.25% AUC with XGBoost
- **Identified**: 679 high-risk customers (>70% churn probability)
- **Test Set Predictions**: 6.56% churn rate among 104,480 customers

## Dataset
- **Training Set**: 243,787 customers with 21 features
- **Test Set**: 104,480 customers
- **Target Variable**: Binary churn indicator (18.12% churn rate in training)

## Feature Engineering
Created 14 new features including:
- `EngagementScore`: Composite metric of user activity
- `SupportIntensity`: Support tickets relative to tenure
- `ChargeToEngagementRatio`: Value vs. usage indicator
- Customer lifecycle features (New/Mid/Long-term)

## Top Churn Indicators
1. **Support Tickets Frequency** - Higher complaints indicate dissatisfaction
2. **Customer Tenure** - New customers (<12 months) at higher risk
3. **Engagement Level** - Low platform usage predicts churn
4. **Subscription Type** - Basic plan users churn more

## Models Evaluated
| Model | CV AUC | Training Time |
|-------|---------|---------------|
| XGBoost | 0.929 | 12.8s |
| LightGBM | 0.933 | 23.8s |
| Random Forest | 0.928 | 287.5s |
| Gradient Boosting | 0.884 | 730.1s |
| Logistic Regression | 0.792 | 9.3s |

## Business Recommendations
1. **Immediate Actions**
   - Target 679 high-risk customers with retention offers
   - Improve customer support quality
   
2. **Strategic Initiatives**
   - New customer onboarding program (first 12 months critical)
   - Engagement campaigns for low-activity users
   - Personalized content recommendations

## Files Generated
- `churn_predictions.csv` - Predictions for test set
- `retention_priority_list.csv` - Top 100 customers for retention
- `churn_prediction_model.pkl` - Trained model

## Tech Stack
- Python 3.x
- scikit-learn, XGBoost, LightGBM
- pandas, numpy, matplotlib, seaborn
- imbalanced-learn (SMOTE)
