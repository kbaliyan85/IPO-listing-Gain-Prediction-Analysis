

# 📊 IPO Listing Gain Prediction & Analysis
### Analyzing the Impact of Grey Market Premium (GMP) and Subscription Demand on Indian IPO Performance

## 1. Project Overview

The Indian IPO market attracts significant investor participation, but predicting whether an IPO will generate positive listing gains remains challenging.

This project focuses on analyzing historical Indian IPO data to understand the factors influencing listing-day performance and develop machine learning models to predict IPO listing gains.

The project investigates the relationship between **Grey Market Premium (GMP), subscription demand, and actual listing performance**, with particular emphasis on how GMP and subscription levels together influence listing outcomes.

It combines data collection, data preprocessing, exploratory data analysis, Excel-based business analysis, SQL, machine learning, and Power BI visualization to provide an end-to-end analytical perspective on the Indian IPO market.

## 2. Business Problem

Investors often use GMP and IPO subscription figures to evaluate the potential performance of an upcoming IPO. However, relying on either indicator independently may not provide a complete picture.

This project aims to answer the following business questions:

- Does a higher GMP indicate better IPO listing gains?
- How does subscription demand influence listing performance?
- Can strong subscription demand compensate for negative GMP?
- Does positive GMP guarantee positive listing gains?
- Which investor categories (QIB, NII/HNI, and Retail) show a stronger relationship with listing gains?
- How does IPO performance vary across different years and issue sizes?
- Can historical IPO data be used to predict listing gains using machine learning?

## 3. Dataset Description

The project uses a historical dataset of **393 Indian IPOs** containing IPO-related information and pre-listing indicators.

### Key Dataset Features

| Feature | Description |
|---|---|
| IPO Name | Name of the company issuing the IPO |
| IPO Date | IPO-related date information |
| Issue Price | Price at which shares were offered |
| GMP | Grey Market Premium before listing |
| GMP Date | Date of the recorded GMP observation |
| Retail Subscription | Retail investor subscription multiple |
| QIB Subscription | Qualified Institutional Buyers subscription |
| NII Subscription | Non-Institutional Investors subscription |
| Total Subscription | Overall IPO subscription demand |
| Listing Price | Actual stock market listing price |
| Listing Gain % | Percentage gain or loss on listing |

**Data Sources:** Historical IPO information was compiled using publicly available financial and IPO market information, including Chittorgarh, Moneycontrol, and other relevant sources.

GMP observations were considered using their recorded pre-listing dates to maintain the pre-listing prediction perspective.

## 4. Tools & Technologies

| Category | Tools |
|---|---|
| Data Analysis | Microsoft Excel |
| Database | MySQL / SQL |
| Programming | Python |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn, XGBoost |
| Business Intelligence | Power BI |
| Documentation & Version Control | Git, GitHub |

## 5. Project Workflow

### 5.1 Data Collection

- Collected historical Indian IPO information from publicly available sources.
- Compiled IPO issue prices, listing prices, GMP values, and subscription figures.
- Combined information from multiple sources into a structured dataset.
- Organized the dataset for further analysis and predictive modelling.

### 5.2 Data Cleaning & Preprocessing

- Identified and handled missing values.
- Standardized numerical and date-related columns.
- Corrected inconsistent data formats.
- Processed GMP and subscription-related variables.
- Created derived features, including Listing Gain Percentage.
- Prepared the dataset for exploratory analysis and machine learning.

### 5.3 Exploratory Data Analysis & Excel Analysis

Performed detailed exploratory analysis to understand relationships between IPO indicators and listing performance.

Key areas of analysis:

- GMP vs. Listing Gain.
- Total Subscription vs. Listing Gain.
- Retail, QIB, and NII subscription analysis.
- Distribution of positive, negative, and flat IPO listings.
- Year-wise IPO performance.
- IPO issue size vs. listing performance.
- Identification of top-performing and underperforming IPOs.

#### Key Analytical Focus: Combined Impact of GMP & Subscription Demand

One of the major objectives was to understand how GMP and subscription demand work together rather than evaluating them independently.

IPOs were classified into four categories:

