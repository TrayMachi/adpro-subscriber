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

## Images
### Simulation Slow Subscriber
According to the image below, the number of peak queue is 35. This could happen because eEach message takes at least 1 second to process due to the `thread::sleep(ten_millis)` call. If messages are being published faster than once per second, they will naturally pile up in the queue because:
- Publisher: Can send messages without waiting
- Subscriber: Takes 1 second per message to process
![Simulation Slow Subscriber](/public/SlowSubscriber.png)

### Running at least Three Subscribers
Here i running three subscribers with the same amount of message i sent from publishers. The chart show that we successfully reduced the number of queue. This could happen because each subscriber can process messages in parallel, effectively distributing the workload. Each subscriber independently processes messages from the same queue, allowing for concurrent message handling, so instead of 1 message per second, we doing 3 messages per second.
![Running at least Three Subscribers](/public/ThreeSubs.png)
![Chart of Running at least Three Subscribers](/public/ChartThreeSubs.png)