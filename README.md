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
x = rnorm(100)
y_x = y-x
test = t.test(y_x)
t.test(y_x)
test[7]
summary(lm(y_x~1))
cohen_d_hand = mean(y_x) / sd(y_x)
cohen_d_hand
y_x_cohen = data.frame(y,x)
y_x_cohen
y_x_cohen =stack(y_x_cohen, select = c("y", "x"))
y_x_cohen
cohen.d(y_x_cohen$values, y_x_cohen$ind)
```