| Category | GMP | Subscription Demand |
|---|---|---|
| 1 | Positive | High |
| 2 | Positive | Low |
| 3 | Negative | High |
| 4 | Negative | Low |

This comparison helps investigate:

- Whether high subscription demand can compensate for negative GMP.
- Whether positive GMP remains reliable when subscription demand is low.
- How different combinations of market sentiment and investor demand relate to actual listing gains.

This analysis provides a more comprehensive understanding of IPO performance than examining GMP or subscription figures individually.

## 6. Machine Learning & Predictive Modelling

Machine learning models were developed to predict IPO listing gains using pre-listing indicators and IPO-related features.

### 6.1 Models Implemented

- Linear Regression
- Decision Tree Regressor (Maximum Depth = 5)
- Random Forest Regressor
- XGBoost Regressor
- Tuned Random Forest Regressor

### 6.2 Model Evaluation Metrics

The following evaluation metrics were used:

- **MAE (Mean Absolute Error):** Measures the average absolute difference between actual and predicted listing gains.
- **MSE (Mean Squared Error):** Measures the average squared prediction error.
- **RMSE (Root Mean Squared Error):** Measures prediction error in the original target scale.
- **R² Score:** Measures the proportion of variation in listing gains explained by the model.

### 6.3 Model Performance

Models were evaluated using a held-out test set of **79 IPOs**.

| Model | MAE | MSE | RMSE | R² |
|---|---:|---:|---:|---:|
| Linear Regression | 18.43 | 795.67 | 28.21 | 0.30 |
| Decision Tree (Depth 5) | 19.43 | 868.76 | 29.47 | 0.23 |
| Random Forest | 17.28 | 715.96 | 26.76 | 0.37 |
| XGBoost | 19.12 | 873.73 | 29.56 | 0.23 |
| **Tuned Random Forest** | **16.99** | **700.78** | **26.47** | **0.38** |

### 6.4 Model Evaluation & Findings

- **Linear Regression:** Established a baseline model with an R² score of 0.30.
- **Decision Tree:** Recorded weaker performance than Linear Regression on the test dataset.
- **Random Forest:** Outperformed the other untuned models, achieving an MAE of 17.28 and an R² score of 0.37.
- **XGBoost:** Did not outperform Random Forest in the current experiment.
- **Tuned Random Forest:** Achieved the best overall performance, with the lowest MAE (16.99), lowest RMSE (26.47), and highest R² score (0.38).

**Final Model: Tuned Random Forest Regressor**

The tuned Random Forest was selected as the best-performing model on the evaluated notebook split.

The results indicate that the model captures some of the variation in IPO listing gains. However, the R² score also highlights that a substantial portion of listing performance remains unexplained by the available features.

## 7. Power BI Dashboard – IPO Listing Analysis

An interactive Power BI dashboard was developed to present the key findings and performance indicators of the Indian IPO market.

The dashboard provides an overview of IPO listing performance and allows users to explore trends using multiple filters.

### 7.1 Dashboard Overview

The dashboard contains the following key performance indicators:

| KPI | Value |
|---|---:|
| Total IPOs | 393 |
| Positive IPOs | 274 |
| Negative IPOs | 77 |
| Flat IPOs | 42 |
| Average Listing Gain | 19.38% |

### 7.2 Dashboard Visualizations

**1. IPO Listing Distribution**

- Distribution of positive, negative, and flat IPOs.
- 69.72% of IPOs recorded positive listing gains.
- 19.59% recorded negative listing performance.
- 10.69% recorded flat listing performance.

**2. Average Listing Gain by Year**

- Compares IPO activity and average listing gains across different years.
- Helps identify variations in IPO market performance over time.

**3. Profitable IPOs by Subscription Demand Category**

- Categorizes profitable IPOs into Very High, High, Moderate, and Low demand groups.
- Helps examine the distribution of profitable IPOs across subscription demand levels.

**4. IPO Issue Size vs. Listing Gain**

- Compares listing gain performance across Large, Very Large, Medium, and Small IPO categories.
- Helps explore the relationship between IPO size and listing performance.

**5. Top 5 IPOs by Listing Gain**

Identifies the five highest-performing IPOs based on listing gains.

**6. Bottom 5 IPOs by Listing Gain**

