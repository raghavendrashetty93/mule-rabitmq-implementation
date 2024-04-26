# mule-rabitmq-implementation

## About Project
Publish, Consume messages from RabbitMQ using AMQP Connector
Anypoint Connector for AMQP (AMQP Connector) enables your application to publish and consume messages using an AMQP 0.9.1-compliant broker. 

## About RabbitMQ
RabbitMQ is a reliable and mature messaging and streaming broker, which is easy to deploy on cloud environments, on-premises, and on your local machine. 

**Interoperable:** RabbitMQ supports several open standard protocols, including AMQP 1.0 and MQTT 5. There are multiple client libraries available.
**Flexible:** RabbitMQ provides many options you can combine to define how your messages go from the publisher to one or many consumers. Routing, filtering, streaming, federation, and so on, you name it.
**Reliable:** With the ability to acknowledge message delivery and to replicate messages across a cluster, you can ensure your messages are safe with RabbitMQ.

## Setting Up Prerequisites
Let’s use a cloud RabbitMQ service through CloudAMQP.

- Go to https://www.cloudamqp.com/ and create a free account.
- Then, create a new Instance using the plan “Little Lemuer”. It doesn't cost anything and it's all we need.
- Copy the username and password by clicking on the name of the plan you created. This will be used to connect to the RabbitMQ service from the MuleSoft application.

- Creating a Queue: Now click on 'RabbitMQ Manager' > 'Queues and Streams'. From the 'Add a new queue' section, provide a valid name and hit 'Add queue'. (In my case it’s MULESOFT-QUEUE)
- Create an Exchange: Navigate to 'Exchanges'. From the 'Add a new exchange' section, provide a valid name and hit 'Add exchange'. (In my example ‘MULESOFT’)
- Binding Exchange to Queue: Click on the Exchange name you just created. From the 'Bindings' section, select 'To queue', enter the name of the queue created and hit 'Bind'. Every message published on Exchange now flows to the queue.

## Setting Up Mulesoft Application

- From Anypoint Studio create a new Mule Project
- Create two simple flows to Publish and Consume messages from RabbitMQ Server.
    - Publish Flow (Sends message to RabbitMQ Exchange.)
    - Subscriber Flow (Consumes message from Queue)
    - AMQP Config ( Use values from Setting Up RabbitMQ section)
