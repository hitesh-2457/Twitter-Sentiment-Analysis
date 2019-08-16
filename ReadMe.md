README
======

Sentiment analysis on tweets.

This is a SPARK-KAFKA Streaming application.\
The TwitterHandler.scala class connects to Twitter stream with "Twitter4j" library, 
read tweets over a window and performs sentiment analysis using "StanfordCoreNLP" library.
The analyzed data is published to a Kafka topic.

One can setup ELK-stack to read the sentiments published to Kafka, perform analysis and 
visualize the data.

Below is an example of this entire stack setup locally:
![alt text](http://url/to/img.png)

