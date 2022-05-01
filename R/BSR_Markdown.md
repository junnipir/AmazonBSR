---
title: "Comparing Amazon Product’s BSR and Category Rank to Number of Sales Per Day"
author: "Heather Ward"
date: "4/10/2022"
output: "html_document"

---

```{r setup, include=FALSE}
data.table(echo=TRUE),
dplyr(echo=TRUE),
ggplot2(echo=TRUE),
lattice(echo=TRUE),
lubridate(echo=TRUE),
plyr(echo=TRUE),
tidyverse(echo=TRUE)
```

#These quick functions will be used to get to know the data and see what data we have to work with. Please know that "my_data" will be used to represent the dataset that will be loaded into R.
str(my_data)
summary(my_data)
plot(amazondata)
```
#Data will then need to be transformed into date format



#figures that will help in analyses. 
#
``` {r}
hist($amazondata$salesperday)
boxplot($amazondata$categoryrank)
```



#The End





