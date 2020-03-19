---
title: "Test"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

Test t.test and lm
```{r}
y = rnorm(100)
t.test(y)
summary(lm(y~1))
```

