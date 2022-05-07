---
title: "index"
author: "Elamathi Elangovan"
date: "06/05/2022"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# Exploring the correlation between parental education level and the education level of their children.

### Elamathi Elangovan
### May 2022

## Research Question: 

Does higher parental education levels correlate to a higher level of education in their offspring?

## Data origins: 

This data is taken from the 2014 General Society Survey (GSS) Merged Single-Year Data Set. It includes variables on topics such as marital status, labor force status, number of hours worked, occupational prestige, divorce status, level of education and similar data for their mothers and fathers. The following considers this dataset and looks at educational correlates, exploring whether there is a relationship between parental education and that of the respondents. 

The data used was provided as a zip file link from https://gss.norc.org/get-the-data/spss provided in tomstafford.github.io 

## Data preparations:

Fortunately, the data was fairly clear, with the required columns appearing next to one another. 

## Visualisation:

I chose to plot scatter plots as they most easily show the relationships between two variables. In this case I sought to observe if paternal and maternal education level separately would depict a relationship with the respondent's education level

#Load in the data 
library(haven)
df <- read_sav("//studata05/home/PC/Pcp21ed/ManW10/Desktop/gss2014merged_r10 - spss.sav")
library(ggplot2)

library(tidyr)


#Using ggplot to create a graph plotting respondent's education level against maternal education level and assigning it to variable p
p <- ggplot(data = df, mapping = aes(x = educ, y = maeduc))

#Plotting a scatterplot and labelling x and y axis
p + geom_point() + geom_smooth() + labs(x = "respondent education level",
                          y = "maternal education level", 
                      title = "The relationship between maternal education and respondents education")

#Using ggplot to create a graph plotting respondent's education level against paternal education level and assigning it to variable q
q <- ggplot(df, aes(x = educ, y = paeduc))

#Plotting a scatterplot and labelling x and y axis
q + geom_point() + geom_smooth() + labs(x = "respondent education level",
                                        y = "paternal education level", 
                                        title = "The relationship between paternal education and respondents education")

![Scatter plot depicting a weak nonlinear postive relationship between maternal education and respondents education](/images/maeduc_vs_educ.png "The relationship between maternal education and respondents education")

![Scatter plot depicting a weak nonlinear postive relationship between paternal education and respondents education](/images/paeduc_vs_educ.png "The relationship between paternal education and respondents education")
```


 
In comparing maternal education level with that of the respondent,  it can be deduced that there is a positive, nonlinear association between the two variables, albeit weak, and the same was seen when paternal education level was compared with the respondent's education level. This suggests a weak positive relationship between parental education level and that of the respondent, where the higher the education level of the parent, the higher the education level of their child. 

Summary:

In future projects, it would be interesting to compare the two plots to determine whether maternal or paternal education level have a stronger relationship with that of the respondent. It would also be interesting to compare parental education level to their occupational prestige, as well as occupation prestige to the respondent's education level to further explore factors influencing and involved with education.