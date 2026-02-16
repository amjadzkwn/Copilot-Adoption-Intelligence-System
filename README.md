# Copilot-Adoption-Intelligence-System

## 📌 Project Overview

This project implements an AI‑driven Copilot Adoption Intelligence System designed to evaluate organizational readiness, adoption likelihood, and productivity impact of GenAI tools.
The system combines machine learning, sentiment analysis, and business rule logic to support data‑driven decision‑making for enterprise AI adoption.


## 🎯 Objectives

1. Predict the likelihood of successful Copilot adoption within an organization
2. Estimate the expected productivity impact of GenAI usage
3. Analyze employee sentiment toward Copilot adoption
4. Provide actionable recommendations to improve adoption outcomes


## 🧠 Machine Learning Approach

The system uses two Random Forest models:

1. Classification Model to predict high vs low adoption likelihood
2. Regression Model to estimate productivity change

Class imbalance is addressed using Random Under Sampling, ensuring fair and stable predictions across adoption classes.


## 📊 Dataset Description

The dataset contains organizational‑level information, including:
- Training hours provided
- Number of employees impacted
- New roles created
- Industry and country context
- Employee sentiment feedback
- Measured productivity change

Categorical variables are encoded, while numerical variables are standardized to ensure consistency across industries and regions.

**Source**: [Enterprise GenAI Adoption and Workforce Impact Data](https://www.kaggle.com/datasets/tfisthis/enterprise-genai-adoption-and-workforce-impact-data) (Kaggle)

## 🔄 Data Preprocessing & Feature Engineering

Key preprocessing steps include:

1. Missing value handling for employee feedback
2. Label encoding for categorical variables
3. Standardization of numerical features using StandardScaler
4. Sentiment score extraction using VADER sentiment analysis

A derived high_adoption label is created based on training intensity, productivity improvement, and positive sentiment.


## ⚖️ Feature Scaling Strategy

All numerical inputs are normalized during model training.
As a result:

- Inputs represent relative organizational intensity, not raw absolute values
- Predictions are robust across companies of different sizes and industries

This design choice improves generalization and prevents scale bias.


## 🖥 Interactive Streamlit Dashboard

The Streamlit application allows users to:

- Input organizational training and adoption parameters
- Enter qualitative employee feedback
- Instantly receive adoption probability and productivity predictions

The interface is designed for business users, analysts, and decision‑makers.


## 📈 Prediction Outputs

The system provides:

- High Adoption Probability (classification output)
- Predicted Productivity Change (scaled)
- Employee Sentiment Score

These outputs are interpreted together to reflect organizational readiness.


## 💡 Recommendation Engine

Based on adoption probability:

- Low adoption likelihood triggers recommendations such as additional training and change champions
- High adoption likelihood suggests scaling, automation, and advanced Copilot use cases

This bridges the gap between prediction and real‑world action.


## 🏗 System Architecture

The project consists of:

- A model training script for preprocessing, training, and saving models
- A Streamlit application for deployment and interaction
- Serialized models and feature metadata for consistent inference


## 📊 Sample Results & Model Interpretation

The following results demonstrate how the Copilot Adoption Intelligence System responds to different organizational scenarios by combining training intensity, workforce impact, role changes, and employee sentiment.

### 🔹 Scenario 1: Low Training & Negative Sentiment
Input:
- Training Hours Provided: 5
- Number of Employees Impacted: 20
- New Roles Created: 0
- Employee Feedback: Copilot is confusing and slow down my work. No proper guidance.

Output:
- Sentiment Score: -0.48
- High Adoption Probability: 0.02
- Predicted Productivity Change: -0.16

💡 Recommendation Engine:
⚠️ Low adoption risk detected

- Recommend additional Copilot training
- Provide prompt templates
- Assign Copilot champions in department

### 🔹 Scenario 2: Moderate Training & Mildly Positive Sentiment
Input:
- Training Hours Provided: 10
- Employees Impacted: 40
- New Roles Created: 1
- Employee Feedback: Copilot seems okay but I'm not sure how to use it effectively.

Output:
- Sentiment Score: 0.43
- High Adoption Probability: 0.70
- Predicted Productivity Change: -0.07

💡 Recommendation Engine: 
✅ High adoption likelihood

- Ready for advanced Copilot use cases
- Suggest automation & workflow optimization
- Scale adoption to similar teams

### 🔹 Scenario 3: Moderate Training but Ongoing User Struggles
Input:
- Training Hours Provided: 20
- Employees Impacted: 50
- New Roles Created: 2
- Employee Feedback: Copilot helps sometimes, but I still struggle with complex tasks.

Output:
- Sentiment Score: -0.28
- High Adoption Probability: 0.04
- Predicted Productivity Change: -0.32

💡 Recommendation Engine:
⚠️ Low adoption risk detected

- Recommend additional Copilot training
- Provide prompt templates
- Assign Copilot champions in department

### 🔹 Scenario 4: High Training & Strong Positive Feedback
Input:
- Training Hours Provided: 40
- Employees Impacted: 120
- New Roles Created: 5
- Employee Feedback: Copilot significantly improves my productivity and task quality.

Output:
- Sentiment Score: 0.42
- High Adoption Probability: 0.72
- Predicted Productivity Change: -0.21

💡 Recommendation Engine:
✅ High adoption likelihood

- Ready for advanced Copilot use cases
- Suggest automation & workflow optimization
- Scale adoption to similar teams

### 🔹 Scenario 5: Small Team with Positive Perception
Input:
- Training Hours Provided: 30
- Employees Impacted: 10
- New Roles Created: 1
- Employee Feedback: When used properly, Copilot is powerful, but few people use it.

Output:
- Sentiment Score: 0.23
- High Adoption Probability: 0.62
- Predicted Productivity Change: -0.46

💡 Recommendation Engine:
✅ High adoption likelihood

- Ready for advanced Copilot use cases
- Suggest automation & workflow optimization
- Scale adoption to similar teams


## 🧠 Key Insights from Results

- Employee sentiment plays a critical role in adoption outcomes
- Higher training hours do not guarantee success without effective guidance
- The model captures realistic organizational trade‑offs between readiness, perception, and productivity
- Recommendations align with change‑management best practices


## 🚀 Use Cases

1. Enterprise AI adoption assessment
2. Change management and workforce planning
3. Executive decision support for GenAI investments
4. Academic research on AI adoption and productivity impact


## 🔮 Future Enhancements

Potential improvements include:
- Multi‑class adoption maturity levels
- Department‑level predictions
- Time‑series adoption tracking
- Explainable AI (SHAP) integration
