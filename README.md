---
title: '6060 Lab Quiz 2: RMarkdown'
author: "Jordan Ho"
output:
  pdf_document:
    number_sections: yes
    toc_depth: 3
  html_document:
    toc_depth: '3'
  word_document:
    toc_depth: '3'
---

```{r,echo=FALSE,message=FALSE, warning=FALSE}
# Code goes in blocks like this

# load libraries
library(tidyverse)
library(apaTables)

#Load data 
bfi_data <- psych::bfi

```

# Relations between variables for all participants (men and women)

Below are the correlations among the variables for all participants (men and women).

```{r, echo=FALSE, message=FALSE, warning=FALSE}
apa.cor.table(analytic_data_excluding_gender,filename="Table1.doc",table.number = 1)  
```

\pagebreak

# Relations between variables for just men over the age of 40


Below we can see the same correlation table again but based just on men over the age of 40.
```{r,echo=FALSE,message=FALSE, warning=FALSE}
apa.cor.table(analytic_data_men_over_age_40,filename="Table2.doc",table.number = 2)
```

\pagebreak

# Scatter plot of the relation between agreeableness and extraversion for men over the age of 40

Below we can see the scatter plot of the relation between agreeableness and extraversion for men over the age of 40.


```{r, echo=FALSE, message=FALSE, warning=FALSE}
my.plot <- qplot(agreeableness, extraversion, data = analytic_data_men_over_age_40)
my.plot <- my.plot + theme_classic(14)
my.plot <- my.plot + theme(axis.line.x = element_line(colour = 'black', size=0.5, linetype='solid'),axis.line.y = element_line(colour = 'black', size=0.5, linetype = 'solid'))
my.plot <- my.plot + labs(title="Men over the age of 40", x="agreeableness", y="extraversion")
print(my.plot)
```

