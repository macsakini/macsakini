# Last Project


All pinned repos are microservices running my last project. To make it simple to understand see here:

https://www.macmaxwell.com/last-project/

Here is also a breakdown of each architecture:

## Architecture 1
Arm Cortex M4(Producer) —-> Kafka Broker ——-> Spark Streaming/ Kafka Streams ————–> Api Gateway ——-> Consumer Group (AWS Lambda)————> Elastic Search

## Architecture 2
Athena(Scrapes Data) ———> Kafka Broker ———-> Kafka Streams ———–> Woocommerce Consumer (HCCore Apache) ————> WC REST API
