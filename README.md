# Pagerank with GraphX
Page rank implemented with CSV plugin and GraphX,it read the data from csv, and once the pagrank read converge it writes the result into file 

The code support the csv look like
```
uid,retweeted_uid
abc,efg
efg,yjk
yjk,abc
```

to build, use
```
sbt package
```
it generates a jar called test_2.10-1.0.jar

## Execution
to run, use
```
./spark-submit --class "Test" --packages com.databricks:spark-csv_2.10:1.3.0  ~/test_2.10-1.0.jar {0} {1} {2}
```
* {0} is csv file input
* {1} is coverge value
* {2} is data output path

So it may look like
```
./spark-submit --class "Test" --packages com.databricks:spark-csv_2.10:1.3.0  ~/test_2.10-1.0.jar ~/data.csv 0.01 /home/user/pagerank_graphx_result.txt
```
