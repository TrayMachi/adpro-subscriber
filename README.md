# Subscriber Adpro Module 9
Tristan Agra Yudhistira
2306245112

## Reflection
#### What is AMQP?
AMQP (Advanced Message Queuing Protocol) is an open standard application layer protocol for message-oriented middleware. It enables applications to communicate through message brokers by:
- Sending messages between applications, systems, or services
- Ensuring reliable message delivery
- Supporting different messaging patterns (publish/subscribe, point-to-point)
- Providing features like message routing, queuing, and security

#### What does it mean? guest:guest@localhost:5672, what is the first guest, and what
is the second guest, and what is localhost:5672 is for?
The connection string can be broken down into these components:

1. First "guest": This is the username for authentication to the AMQP broker (RabbitMQ in this case)
2. Second "guest": This is the password for authentication
3. "localhost:5672": 
   - "localhost" is the hostname where the AMQP broker is running (in this case, on your local machine)
   - "5672" is the default port number that AMQP uses for non-SSL connections

So when combined as "amqp://guest:guest@localhost:5672", it creates a connection URL that tells your application:
- Use the AMQP protocol
- Connect to a broker running on localhost at port 5672
- Authenticate using the username "guest" and password "guest" (these are default credentials in RabbitMQ)