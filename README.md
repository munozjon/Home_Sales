# Home_Sales

## Module 22 Challenge

For this challenge, I leveraged my skills with PySpark and SparkSQL to determine key metrics about home sales data. I was able to create temporary views, query the data via SQL statements, cache my table, and partition with parquet data.

I compared the runtimes for a specific query across three different instances:

- __Query: What is the average price of a home per "view" rating having an average home price greater than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.__
- First instance: I ran the query with the temporary view of the DataFrame and returned a runtime of 0.129 seconds.
- Second instance: I ran the query after caching the temporary table, this time with a 0.100 runtime.
- Third instance: I reran the query after partitioning the data with the *date_built* field, and then formatted the table with parquet. After reading the parquet data and creating another temporary table, the query returned a runtime of 0.091 seconds.

Overall, while the difference were very minor, the caching and partitioning of the data did result in faster runtimes. This will be especially important when running datasets with much larger sizes and queries that return more rows of data.