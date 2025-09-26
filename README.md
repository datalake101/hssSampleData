###install the necessary libraries
install.packages('pacman', 'dplyr', 'ggplot2', 'rio')
library(rio)
library(dplyr)
library(ggplot2)

###import the data:
df = import('https://raw.githubusercontent.com/datalake101/hssSampleData/refs/heads/main/healthData.csv')

######## Example of t-test:
#Code
t.test(bmi ~ owns_home, df)

#Output: 
data:  bmi by owns_home
t = -0.054302, df = 4002.2, p-value = 0.9567
alternative hypothesis: true difference in means between group No and group Yes is not equal to 0
95 percent confidence interval:
 -0.4411428  0.4173646
sample estimates:
 mean in group No mean in group Yes 
         29.05364          29.06553


######## example of ANOVA ########

> aov(systolic_bp ~ marital_status, data = df)
Call:
   aov(formula = systolic_bp ~ marital_status, data = df)

Terms:
                marital_status Residuals
Sum of Squares           710.1  968427.7
Deg. of Freedom              4      4995

Residual standard error: 13.92406
Estimated effects may be unbalanced


###### example of chi-sq test  ########
> chisq.test(table(df$reddit_active, df$sex))

data:  table(df$reddit_active, df$sex)
X-squared = 0.022421, df = 2, p-value = 0.9889




         
