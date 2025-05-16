# Reflection

### a. What is AMQP?

AMQP (Advanced Message Queuing Protocol) is an open standard application layer protocol for message-oriented middleware. It enables applications to communicate through message brokers by:
- Sending messages between applications
- Managing message queues
- Handling routing and delivery of messages
- Ensuring reliable message delivery

### b. Understanding the AMQP URL: `guest:guest@localhost:5672`

The URL can be broken down into these components:

- First `guest`: Username for authentication (default RabbitMQ username)
- Second `guest`: Password for authentication (default RabbitMQ password)
- `localhost`: The hostname where the AMQP broker (like RabbitMQ) is running
- `5672`: The default port number that AMQP uses for non-SSL connections

So when written as `amqp://guest:guest@localhost:5672`, it creates a connection to a local AMQP broker using the default credentials.

## Simulation slow subscriber

![Image](https://github.com/user-attachments/assets/ad96d5b1-4b6d-4f0f-a92e-a20234b54434)

The total number of queues is shown as 2, which reflects the number of active queues currently declared in your RabbitMQ instance. This number can vary depending on how many queues have been created by applications or services connected to RabbitMQ.

## Reflection and Running at least three subscribers

![Image](https://github.com/user-attachments/assets/3673adcf-3fe3-4aaa-8d1f-b369e4b20b1d)

The message queue is drained faster with more subscribers because RabbitMQ distributes messages among all active consumers in a round-robin fashion. This parallel processing allows multiple messages to be handled simultaneously, reducing overall latency and backlog. From the code, one improvement could be adding message acknowledgment (ack) handling properly and making subscriber logic more efficient to avoid delays—especially if any subscriber is blocking. Also, adding retry or dead-letter logic might help in case a message fails to be processed.