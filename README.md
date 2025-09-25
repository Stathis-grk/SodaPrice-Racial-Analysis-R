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




<img width="641" height="432" alt="image" src="https://github.com/user-attachments/assets/a34371d0-d511-46e0-8300-8c4a1b0e3208" />



## Log-Log Model 
log(psoda) = β₀ + β₁prpblck + β₂log(income) + u

1% increase in Black population → 0.12043% increase in soda price

1% increase in income → 0.07535% increase in soda price

R-squared: 0.06723

Preferred model based on lower AIC





<img width="662" height="501" alt="image" src="https://github.com/user-attachments/assets/19ef6365-5459-4b24-936f-23b16173b284" />





## log-log model with poverty rate
log(psoda) = β₀ + β₁prpblck + β₂log(income) + β3(prppov) + u

Black population → 0.07267% decrease in soda price 

R-squared: 0.08517 → it got increased 




<img width="713" height="447" alt="image" src="https://github.com/user-attachments/assets/0cb4673c-d410-4e00-b018-5b6fe2cb89c7" />






## Correlation Analysis 
log(income) and prppov show high negative correlation (-0.838)

As expected: higher income generally associates with lower poverty



<img width="390" height="38" alt="image" src="https://github.com/user-attachments/assets/f4e97ea1-fa4b-460c-a683-e662b3ec66e5" />




## Multicollinearity Check 
Despite high correlation between log(income) and prppov:

VIF values < 10 indicate no severe multicollinearity



<img width="392" height="60" alt="Στιγμιότυπο οθόνης 2025-09-25 100709" src="https://github.com/user-attachments/assets/351af369-ddec-4861-a4c0-5243064a4a1e" />





## Final Model Selection 
The most reliable model is the extended log-log model with poverty rate (ols3) because:

Lowest AIC among alternatives

prpblck coefficient remains positive and significant

Suggests racial composition affects fast food pricing



<img width="325" height="81" alt="image" src="https://github.com/user-attachments/assets/b6500132-d1e5-413d-ba13-c1b19f89a84f" />



## Assumption Validation 
Tests performed:
### Normality of residuals: Jarque-Bera test indicates issues
### Multicollinearity: VIF shows no problems
### Autocorrelation: Durbin-Watson test shows no issues
### Heteroskedasticity: White test shows no problems



<img width="634" height="438" alt="Στιγμιότυπο οθόνης 2025-09-25 101527" src="https://github.com/user-attachments/assets/e7066e71-90de-4ad8-a8b2-6d3435a0467d" />




<img width="693" height="404" alt="Στιγμιότυπο οθόνης 2025-09-25 101712" src="https://github.com/user-attachments/assets/fee4d882-d727-44ef-8058-f1ffb8364611" />




# Interpretation
The analysis consistently shows that areas with higher Black populations tend to have higher fast food soda prices, even after controlling for income and poverty levels. This may indicate:

Economic exploitation by fast food chains

Different consumption patterns

Market dynamics in predominantly Black neighborhoods

The most robust model (log-log with poverty rate) suggests that a 1% increase in Black population is associated with approximately 0.12% higher soda prices, holding other factors constant.
