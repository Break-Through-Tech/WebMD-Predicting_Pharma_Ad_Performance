

# Did that campaign work?: Predicting Pharma Ad Performance

**Company / Org:** WebMD  
**Challenge Advisor:** Kimia Naeiji, kimianaeiji@gmail.com  
**Program:** Break Through Tech AI Studio - Fall 2026

---

## 🏢 About WebMD

WebMD provides valuable health information and services, focusing on empowering consumers to make informed health decisions. As a leader in digital health, we aim to improve the health and wellness of our users through a comprehensive understanding of the healthcare landscape.

---

## 🎯 The Challenge

### Project Summary
In this project, you will use historical pharmaceutical advertising campaign data (including brand, media type, audience targeting, geography, cost-per-engagement metrics, HCP specialty, client segments, and tactic-level engagement data from January-June) and supervised regression, multi-output modeling, and/or gradient boosting ML techniques to build a model that predicts second-half campaign spend performance, cost efficiency (CPE), and expected engagement volume, broken out by tactic type (Email Alert, Brand Alert, Sponsored Video, etc.), client target list segments, and HCP specialty groups. This will help our company address the challenge of proactively allocating media budgets and optimizing campaign planning by forecasting not just overall campaign ROI, but which specific tactic and audience combinations are likely to drive the highest engagement and prescription lift before H2 begins,  enabling smarter, more granular investment decisions at the segment and specialty level.

### Success Criteria
Success should be evaluated on three levels:

Quantitative (model performance): The primary metric should be Mean Absolute Percentage Error (MAPE) on total_spend predictions for H2 campaigns, since spend varies widely across campaigns (from near-zero to billions) and a percentage-based error is more interpretable than RMSE. A secondary metric of R² should confirm the model explains meaningful variance. Given the dataset size, an R² above 0.55 and a MAPE below 30% on the held-out H2 set would constitute a successful outcome, students should define this threshold explicitly in their November presentation.

Qualitative (business relevance): A successful outcome also means students can articulate which campaign characteristics most strongly predict spend or CPE (e.g., "urology-targeted SPONSORED_VIDEO campaigns in the USA have 40% higher predicted CPE than the baseline"). This insight is directly actionable for campaign planning.

Process success: The team has documented their data cleaning decisions, can justify their model choice, and has produced a reproducible notebook.

Optional: They can design a frontend like a chatbot to have the user ask question regarding the second 6 months campaign performance


### Stretch Goals

- Multi-target modeling: Predict both total_spend and meta_mapped_cpe simultaneously using multi-output regression, then build a composite "efficiency score" that ranks predicted campaigns by ROI.
- Clustering + prediction pipeline: Use unsupervised clustering (K-Means or DBSCAN) to group campaigns by profile similarity before training separate regressors per cluster, a more realistic modeling pattern for heterogeneous campaign data.
Time-series forecasting layer: For brands with enough historical rows (e.g., ABBVIE, AMGEN), build a simple time-series trend model and combine it with the regression predictions as an ensemble.
- Interpretability deep-dive: Use SHAP values to produce per-campaign explanations ("this campaign is predicted to overspend because it targets profession=8 in country=zaf"), making the model's output actionable for non-technical stakeholders.
  Data quality audit tool: Build a small script or dashboard that flags incoming campaign records likely to produce unreliable predictions (e.g., missing specialty, unknown profession codes), making the model production-ready rather than just experimental.

### Project Milestones

Use these milestones to guide your work. Your team will create a **GitHub Projects board** to track tasks within each milestone.

