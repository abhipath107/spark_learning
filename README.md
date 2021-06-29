

### PySpark program for wordcount

```py
$ pyspark

words = sc.textFile('/Users/abhishekpathak/Code/spark_learning/assets/word_count_input.txt').flatMap(lambda line: line.split(' '))
# If we have configured pyspark with hdfs then we have to specify local file system as
# sc.textFile('file"///Users/....')

a = words.map(lambda word: (word, 1))
b = a.reduceByKey(lambda a,b:a+b)
b.collect()
```