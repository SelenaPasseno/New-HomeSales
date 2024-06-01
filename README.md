# New-HomeSales


Answer the following questions using SparkSQL:
1) The average price for a four-bedroom house sold for each year? Rounded off to two decimal places.
+----------+-------------+
|date_built|Average_Price|
+----------+-------------+
|      2010|    296800.75|
|      2011|     302141.9|
|      2012|    298233.42|
|      2013|    299999.39|
|      2014|    299073.89|
|      2015|    307908.86|
|      2016|    296050.24|
|      2017|    296576.69


2) What is the average price of a home for each year the home was built, that has three bedrooms and three bathrooms? Round off your answer to two decimal places.
+----------+-------------+
|date_built|Average_Price|
+----------+-------------+
|      2010|    292859.62|
|      2011|    291117.47|
|      2012|    293683.19|
|      2013|    295962.27|
|      2014|    290852.27|
|      2015|     288770.3|
|      2016|    290555.07|
|      2017|    292676.79

3) What is the average price of a home for each year the home was built, that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

+----------+-------------+
|date_built|Average_Price|
+----------+-------------+
|      2010|    285010.22|
|      2011|    276553.81|
|      2012|    307539.97|
|      2013|    303676.79|
|      2014|    298264.72|
|      2015|    297609.97|
|      2016|     293965.1|
|      2017|    280317.58|

4) What is the average price of a home per "view" rating having an average home price greater than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

+----+-------------+
|view|Average_Price|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38

Cached the temporary table home_sales and Checked if the temporary table is cached.
Using the cached data, run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.
+----+-------------+
|view|Average_Price|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.38
--- 1.2283167839050293 seconds ---
Partition by the "date_built" field on the formatted parquet home sales data.
Create a temporary table for the parquet data.

Run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.
|view|Average_Price|
+----+-------------+
|  99|   1061201.42|
|  98|   1053739.33|
|  97|   1129040.15|
|  96|   1017815.92|
|  95|    1054325.6|
|  94|    1033536.2|
|  93|   1026006.06|
|  92|    970402.55|
|  91|   1137372.73|
|  90|   1062654.16|
|  89|   1107839.15|
|  88|   1031719.35|
|  87|    1072285.2|
|  86|   1070444.25|
|  85|   1056336.74|
|  84|   1117233.13|
|  83|   1033965.93|
|  82|    1063498.0|
|  81|   1053472.79|
|  80|    991767.3

--- 0.6854479312896729 seconds 

The particioned data ran almost twice as fast


Requirements
A Spark DataFrame is created from the dataset. (5 points)
A temporary table of the original DataFrame is created. (10 points)
A query is written that returns the average price, rounded to two decimal places, for a four-bedroom house that was sold in each year. (5 points)
A query is written that returns the average price, rounded to two decimal places, of a home that has three bedrooms and three bathrooms for each year the home was built. (5 points)
A query is written that returns the average price of a home with three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet for each year the home was built rounded to two decimal places. (5 points)
A query is written that returns the average price of a home per "view" rating having an average home price greater than or equal to $350,000, rounded to two decimal places. (The output shows the run time for this query.) (10 points)
A cache of the temporary "home_sales" table is created and validated. (10 points)
The query from step 6 is run on the cached temporary table, and the run time is computed. (10 points)
A partition of the home sales dataset by the "date_built" field is created, and the formatted parquet data is read. (10 points)
A temporary table of the parquet data is created. (10 points)
The query from step 6 is run on the parquet temporary table, and the run time is computed. (10 points)
The "home_sales" temporary table is uncached and verified. (10 points)
