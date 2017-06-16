# Bitcoin_Blockchain_network_analysis
Finding out fraudulent activities and actors in the Bitcoin transaction network

Bitcoin blockchain is publically available. A node had to be created to get ~90GB of data. However, this data is not analyzable directly and has to be parsed first. 

Using this Parser: https://github.com/bitcoin-abe/bitcoin-abe, Bitcoin block files are read, transformed and loaded into a database.

After the data is loaded into MySQL database, it occupies ~350GB on disk. Therefore, AWS pipeline is created to process and analyze Big data. 

Tables are created in S3 bucket as Hive tables and data is extracted and filtered using HiveSQL.

Dataframe is created at address level and important features are created on PySpark. Some of the features are obtained from graph property of the network using Scala GraphX.

Then, with all the features and labelled dataset, Logistic Regression model is then trained and validated using SparkML on PySpark.

Intermediate results are stored in S3 bucket