Highlights the five IPOs with the lowest listing performance, including significant listing losses.

**7. Impact of GMP and Subscription on IPO Performance**

This is one of the most important visualizations in the dashboard.

It compares four combinations of GMP and subscription demand:

- Negative GMP + High Subscription
- Positive GMP + High Subscription
- Positive GMP + Low Subscription
- Negative GMP + Low Subscription

The visualization compares average listing gain and IPO count across these categories to help understand the combined relationship between market sentiment, investor demand, and actual listing performance.

### 7.3 Interactive Filters

The dashboard includes slicers for:

- IPO Type
- Issue Size Type
- Subscription Demand
- IPO Year

These filters allow users to explore different segments of the IPO dataset and investigate performance patterns.

### 7.4 Dashboard Preview

![IPO Listing Analysis Dashboard](IPO/IPO%20dashboard%20.png)

## 8. Key Insights & Findings

Based on the exploratory analysis, dashboard, and machine learning experiments:

1. **Positive Listing Performance:** Out of 393 IPOs, 274 recorded positive listing gains, representing approximately 69.72% of the dataset.

2. **GMP as a Market Indicator:** GMP provides an indication of market sentiment but does not independently guarantee positive listing performance.

3. **Subscription Demand:** Higher subscription demand reflects stronger investor participation, but it should not be treated as a guaranteed indicator of listing gains.

4. **Combined GMP and Subscription Analysis:** Evaluating GMP and subscription demand together provides a more comprehensive perspective on IPO performance.

5. **Investor Categories:** QIB subscription showed a relatively strong relationship with listing gains in the analyzed dataset.

6. **Machine Learning Performance:** Tuned Random Forest achieved the best results among the evaluated models, with an MAE of 16.99 and R² of 0.38 on the held-out test set.

7. **Prediction Limitations:** IPO listing performance is influenced by several factors, and the available pre-listing indicators alone do not explain all variations in listing gains.

## 9. Limitations

- GMP is an unofficial market indicator and may not accurately reflect actual listing performance.
- Historical trends may not remain consistent under changing market conditions.
- Missing or inconsistent historical information may affect analytical outcomes.
- IPO listing gains are influenced by external market conditions and other factors not fully represented in the dataset.
- The machine learning models have limited predictive performance and should not be considered reliable investment decision-making tools without further validation.

## 10. Future Scope

- Incorporate broader market indicators and market sentiment.
- Include additional features such as sector, issue size, and overall market conditions.
- Experiment with advanced machine learning algorithms.
- Explore improved feature engineering and hyperparameter optimization.
- Apply additional validation techniques to evaluate model generalization.
- Enhance the Power BI dashboard with more detailed comparative and time-based analysis.

## 11. Project Structure

```text
IPO-Listing-Gain-Prediction/
│
├── Dataset/
│   └── IPO_Dataset.xlsx
│
├── Excel_Analysis/
│   └── IPO_Analysis.xlsx
│
├── Machine_Learning/
│   └── IPO_Prediction.ipynb
│
├── PowerBI_Dashboard/
│   ├── IPO_Dashboard.pbix
│   └── IPO_Dashboard.png
│
├── Project_Report/
│   └── IPO_Project_Report.pdf
│
└── README.md
```

## 12. Conclusion

This project provides an end-to-end analytical approach to understanding Indian IPO listing performance.

By combining historical IPO data, Excel-based analysis, SQL, machine learning, and Power BI, the project explores how GMP and subscription demand relate to actual listing gains.

A key focus of the analysis is the combined impact of GMP and subscription demand, demonstrating why multiple indicators should be considered when evaluating IPO performance.

The machine learning experiments further demonstrate the challenges of predicting listing gains using historical pre-listing information.

Overall, the project strengthened practical understanding of data collection, preprocessing, exploratory data analysis, business intelligence, predictive modelling, and communicating data-driven insights.

## 13. Author

**Khushi Baliyan**

B.Tech – Computer Science & Engineering

Interested in Data Analytics, Business Intelligence, and Machine Learning.

---

**Disclaimer:** This project is developed for academic and analytical purposes only. It does not constitute financial or investment advice and should not be used as the sole basis for IPO investment decisions.
