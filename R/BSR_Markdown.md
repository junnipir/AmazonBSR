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
plot(my_data)
```

```
#Data will then need to be transformed into date format as sometimes the dates pull through as Character. This all depends on the type of data you're inputting. The functions used in this package require POSIXct class.  
class(my_data)
as.Date(my_data)



#Then you will need to use the following functions.

#The Totalmean function removes any NA datapoints so you can find the total combined mean for a data column. This is useful for comparing parsed data to the overall dataset. 
``` {r}
Totalmean<- function(df){
  Totalmean<- mean(df, na.rm= TRUE)
  return(Totalmean)
}
```

#This function helps with joining created vectors to the dataframe. I found that I was joining vectors frequently while analyzing the data, so I made a function to save me some time. 

```{r}
join<- function(df,vect){
  new.df<-cbind(df, vect)
  return(new.df)
}
```

#This function allows me to compare two different datapoints to the BSR.
```{r}
plot_BSR<- function(my_data){
  ggplot()+
    geom_line(data= my_data, mapping=aes(x=date, y=BSR_rank ), color="blue")+
    geom_point(data= my_data, mapping=aes(x=date, y=BSR_rank ), color="blue")+
    geom_line(data= my_data, mapping=aes(x=date, y=units_sold ), color="orange")+
    geom_point(data= my_data, mapping=aes(x=date, y=units_sold ), color="orange")

}
```


#The End





