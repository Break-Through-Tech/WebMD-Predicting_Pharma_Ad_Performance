---

> ## Challenge Advisor: Update & Finalize Your Project Overview
>
> > 💡 **These grey text instructions are just for you, the team's Challenge Advisor; please delete them once you have completed the steps below.**
>
> We've pre-populated this Challenge Project Overview page — which is what will be shared with your Break Through Tech student team in August — using the details from your submission form. You should have received an email inviting you to join this repo as a Collaborator, enabling you to add files and make edits.
> 
> In order for your project to be finalized and assigned to a team, please:
> 1. **Review all sections below** and update or expand any content as needed, making sure to address the SME Feedback in the section immediately below. Look for square brackets to find the places below that require additional inputs from you (e.g., "About [Company / Org Name]").
> 2. **Add your dataset** to the [data folder](data) in this repo.
> 3. **Close the Issue assigned to you in this repo** to let us know that you have made your edits and the overview page is ready for final review. You can do this by going to the _Issues_ tab in the top left section of the menu above, add a comment that says "CA review complete", and click the button to Close the Issue. 
>
> If you're unfamiliar with how to edit a page like this in GitHub, check out [this tutorial](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/handson/edit-readme.html) for a quick overview (start with step 2 and only edit this page), and [this guide](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/markdown.html) on how to use Markdown to compose text.
>
>
> ❌ Remember that this is a public repo. Do NOT include: Proprietary data, PII, API keys, credentials, or anything confidential.

---

## 📋 BTT Internal Evaluation Notes
*(This section is for BTT staff only — remove before sharing with students)*

| Check | Status | Notes |
|-------|--------|-------|
| Python Compatibility | 🟢 | The tech stack is centered on Python, utilizing Python-based libraries and tools such as XGBoost, Random Forest, and SHAP values for interpretability. |
| Data Readiness | 🟢 | The dataset is under 1GB and is provided in a .csv file, indicating that it is likely ready to use with minimal cleaning required. |
| Resource Check | 🟢 | The project uses Google Colab's free tier, which is accessible to students without the need for specialized hardware or proprietary software. |

**Student Fit Score:** 7/10  
**Technical Depth Score:** 8/10  
**Overall Recommendation:** REVISE

**Advisor Feedback Draft:**
The project leverages a challenging yet realistic scenario involving pharmaceutical ad performance prediction, which aligns well with industry needs. However, ensure that students receive guidance on advanced modeling techniques and the ethical implications of using healthcare data. I recommend simplifying the complexity of multi-output modeling or providing a clearer framework for students to follow. Encourage them to focus first on a single output model to build confidence before tackling the ensemble techniques. This will ultimately lead to a better learning experience and project feasibility.

---

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
In this project, you will use historical pharmaceutical advertising campaign data (including brand, media type, audience targeting, geography, cost-per-engagement metrics, HCP specialty, client segments, and tactic-level engagement data) to build a model that predicts second-half campaign spend performance, cost efficiency (CPE), and expected engagement volume, broken out by tactic type, client target list segments, and HCP specialty groups. This will help the company address the challenge of proactively allocating media budgets and optimizing campaign planning by forecasting specific tactic and audience combinations likely to drive the highest engagement and prescription lift before H2 begins.

### Success Criteria
Quantitative: Mean Absolute Percentage Error (MAPE) < 30% on total_spend predictions and R² > 0.55 on the held-out H2 set. Qualitative: Ability to articulate which campaign characteristics strongly predict performance. Process: Documented data cleaning decisions and a reproducible notebook.

### Project Milestones

Use these milestones to guide your work. Your team will create a **GitHub Projects board** to track tasks within each milestone.

| Month | Milestone | Key Activities |
| :--- | :--- | :--- |
| September | Data Foundations & Problem Definition | • Perform Exploratory Data Analysis (EDA) on campaign performance metrics.<br>• Clean brand name inconsistencies and resolve missing values in country, pillar, profession, and specialty.<br>• Handle null columns and anomalous campaign end dates.<br>• Encode categorical variables and establish baseline predictive metrics (MAE, RMSE, $R^2$). |
| October | Feature Engineering & Model Development | • Engineer features across client target segments, HCP specialties, and tactic types.<br>• Train multi-output regression models and gradient boosting classifiers (XGBoost / LightGBM).<br>• Predict second-half campaign spend, Cost-Per-Engagement (CPE), and engagement volume.<br>• Perform hyperparameter tuning and cross-validation on target segments. |
| November | Model Interpretability, UI & Final Deliverables | • Integrate SHAP (SHapley Additive exPlanations) for per-campaign feature importance.<br>• Develop an interactive Streamlit dashboard to display predictions and risk flags.<br>• Finalize project documentation, clean GitHub repository, and stakeholder presentation deck. |

### Stretch Goals
* **Campaign ROI Ranking:** Develop a cost-efficiency scoring system that ranks predicted campaigns by anticipated return on investment.
* **Clustering + Prediction Pipeline:** Apply unsupervised clustering (K-Means or DBSCAN) to group campaigns by profile similarity prior to running cluster-specific regressors.
* **Time-Series Forecasting Layer:** Build a temporal trend model for high-volume brands and ensemble it with regression outputs.
* **Data Quality Audit Tool:** Build an automated validation script or UI widget that flags incoming campaign records with missing or inconsistent metadata before running inference.

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset

**Name and Source:** Historical Pharmaceutical Advertising Campaign Data  
**Format:** CSV  
**Size:** under 1gb  
**Location:** [Link to dataset or instructions for accessing it]

### Key Details
- The dataset includes campaign performance metrics: total engagement, type of engagement, NRx rates (prescription volume), brand, media type, audience targeting, geography, CPE metrics, HCP specialty, and client segments. Provided as a .csv file.
- [Any known limitations or preprocessing needed]
- [Link to data dictionary or documentation, if available]

---

## 🛠️ Suggested Approach

**ML Problem Type:** Supervised Regression

**Recommended Libraries:**
- Supervised regression
- Multi-output modeling
- Gradient boosting (Random Forest, XGBoost)
- Linear regression baseline
- Clustering (K-Means, DBSCAN)
- SHAP values for interpretability
- Time-series forecasting (ensemble)
- Google Colab

**Evaluation Metrics:**
- Mean Absolute Percentage Error (MAPE)
- R-squared

---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [Link to an article or blog post about the problem domain]
- [Link to an industry report or case study]

**Technical Tutorials:**
- [Link to a free tutorial on the ML technique(s) involved]
- [Link to documentation for a key library or tool]

**Code Examples:**
- [Link to a relevant GitHub repo]
- [Link to a sample implementation or starter code]

**Other:**
- [Links to any additional resources — e.g., papers, videos, podcasts, etc.]

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Slack (Break Through Tech workspace)  
**Response time:** Within 48 hours on weekdays  

**Recommended Tools:**
- **Coding:** Google Colab
- **Collaboration:** GitHub, Notion
- **Virtual Meetings:** Zoom, Google Meet

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I'm excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).

---
