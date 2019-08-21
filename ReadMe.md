README
======

Sentiment analysis on tweets.

This is a SPARK-KAFKA Streaming application.\
The TwitterHandler.scala class connects to Twitter stream with "Twitter4j" library, 
read tweets over a window and performs sentiment analysis using "StanfordCoreNLP" library.
The analyzed data is published to a Kafka topic.

One can setup ELK-stack to read the sentiments published to Kafka, perform analysis and 
visualize the data.

Below is an example of this entire stack setup locally:\
This Bar graph shows sentiments on "Sports" related tweets as of 27th July 2019:\
![alt text](https://github.com/hitesh-2457/Twitter-Sentiment-Analysis/blob/master/KibanaGraphs/SentimentAnalysis.jpg)

This Pie graph shows sentiments on "Sports" related tweets as of 27th July 2019:\
![alt text](https://github.com/hitesh-2457/Twitter-Sentiment-Analysis/blob/master/KibanaGraphs/SentimentAnalysisPie.jpg)

Usage:
------

To package the code use sbt->assembly

Twitter Sentiment Analysis
--------------------------
Usage:

`spark-submit --class TwitterHandler <PathToJarFile> <Kafka-Topic> <Twitter-filter> [more space seperated filter keys]`

Example:

`spark-submit --class TwitterHandler target\scala-2.11\Kafka-Assignment-assembly-0.1.jar sentiment-analysis sports`

Explaination of command:
TwitterHandler	this is the spark class name
You can add more than one keyword to the argument list after the topic name, the class will be invoked the API endpoint with these filters.