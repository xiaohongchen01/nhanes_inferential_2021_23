# NHANES 2021-2023 Inferential Analytics

This project uses publicly available data from the NHANES 2021-2023 to perform basic inferential statistical analyses. Using the XPT files, I cleaned, recoded and merged multiple XPT files and applied inferential tests. 

## Data Preparation
The XPT files were merged using the unique respondent identifier (SEQN). Continuous variables were cleaned by removing placeholder values (7777, 9999) and converting them to NaN. Categorical variables were recoded into meaningful labels, such as married vs not married. 


### Question 1: Is there an association between marital status and education level?
Test Used: Chi-square

Interpretation: 
```
Chi-square statistic: 129.17381826322236
p-value: 6.213197986632679e-30
```
The p-value is less than 0.05, indicating a statistically significant association between marital status and education level. Married individuals are more likely to have a bachelor’s degree or higher, while those who are not married are more likely to have less than a bachelor’s degree.


### Question 2: Is there a difference in mean sedentary behavior time between those who are married and those who are not married?
Test Used: Independent-sample T-test

Interpretation:
```
T-statistic: -3.8699896847970154
P-value 0.00010973792037934772
Married mean: 353.28714076960546
Not married mean: 371.95753538717736
```
A p-value less than 0.05 indicates a statistically significant difference. Individuals who are married have lower sedentary behavior time compared to those who are not married.

### Question 3: How do age and marital status affect systolic blood pressure?
Test Used: Linear Regression

Interpretation:
```
p-values: age <0.001, martial = 0.003
coefficients: age =+ 0.3952, not married =+1.3420
```
As the population ages, systolic blood pressure increases. Being married or not married does not appear to play a major role in systolic blood pressure. There may be a slight increase in systolic pressure among unmarried individuals compared to those who are married. 


### Question 4: Is there a correlation between self-reported weight and minutes of sedentary behavior?

Test Used: Pearson correlation

Interpretation: 
```
Correlation (r): 0.1559714584645022
p-value: 1.6988498386823033e-44
```
A Pearson correlation was conducted to examine the relationship between self-reported weight and sedentary behavior. Results show a weak positive correlation between the two columns. The correlation strength (r = 0.15597) indicates a weak positive relationship. The p-value shows that the correlation is unlikely to be due to random chance.

### Question 5: Is there a difference in mean sedentary behavior time across vitamin D interpretation levels and weak/failing kidney status?

Test used: Two-Way ANOVA

Interpretation: 
```
                             sum_sq      df         F    PR(>F)
C(LBDVD2LC)            1.406932e+05     1.0  3.238234  0.071992
C(KIQ022)              7.987817e+04     1.0  1.838498  0.175182
C(LBDVD2LC):C(KIQ022)  1.755563e+04     1.0  0.404065  0.525024
Residual               2.408296e+08  5543.0       NaN       NaN
```

The bar plot shows that mean sedentary minutes are similar across both vitamin D interpretation levels and kidney status groups, with only small differences between the bars.

The p-values (PR(>F)) were all above 0.05, indicating that the results were not significant.

The visual pattern shows no significant main effects or interaction between vitamin D status and weak/failing kidneys on sedentary behavior.

The chart shows that people with weak/failing kidneys had slightly more sedentary minutes than those who have never been told. People with low vitamin D also had slightly fewer mean sedentary minutes compared to those with normal vitamin D results. Although it appears this way visually, the differences are minimal.







