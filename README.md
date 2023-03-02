# Last Project

My last project involved collecting data from arm chips, creating a C http client that would deliver streams to a kafka broker.
The data would then be processed using Spark Streaming and consumed by a lambda function and stored in an elasticsearch database.
My choices behind this architecture was based on fault-tolerance, high-availability and consistency. 
The pinned projects showcase all components of this venture.

## Architecture 1
Arm Cortex M4(Producer) ----> Kafka Broker -------> Spark Streaming/ Kafka Streams --------------> Api Gateway -------> Consumer Group (AWS Lambda)------------> Elastic Search

To utilize the Kafka Broker as it was hosted, I also secured it using SSL to allow an E-Shop to scrape data using Athena (Built by scrapy) injested into a topic 
then cleaned and transformed using Kafka Streams and finally sent to the woocommerce rest api for delivery.


## Architecture 2
Athena(Scrapes Data) ---------> Kafka Broker ----------> Kafka Streams -----------> Woocommerce Consumer (HCCore Apache) ------------> WC REST API

To make the process even faster and utilize all cores of the computers hosting the consumers, I used a combination of CountDownLatch and CyclicBarriers for multithreading.

I consider this as event-driven microservices as they all used different servers or runtimes but still communicated with each other. Another win for distributed systems.

All these can be seen in the projects pinned below.
