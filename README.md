---
title: "Test"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

Test t.test and lm, and cohen's for one sample same as standarded effect
https://ncss-wpengine.netdna-ssl.com/wp-content/themes/ncss/pdf/Procedures/PASS/One-Sample_T-Tests_using_Effect_Size.pdf
```{r}
y = rnorm(100)
test = t.test(y)
t.test(y)
test[7]
summary(lm(y~1))
cohen.d(y)
```

