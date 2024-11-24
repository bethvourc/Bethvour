# Real Time Stock Analysis

## Overview

This project demonstrates the use of Apache Kafka to implement a producer-consumer model for real-time data streaming. The primary goal is to produce and consume data using Kafka topics, allowing for efficient, distributed communication between different components of a system. This can be particularly useful for applications requiring fast and scalable data processing pipelines, such as in financial systems or big data analytics.

## Project Components

1. **KafkaProducer.ipynb**: This Jupyter Notebook file contains the implementation of the Kafka producer. It reads data from a CSV file and sends it as messages to a Kafka topic. This file is responsible for:
   - Connecting to a Kafka broker.
   - Reading data from the provided CSV file (`indexProcessed.csv`).
   - Publishing messages to the specified Kafka topic.

2. **KafkaConsumer.ipynb**: This Jupyter Notebook file contains the implementation of the Kafka consumer. It listens to the specified Kafka topic and processes messages as they arrive. This file is responsible for:
   - Connecting to a Kafka broker.
   - Subscribing to a Kafka topic.
   - Consuming and processing incoming messages.

3. **indexProcessed.csv**: This CSV file contains the data that is used as input for the Kafka producer. It may contain data such as stock indexes, metrics, or other information relevant to the streaming process.

## Prerequisites

- **Apache Kafka**: Make sure you have Apache Kafka installed and running on your local machine or a server.
- **Python Libraries**: This project uses the following Python libraries:
  - `confluent-kafka`: To connect with Kafka and handle producer and consumer operations.
  - `pandas`: To handle and manipulate the data from CSV files.
  - `json`: To serialize and deserialize messages for Kafka communication.
  - Other standard libraries as required.

## Setup Instructions

1. **Install Dependencies**: Make sure to install the required Python libraries by running the following command:
   ```sh
   pip install confluent-kafka pandas
   ```

2. **Run Kafka**: Ensure that Kafka is running on your system. Start the ZooKeeper server and Kafka broker as follows:
   ```sh
   bin/zookeeper-server-start.sh config/zookeeper.properties
   bin/kafka-server-start.sh config/server.properties
   ```

3. **Create Kafka Topics**: Create the necessary Kafka topic that the producer will write to and the consumer will read from. You can do so with the following command:
   ```sh
   bin/kafka-topics.sh --create --topic your_topic_name --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
   ```

4. **Running the Producer and Consumer**:
   - Start with the `KafkaProducer.ipynb` notebook. Ensure that the topic name matches the one created earlier.
   - After producing messages, open the `KafkaConsumer.ipynb` notebook to start consuming the data.

## Usage

- **KafkaProducer.ipynb** will read the `indexProcessed.csv` file and publish the records to the Kafka topic.
- **KafkaConsumer.ipynb** will then consume the records from the Kafka topic and process them in real-time.

The goal is to showcase how to produce and consume data in real-time using Apache Kafka, which can be applied to build robust data processing pipelines.

## Notes

- Ensure that the Kafka server is properly configured and running before running the notebooks.
- Modify the Kafka configurations (such as topic name, bootstrap servers, etc.) in the notebooks based on your environment.
- You can adapt the consumer logic to perform specific data analysis or further processing as needed.

## Future Improvements
- **Error Handling**: Add error handling mechanisms for better resilience during network failures or Kafka outages.
- **Data Validation**: Introduce validation steps for data consistency and correctness before producing or consuming.
- **Scalability**: Implement multiple partitions to allow scalability across different consumers and producers.

## License
This project is released under the MIT License.

## Contact
For any questions or collaboration requests, please contact Bethvour Chike at [bethvourc@gmail.com].

