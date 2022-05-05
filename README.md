# Data-Summary-and-Visualization-example-in-R
This is a brief introductory example of data analysis in R using one of the well-known built-in data sets. 

#I would personally use data.table as it is more convenient. Some example codes would be:

dt[, treatment_f:= as.factor(treatment)]
dt[,table(treatment_f)]
dt1[, New_State:= ifelse(state== "NY", 0,1)]
na.omit(dt1, cols=c("first.column", "second.colum"))

mod_2= lm(Y~relevel(treatment_f, ref = "Placebo"), data=dt)
modelsummary(mod_2, statistic = c('std.error' , 'p.value'))
