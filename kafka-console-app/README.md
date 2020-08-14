# IBM Event Streams for IBM Cloud Kafka Python console sample application
This Python console application demonstrates how to connect to [IBM Event Streams for IBM Cloud](https://cloud.ibm.com/docs/services/EventStreams?topic=eventstreams-getting_started), send and receive messages using the [confluent-kafka-python](https://github.com/confluentinc/confluent-kafka-python) library. It also shows how to create and list topics using the Event Streams for IBM Cloud Admin REST API.

__Important Note__: This sample creates a topic with one partition on your behalf. On the Standard plan, this will incur a fee if the topic does not already exist.

## Running the application

## Prerequisites
* [Python](https://www.python.org/downloads/) 3.6 or later

##### macOS 
* Open Keychain Access, export all certificates in System Roots to a single .pem file

## Installing dependencies
Run the following commands on your local machine, after the prerequisites for your environment have been completed:
```shell
pip install -r requirements.txt
```

## Running the Sample
Once built, to run the sample, execute the following command:
```shell
python3 app.py <kafka_brokers_sasl> <kafka_admin_url> <api_key> <ca_location>
```

To find the values for `<kafka_brokers_sasl>`, `<kafka_admin_url>` and `<api_key>`, access your Event Streams instance in IBM Cloud®, go to the `Service Credentials` tab and select the `Credentials` you want to use.  If your user value is `token`, specify that with the password seperated by a `:`.

`<ca_location>` is the path where the trusted SSL certificates are stored on your machine and is therefore system dependent. 
For example:
* Ubuntu: /etc/ssl/certs
* RedHat: /etc/pki/tls/cert.pem
* macOS: The .pem file you created in the prerequisite section

__Note__: `<kafka_brokers_sasl>` must be a single string enclosed in quotes. For example: `"host1:port1,host2:port2"`. We recommend using all the Kafka hosts listed in the `Credentials` you selected.

Alternatively, you can run only the producer or only the consumer by respectively appending the switches `-producer` or `-consumer`  to the command above.

The sample will run indefinitely until interrupted. To stop the process, use `Ctrl+C`.