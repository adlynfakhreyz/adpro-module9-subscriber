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