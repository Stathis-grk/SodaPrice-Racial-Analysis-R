# SodaPrice-Racial-Analysis
Analysis of fast food pricing and racial demographics using R.

This R project analyzes whether fast food restaurants charge higher prices for soft drinks in ZIP code areas with a higher percentage of Black residents, using data from New Jersey and Pennsylvania. It includes regression modeling, diagnostic testing, and interpretation of socioeconomic effects on pricing.

## Key Findings
Descriptive Statistics 
prpblck (proportion Black):

Mean: 0.113 (11.3%)

Standard deviation: 0.182

Unit: Percentage (%)

income:

Mean: $47,053.78

Standard deviation: $13,163.16

Unit: Dollars ($)


![Στιγμιότυπο οθόνης 2025-07-03 123533](https://github.com/user-attachments/assets/9ca914cc-043b-42ba-beff-f30508f6667a)


## Regression Analysis
Basic Model 
psoda = β₀ + β₁prpblck + β₂income + u

A $1 increase in income is associated with a $0.000001579 increase in soda price

R-squared: 0.06352

Sample size: 410 observations

p-value: 1.586e-06 (statistically significant)
![image](https://github.com/user-attachments/assets/e9a8f15a-22e6-4e1a-9d2a-4b80e8924098)
![image](https://github.com/user-attachments/assets/6cec927e-a655-4a5c-92dd-8d7d0b3ba2de)

## Log-Log Model 
log(psoda) = β₀ + β₁prpblck + β₂log(income) + u

1% increase in Black population → 0.12043% increase in soda price

1% increase in income → 0.07535% increase in soda price

R-squared: 0.06723

Preferred model based on lower AIC
![image](https://github.com/user-attachments/assets/e791f3e5-6791-4fb3-89aa-0c37b505bf4b)
![image](https://github.com/user-attachments/assets/a305c8ee-e60c-485b-8ff5-2bb5eae7e8ec)

## Correlation Analysis 
log(income) and prppov show high negative correlation (-0.838)

As expected: higher income generally associates with lower poverty
![image](https://github.com/user-attachments/assets/4fd06d22-1ef5-4178-9b8e-8060f2f59284)

## Multicollinearity Check 
Despite high correlation between log(income) and prppov:

VIF values < 10 indicate no severe multicollinearity
![image](https://github.com/user-attachments/assets/6574422f-4006-4c6f-90c2-d43db01a786b)

## Final Model Selection 
The most reliable model is the extended log-log model with poverty rate (ols3) because:

Lowest AIC among alternatives

prpblck coefficient remains positive and significant

Suggests racial composition affects fast food pricing
![image](https://github.com/user-attachments/assets/7db81a84-5b7c-4c22-a98a-b9aa7fc28909)

## Assumption Validation 
Tests performed:
Normality of residuals: Jarque-Bera test indicates issues
Multicollinearity: VIF shows no problems
Autocorrelation: Durbin-Watson test shows no issues
Heteroskedasticity: White test shows no problems
![image](https://github.com/user-attachments/assets/dd470f32-c68d-444e-a362-be6112fd1106)
![image](https://github.com/user-attachments/assets/4051d812-e28f-4ca6-aafe-02a8d6e3dbb3)
![image](https://github.com/user-attachments/assets/1855f7f6-8e7c-43d6-928e-a0d5b937492c)

# Interpretation
The analysis consistently shows that areas with higher Black populations tend to have higher fast food soda prices, even after controlling for income and poverty levels. This may indicate:

Economic exploitation by fast food chains

Different consumption patterns

Market dynamics in predominantly Black neighborhoods

The most robust model (log-log with poverty rate) suggests that a 1% increase in Black population is associated with approximately 0.12% higher soda prices, holding other factors constant.
