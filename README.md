# Home_Sales

In the **Home Sales** challenge (Module 22), I used **SparkSQL** to determine key metrics of given home sales data.  I created temporary views, partitioned data, cached and uncached a temporary table, and then verified the final cache state as ‘uncached’.
The programming was done on a **Google Colab** platform.  The analysis data was imported directly via the URL below:
https://2u-data-curriculum-team.s3.amazonaws.com/dataviz-classroom/v1.2/22-big-data/home_sales_revised.csv

The following information was programmatically determined, as can be seen in the output section of Colab platform’s programming cells:

•	The average price of a 4-bedroom house sold for each year.

•	The average home price, for each year built, with 3 bedrooms and 3 bathrooms.

•	The average home price for each year with 3 bedrooms, 3 bathrooms, 2 floors, and greater than or equal to 2,000 square feet.

•	The view rating of homes that cost more than or equal to 350,000—and the run-time for the query.


### Observational Highlights & Knowledge Gained: ###

•	The data was retrieved from an AWS S3 bucket.

•	An **AWS S3** ‘bucket’ is a storage space provided by **Amazon Simple Storage Service** (**Amazon S3**).  Amazon S3 is utilized for not only data storage, but also data protection.  As well, it provides management features that optimize, organize, and configure data access.  In the era of ‘Big Data’, such services are indispensable.

•	PySpark is very similar to traditional Python.  One ubiquitous example would be with the display function ‘head()’ in Python.  In PySpark, this function is ‘show()’.

•	PySpark combined with Spark SQL makes for clean and efficient data querying.

•	The PySpark partition is a way to split a large dataset into smaller datasets based on one or more partition keys.

•	Partitioning reduces the amount of data that needs to be processed, and therefore improves query performance.

•	Performance is often assessed/measured in terms of runtime (i.e., the time a query, or any programmatic operation, takes to run).

•	Parquet partitioning is the dividing of data into smaller chunks based on specific criteria – such as date, time, or certain values in a column.

•	The performance results of processing our home sales data is as follows:

o	Run time of Spark SQL query  1.028 seconds

o	Run time of Spark SQL query on cached table   0.44 seconds

o	Run time utilizing parquet partitioning  0.73 seconds


•	As expected, the performance significantly improved when running Spark SQL on a cached table – from **1.028 seconds** on the non-cached, to less than half that (**0.44 seconds**) on the cached.

•	I would expect this improvement to continue when utilizing parquet partitioning, and yet in our case, this did not happen. Note, the methodologies are used to optimize ‘Big Data’, and prove successful with dataset magnitudes of this kind.  Our dataset is not large enough to be classified as such, and thus our results fluctuate from what would otherwise be the expected consistent trend.
