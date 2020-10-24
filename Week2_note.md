# Understand the Marks Card

Purpose of marks card:
1. set up data source of 'area' type of chart (eg. pie or bubble chart)
2. set up any format such as underline data in tooltip, labels, colors, size of areas,  

# removing outliers using scatterplot and filtering and groups

1. remove outlier by applying filter
filtering allows you to change the data universe in the calculated field
*check: you can check #records universe in the '# marks' below*

2. group outliers into its own group
this is to grouping numeric variables, we can set up threshold or simply using GUI to select the outlier data points
*tableau can only use information that's in the workspace, and so we need to add row identifier into the 'Detail' marks card to reference the particular data point, in order to use that data point*
*data identifier needs to be able to separate every single row that's in the data*

# analyzing data-related salaries in different states using filter and groups
* grouping Others
this is to further group categorical variables using Tableau's group function. And one very handy feature is to activate 'Include 'Other' option, this allows to group everything else that are not defined by your grouping into 'Others' immediately.

# when to use line graphs
* date variable:
tableau can treat date as continuous variable as well as categorical variables.
* intelligent hierarchy:
tableau tends to automatically create hierarchy for some dimensional variable (geo location or date), but it might not always does a correct job. and so we can remove that hierarchy groups ourselves.
* self-made hierarchy:
in the dimensions panel, drag the sub-group variable under group variable
* self-define date:
right clicking



# analyzing data related salaries over time using date hierarchy
measure variable: for continuous variables, we can switch the aggregated form or scatter form using the aggregate option: go to Analysis -> aggregate measure

*I really like the way Dr. Jana describes statistics concepts as those descriptions are easy to interpret and to the point*
1. CI for regression line: how reliable the regression line it is, and how much we should trust these lines.
2. P-value: its usage is for us to tell how likely the measure is due to chance or is indeed reliable. The specific value you use represents what highest of positive rate your test could have.
