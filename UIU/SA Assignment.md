<div class="container">
<h1>
Software Architecture
</h1>
<h2>
Assignment 01
</h2>
<p>
Name: MD. Arif Faysal Nayem
<p>ID: 011201194</p>
<p>Course: Software Architecture</p>
Section: B
</div>

1. In such a case, the microservices architecture would be preferable because that would render certain advantages. It can scale individual components independently: User Authentication, Booking, Payment, and Seat Availability handle sudden spikes in traffic through load balancing and auto-scaling. The event-driven design of the system introduces real-time data consistency-introduce message queues like Kafka/RabbitMQ for seat availability updates, distributed caching like Redis to optimize checks, and database sharding and replication for better performance. Finally, integration with payment gateways and loyalty programs can be enabled through APIs, while flexibility in microservices allows each of them to use the most appropriate database and technology to interact smoothly with third-party interaction.
2. Some of the key benefits of microservices architecture include:
   
**Agility**: Microservices will let teams independently build smaller services, thus enabling faster development, simpler deployments, and flexibility.

Rate **of** deployment: Independent deployment of small services will allow for quicker and more frequent releases. This decreases the risk associated with deployments and enables Continuous Delivery.

**Testability**: Smaller services are easier to test in isolation, improving test coverage and accelerating feedback cycles.

**Performance**: Microservices can be scaled independently of each other, thus optimizing resource utilization and improving responsiveness.

**Scalability**: Services can be scaled horizontally to meet demand, thus enabling effective resource allocation and fine-grained scalability.

**Rate of Development**: It can develop and deploy smaller, independent services faster, hence speeding up the overall development process and allowing parallel development.

3. 

| Feature          | Broker Pattern                                                              | Mediator Pattern                                                 |
|------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------|
| **Definition**    | Decentralized communication through brokers that route requests.            | Centralized controller (mediator) manages communication between components. |
| **Structure**     | Uses a broker to enable indirect communication.                              | Uses a mediator as a single point of communication.              |
| **Use Case**      | Distributed systems, message queues, and event-driven architectures.         | GUI event handling, workflow management, and chat applications.  |
| **Scalability**   | More scalable due to decentralized interactions.                             | Less scalable due to the mediator becoming a bottleneck.         |
| **Example**       | Enterprise Service Bus (ESB), gRPC, Kafka.                                  | MVC Controller, Chat room managers.                              |
| **When to Use**   | **Broker Pattern**: When building distributed, loosely coupled systems where services communicate asynchronously. | **Mediator Pattern**: When centralizing complex inter-component interactions to simplify dependencies. |

4. 

| Feature           | Microkernel Architecture                                                         | Microservices Architecture                                                      |
| ----------------- | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Definition**    | A core system with plug-in modules to extend functionality.                      | A distributed architecture where services function independently.               |
| **Structure**     | A minimal core (kernel) with optional extensions (plugins).                      | A set of loosely coupled, independently deployable services.                    |
| **Communication** | Internal communication between core and plugins.                                 | Services communicate via APIs, typically REST or gRPC.                          |
| **Scalability**   | Limited scalability; mostly vertical scaling.                                    | Highly scalable due to independent service deployment.                          |
| **Deployment**    | Monolithic with modular extensibility.                                           | Fully distributed and independently deployable services.                        |
| **Use Case**      | Applications with a stable core and extensible features, e.g., IDEs, OS kernels. | Large, complex, and evolving applications, e.g., cloud-native apps, e-commerce. |
| **Examples**      | Eclipse IDE, Operating Systems (Linux Kernel).                                   | Netflix, Amazon, Uber.                                                          |

**When to Use Which Pattern?**

**Microkernel Architecture (Plugin-Based)**

- Use when the core functionality is stable, and only specific features need customization.
- Suitable for applications that require modular extensibility, like **IDEs (Eclipse, VS Code), operating systems, or CMS platforms**.
- Works well when system updates primarily involve plugins rather than the core.
**Microservices Architecture (Distributed)**

- Ideal for **large-scale, cloud-based, or enterprise applications** where independent scaling is needed.
- Best for applications that require **continuous deployment and flexibility**, such as **e-commerce, SaaS platforms, and fintech apps**.
- Suitable when different teams work on different services and need independent deployments.

5. 

