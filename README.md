# pymaceuticals_capomulin_study
 Pymaceuticals - Capomulin Study - 249 Mice with SCC Tumors - 45 Day Study - Tumor Size Comparison

While cleaning the data, I assumed I was working with a much larger dataset.
The data was checked to ensure each ["Mouse ID", "Timepoint"] combination was unique in the dataset.
When dealing with large studies, data is sometimes entered twice. So instead of excluding all ["Mouse ID"] data which the ["Mouse ID", "Timepoint"] combinations are not unique, there should be another check.

Assumption: If there is data with the same ["Mouse ID", "Timepoint"] combination, the data could be included in the dataset 
    if: Every instance of a duplicate ["Mouse ID", "Timepoint"] combination for a single ["Mouse ID"] are exactly the same - (Assumed the data is correct just entered multiple times)
    else: the data for ["Mouse ID", "Timepoint"] combinations differ - (["Mouse ID"] exculed from entire dataset)

Test:
If: The mean of all the duplicate ["Mouse ID", "Timepoint"] = any one of the ["Mouse ID", "Timepoint"] data points -> all duplicate ["Mouse ID", "Timepoint"] are equal
    ["Mouse ID", "Timepoint"] duplicates can be deleted and the ["Mouse ID"] can be included in the dataset.
else: ["Mouse ID"] is fully exculeded from the dataset