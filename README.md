# student-retention-prediction
🚀 Project Overview
This project leverages machine learning to predict which students are at risk of dropping out from educational opportunities, enabling proactive intervention and improving retention rates by up to 700+ students annually.

By analyzing 1,701 student application records with 22 engineered features, we built a production-ready Gradient Boosting model achieving 90.3% accuracy and 75% churn recall.

📊 Dataset
Source: Cleaned student opportunity application data
Size: 1,701 records × 22 features
Target Variable: completion_flag (0 = Churn, 1 = Completed)
Class Distribution: 82.5% completion, 17.5% churn (imbalanced)

Key Features:
Demographics: Age, gender, country, institution

Temporal: Application lag, start lag, opportunity duration

Institutional: Success rate, opportunity count, competition level

Behavioral: Previous applications, region, field of study

🔍 Exploratory Data Analysis (EDA)
Key Insights:
Age Distribution: Majority concentrated in 18-25 age bracket

Geographic Patterns: High representation from India and United States

Seasonal Trends: Application spikes align with academic calendars

Institutional Impact: Success rates vary significantly by institution

Gender Balance: Minimal gender-based churn differences observed

Visualizations Included:
Age vs Churn histograms

Regional churn distribution

Correlation heatmaps

Institution success rate boxplots

Feature importance rankings

🛠️ Feature Engineering
Created Features:
apply_lag: Days between signup and application submission

start_lag: Days between application and opportunity start

opportunity_duration: Total program length in days

One-hot encoding: Gender, country, region, opportunity category

Data Processing:
Removed duplicate and null values

Handled missing dates with median imputation

Eliminated data leakage by removing post-outcome features

Stratified train-test split (80-20) to preserve class distribution

🤖 Models Tested
We evaluated four classification algorithms to find the optimal predictor:

Model	Accuracy	Recall (Churn)	Key Strength
🏆 Gradient Boosting	90.3%	75.0%	Best accuracy-recall balance
Random Forest	90.0%	74.0%	Strong generalization
Decision Tree	88.0%	68.0%	High interpretability
Logistic Regression	88.0%	61.0%	Fast baseline model
Why Gradient Boosting?
✅ Highest overall accuracy

✅ Strong recall for minority class (churn detection)

✅ Robust to overfitting via regularization

✅ Excellent feature importance insights

✅ Validated with 5-fold cross-validation (84.03% ± 1.70%)

📈 Model Performance
Final Metrics (Test Set):
Accuracy: 90.3%

Precision: 91.5%

Recall (Churn): 75.0%

F1-Score: 88.7%

Cross-Validation: 84.03% (±1.70% SD)

Confusion Matrix:
text
                Predicted
              Not Churn | Churn
Actual  
Not Churn      264    |    8
Churn           22    |   44
🔑 Key Findings
Top 5 Churn Drivers (Feature Importance):
start_lag (25%) – Long waiting periods before program start

apply_lag (15%) – Delays between signup and application

opportunity_duration (12%) – Longer programs = higher dropout

previous_applications (10%) – First-timers more at risk

institution_success_rate (8%) – Low success history correlates with churn

Actionable Insights:
⏰ Process bottlenecks matter more than demographics

📉 Reduce onboarding friction by 30% to improve retention

🎯 Flag students with long wait times for priority support

💡 Recommendations
1. Optimize Onboarding Process
Automate enrollment communications

Set SLA targets for student allocation

Provide "keep-warm" content during waiting periods

2. Program Design Improvements
Break long programs into modular milestones

Introduce early success checkpoints

Offer flexible scheduling options

3. Targeted Interventions
Real-time churn risk alerts for advisors

Personalized mentorship for high-risk students

Incentivize reapplication for unsuccessful candidates

4. Continuous Monitoring
Dashboard integration for live tracking

Quarterly model retraining with new data

A/B testing intervention strategies
