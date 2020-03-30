---
title: "Test"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

Test t.test and lm, and cohen's for one sample same as standarded effect
https://ncss-wpengine.netdna-ssl.com/wp-content/themes/ncss/pdf/Procedures/PASS/One-Sample_T-Tests_using_Effect_Size.pdf
Cohen 1988
```{r}

#equal
y = rnorm(100)
x = rnorm(100)
y_x = y-x
test = t.test(y_x)
t.test(y_x)
test[7]
summary(lm(y_x~1))
#equal diff score and paired
t.test(y,x, paired= TRUE)


cohen_d_hand = mean(y_x) / sd(y_x)
cohen_d_hand
cohen_d_hand


## Different formula for cohen's D but still legit
y_x_cohen = data.frame(y,x)
y_x_cohen
y_x_cohen =stack(y_x_cohen, select = c("y", "x"))
y_x_cohen
cohen.d(y_x_cohen$values, y_x_cohen$ind)
test_stan = stan_glm(y~ x)
summary(test_stan)
test_stan$stan_summary
test_lm = summary(lm(y ~x))
confint(lm(y ~x))
```

