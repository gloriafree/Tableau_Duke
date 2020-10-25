# Tableau calculation types

calculations are embeded in calculation fields

calculation types
1. row level calculations
2. aggregated calculations
3. table level calculations (complex)


creating a CALCULATED field to flagging whether to view certain state or not, is similar as using GROUPING function and apply it to the state field.

we can make calculations with calculated fields in Tableau

# Blending price parity data with our salary data
Tableau does it by keeping higher level table the main table, and append the aggregated measures from more granular table to main table.


# ATTR() - [aggregation function for data blending](https://kb.tableau.com/articles/howto/when-to-use-the-attribute-attr-function)

* How it works:
ATTR() compares all of the values from each record in the underlying data that grouped into certain level, and if all values are the same then return that value, otherwise it returns an asterisk.

* detailed formula:
```
IF MIN ([dimension]) = MAX ([dimension]) THEN MIN ([dimension]) ELSE "*"  END
```
* When to use it:
when blending two data sources, fields from the other source are automatically wrapped in ATTR() based on the levels of matching key, if the value in each of the levels are the same.


# Overlay two measurements for same categories
1. re-position the 2nd measure from row shelf to y-axis, so that we have double measures shared on the same x-axis, instead of two separate charts
2. put measure name (two measures in this case) on both size and color to distinguish between the two measures

*Question: what if our matching key are messy and not completely matched?*


#RANK() function that can rank measures within nested groups/levels
1. choose measurement and apply the rank function
2. convert this rank function into discrete instead of continuous so we can apply it to the column
3. change the formatting of rank header and column divider so it looks nicer and cleaner

#add parameter variable to go with rankings
1. create parameter to hold the rank value which can be customized later
2. add calculated field (in top x?) to do logic operation on whether the rank is large than the parameter
3. add the 'in top x?' into marks card, make sure its table calculation is configured on the correct data blending level (if data only comes from one data source, then this step can be ignored)
4. apply the 'in top x?' into filter and put parameter into the board so we can use

# Designing a dashboard to determine where you should work
1. use dashboard container to automatically position different charts
2. link different charts together with the same filter
3. link different charts together using themselves
dashboard -> actions -> add action -> filter/highlight/URL -> set up source sheets, how to run action on, and the target sheets


#tableau trick: Extract mode
if work with large data, we can switch to Extract mode, which is using [columnar store](https://www.tableau.com/about/blog/2014/7/understanding-tableau-data-extracts-part1) for data and so it makes it possible to quickly operate on values for certain columns.
Basically by re-structing how data are loaded into memory and used by Tableau, it improves the processing time.

more operations on working with extract is saved [here](https://help.tableau.com/current/pro/desktop/en-us/extracting_data.htm).


#lesson learned
the function/feature of different version of tableau could be very different, so one solution in certain version might not work exactly the same as the other.
so don't simply just apply the same solutions or steps, but try to adjust it according to the version you are currently working on.