| Month | Milestone | Key Activities |
|---|---|---|
| September | Data Foundations & Problem Definition | Students should complete exploratory data analysis (EDA): cleaning brand name inconsistencies, handling nulls in country, pillar, profession, and specialty, dropping or engineering around the total_engagements null column and the 2099 end dates, and encoding categorical variables.<br>• A Data Quality Report (submitted end of Week 2 of September): a notebook documenting every issue found, how many rows/columns are affected, and the team's proposed fix for each.<br>• A Cleaned Dataset Artifact: the final cleaned_df.csv the team will use for all subsequent modeling, versioned and committed so instructors can audit the choices made.<br>• A Cleaning Decision Log: a short written justification for each major choice (e.g., "We dropped total_engagements because it was 100% null; we treated numeric profession codes as categorical rather than ordinal because there is no natural ordering").<br><br>By the end of September, the team should have a clean, model-ready dataset with a clearly defined target variable (total_spend or meta_mapped_cpe) and a documented feature set. They should also produce a written problem framing document and baseline statistics. |
| October | Feature Engineering & Model Development | Students should engineer meaningful features (e.g., campaign age in days from start date, brand-level historical average CPE, media type dummies, country groupings), then train and compare at least two model types: a linear regression baseline and a tree-based model (Random Forest or XGBoost). By end of October, the team should have initial model performance metrics on a validation set and a comparison table showing which features matter most (feature importance or coefficients). |
| November | Evaluation, Iteration & Storytelling | Students should iterate on the best-performing model (hyperparameter tuning, additional feature engineering), evaluate it formally on the H2 held-out test set, and build a clear results presentation. By end of November, the team should have a final model, evaluation metrics, and a 5–10 slide deck explaining their methodology, results, and business recommendations. A short written report should accompany the deck. |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset

The dataset includes Campaign's performances, including total engagement, type of engagement, NRx rates (rate of prescription volume before and after the campaign), etc. This data helps students to use this data to learn the campaign performance. 

This data will be shared as a .csv file with the student team.

**Location:** data/BreakThroughTech_training_data_1.xlsx



---

## 🛠️ Suggested Approach

**ML Problem Type:** Classification,Regression,Clustering

**Recommended Libraries:**
- [e.g., pandas, scikit-learn, TensorFlow, Hugging Face]

**Evaluation Metrics:**
- [e.g., Accuracy, Precision/Recall, RMSE, BLEU score]

---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [WebMD](https://www.webmd.com/) - Background on WebMD and the healthcare information space
- [Scikit-learn Supervised Learning Guide](https://scikit-learn.org/stable/supervised_learning.html) - Overview of supervised machine learning methods, including regression

**Technical Tutorials:**
- [Scikit-learn Preprocessing Documentation](https://scikit-learn.org/stable/modules/preprocessing.html) - Guidance on preparing numerical and categorical features for modeling
- [Scikit-learn Model Evaluation Documentation](https://scikit-learn.org/stable/modules/model_evaluation.html) - Guidance on regression metrics and model evaluation
- [XGBoost Python Documentation](https://xgboost.readthedocs.io/en/stable/python/) - Documentation for building gradient-boosted models

**Code Examples:**
- [Scikit-learn Examples](https://scikit-learn.org/stable/auto_examples/) - Sample implementations for preprocessing, regression, model selection, and evaluation
- [XGBoost Examples](https://xgboost.readthedocs.io/en/stable/python/examples/) - Example implementations using XGBoost

**Other:**
- [Pandas Documentation](https://pandas.pydata.org/docs/) - Reference for data cleaning, manipulation, and exploratory analysis
- [SHAP Documentation](https://shap.readthedocs.io/) - Resources for interpreting machine learning model predictions and feature importance

*Feel free to explore beyond these, and share anything interesting you find with me!*

---
## 🤝 How We'll Work Together

**Official check-ins:** During our biweekly 45-minute AI Studio Lab Section meeting block (2nd and 4th week of every month)

 **Other ways to reach out to me with questions:** 
* [e.g., Your team's channel within Break Through Tech’s Discord space]
* [e.g., Email; please copy your teammates and AI Studio Coach]
* [e.g., Request a team check-in on Zoom]
* [Note: I will aim to respond within 48 hours. Please reach out to your AI Studio Coach with urgent questions.]

> 💡 **Challenge Advisor: Please update the above based on your availability and preference. If you are not able to answer questions or meet with fellows outside of the biweekly Lab Section check-ins, simply write in "N/A (only available during the official check-in times)"**



## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I’m excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech’s Bridge to Studio - Session C). 