- **Event Producers (Sources of Events)**
    
    - **User Interface (UI)/Trading Application**
        - Users place or cancel trade orders.
        - Generates events like `TradePlaced`, `TradeCancelled`.
    - **Stock Market Data Feed**
        - Continuously streams stock price updates.
        - Generates `StockPriceUpdated` events.
    - **Trade Execution Engine**
        - Confirms when a trade is successfully executed.
        - Emits `TradeExecuted` events.
- **Event Consumers (Subscribers to Events)**
    
    - **Trade Processing Service**
        - Listens for `TradePlaced` and `TradeCancelled` events.
        - Validates and processes trades accordingly.
    - **Portfolio Management Service**
        - Subscribes to `TradeExecuted` and `StockPriceUpdated` events.
        - Updates user portfolio values in real time.
    - **Notification Service**
        - Listens for `TradeExecuted` and critical `StockPriceUpdated` events.
        - Sends real-time alerts to users.
- **Message Broker (Event Handling and Routing)**
    
    - **Kafka/RabbitMQ/Pub-Sub System**
        - Acts as an event bus to decouple producers and consumers.
        - Ensures reliable delivery of trade and market events.
          


The concept of events is central to this system. Events are the things that happen within the system and might be of interest to other parts of the system—for example, "Trade Placed," "Stock Updated." These are generated by some components and consumed by other interested ones.

**Event Producers**

- **Trade Service**: Handles user requests for placing and canceling trades. Upon successful validation, it emits either "Trade Placed" or "Trade Cancelled" events.
- **Market Data Service**: Continuously receives real-time stock price updates from external market data providers. It emits events of type "Stock Price Updated".
- **Portfolio Service**: Manages user portfolios and their holdings. Listens for "Trade Placed" events to update portfolio balances and emits "Portfolio Value Updated" events.
- **Alerting Service**: Monitors market conditions and user-defined alerts. In case a trigger condition is met, it emits events of the type "Market Alert Triggered".

**Event Consumers**

- **Order Processing Service**: Listens for "Trade Placed" events. Verifies the details of the trade for sufficiency of funds and communicates with the exchange API to complete the trade. It may further publish "Trade Executed" events.
- **Portfolio Update Service**: Listens for events "Trade Executed" and "Stock Price Updated". Updates respective user portfolios and publishes events "Portfolio Value Updated".
- **Notification Service**: Subscribes to events such as "Trade Executed," "Trade Cancelled," and "Market Alert Triggered." Sends users real-time notifications on their preferred channels, whether via push notification, email, or SMS.
- **Real-time UI Updates Service**: Subscribes to events "Stock Price Updated", "Portfolio Value Updated", "Trade Executed", and "Market Alert Triggered". Pushes changes right into the user's interface for real-time effects on updated market data, portfolio values, status of trades, or alerts.

 **Message Broker**

- **Centralized Message Queue**: A Centralized Message Queue forms the backbone of the event-driven architecture. Various producers publish their events to a message queue, and consumers subscribe to their relevant topics/queues from which they consume events.

**Event Example - A Trade Placement**

1. User places the trade request through UI.
2. The Trade Service checks the validity of the request and publishes an event "Trade Placed" to the broker.
3. The Order Processing Service consumes the "Trade Placed" event, performs validation of the trade, and communicates with the exchange API.
4. Once the trade is successfully executed, the Order Processing Service produces a "Trade Executed" event.
5. The Portfolio Update Service consumes the "Trade Executed" event and updates the portfolio of the user. It then produces a "Portfolio Value Updated" event.
6. The Notification Service consumes the "Trade Executed" event and sends a confirmation to the user.
7. The Real-time UI Updates Service listens for events such as "Trade Executed" and "Portfolio Value Updated" to update the user's dashboard in real time.


6. 
   
![[Untitled Workspace.png]]

7. 
**Stock Price Update**: This feature ensures that at every given instance, the changes in stock price are updated throughout the system. How it works:

- Market Data Provider streams real-time stock price data continuously.
- Market Data Service receives and processes an incoming stock price update.
- The Market Data Service publishes a "Stock Price Updated" event to the Message Broker (Event Bus).
**There are several subscribers for this event**:
Portfolio Update Service: Updates user portfolios with regard to new stock prices.
**Notification Service**: It sends notifications to the users in case a stock crosses a threshold set by them. Real-time UI Update Service: Updates the stock prices on the user interface for real-time updates.

![[component_diagram.drawio.png]]

