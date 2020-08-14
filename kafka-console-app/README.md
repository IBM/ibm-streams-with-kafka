# IBM Event Streams console sample application

This Python console application demonstrates how to connect to [IBM Event Streams for IBM Cloud](https://cloud.ibm.com/docs/services/EventStreams?topic=eventstreams-getting_started), send and receive messages using the [confluent-kafka-python](https://github.com/confluentinc/confluent-kafka-python) library. It also shows how to create and list topics using the Event Streams for IBM Cloud Admin REST API.

__Important Note__: This sample creates a topic with one partition on your behalf. On the Standard plan, this will incur a fee if the topic does not already exist.

## Running the application

### Prerequisites

* [Python](https://www.python.org/downloads/) 3.6 or later

### Installing dependencies

Run the following commands on your local machine, after the prerequisites for your environment have been completed:

```bash
pip install -r requirements.txt
```

### Supply IBM Event Streams credentials

Copy the `env.sample` file to `.env`.

Edit the `.env` file with IBM Event Streams credentials.

To find the values for `KAFKA_BROKERS_SASL`, `KAFK_ADMIN_URL` and `PASSWORD`, access your Event Streams instance in IBM Cloud®, go to the `Service Credentials` tab and select the `Credentials` you want to use.

__Note__: `KAFKA_BROKERS_SASL` must be a single string enclosed in quotes. For example: `"host1:port1,host2:port2"`. We recommend using all the Kafka hosts listed in the `Credentials` you selected.

### Running the Sample

Once built, to run the sample, execute the following command:

```bash
python3 app.py
```
Alternatively, you can run only the producer or only the consumer by respectively appending the switches `-producer` or `-consumer`  to the command above.

The sample will run indefinitely until interrupted. To stop the process, use `Ctrl+C`.