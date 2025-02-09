#software-engineering  #software-architecture

**Resources:** https://drive.google.com/drive/folders/1O5hLSCu1InGJbcGU-3u86LfU1-SsS3Og

>[!Contents]
>## Final Exam Materials
>- https://drive.google.com/drive/folders/1qDL3wlFJpzHbo_augtCJ3KzsjR4TR45Y
>- [[Quality Attributes]]
>- [[Availability]]
>- [[Deployability]]
>- [[Energy Efficiency in Software Architectures]]
>- [[Architecturally Significant Requirements(ASR)]]
>- [[Software Architecture Patterns]]

[[Software Architecture Practice problems]]

## N-Tier(Layered) Architecture
An approach where project/program is distributed among N separate computers in a distributed network.


### Types of N-Tire

- **3-Tier**
- **2-Tier**
- **1-Tier**

### Advantages of multi-Tiering
 Scalability
 Reliability
 Fault tolerance
 Security
 Maintainability
 Reusability

## Types of Layered Architectural Patterns
 [[MVC Architecture]]
 HMVC
 MVVM
 MVP

![[Monolithic Architecture]]

![[Micro service architecture]]

## Micro-Kernel Architecture
Also called plug-in architecture which consists of two types of components – a core system and several plug-in modules.

 The core system works on minimal functionality to keep the system operational, the plug-in modules are independent components with specialized processing.
 Suitable for applications that have a fixed set of core routines and dynamic set of rule that needs frequent updates.
 The plugins must have good handshaking code so that the
micro kernel is aware of the plugin installation and is ready to work.

## Event-Driven Architecture

 It is made up of decoupled, single-purpose event processing components that asynchronously receive and process events.
 Agile and highly performant
 Easy debugging, fast development and low coupling



## Micro Service vs event driven

| Aspect                | Microservices Architecture                                                                                                                        | Event-Driven Architecture                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Communication         | Typically relies on synchronous communication between services via APIs.                                                                          | Relies on asynchronous communication through events/messages.                                                                              |
| Service Structure     | Organized around individual business capabilities or features, with each service responsible for its own data and functionality.                  | Decoupled services that react to events emitted by other services or external sources.                                                     |
| Scalability           | Scalability is achieved by independently scaling each microservice based on its workload.                                                         | Scalability is achieved by distributing events across multiple event consumers, allowing for horizontal scaling.                           |
| Dependency Management | Services are loosely coupled but may still have dependencies on each other, especially if they share data.                                        | Services are decoupled from each other and only interact through events, minimizing direct dependencies.                                   |
| Failure Isolation     | Failures in one microservice may affect other microservices if they have dependencies or shared resources.                                        | Failures in one component generally don't affect other components directly, as they are decoupled through events.                          |
| Data Consistency      | Maintaining data consistency across services can be challenging, often requiring distributed transactions or eventual consistency strategies.     | Eventual consistency is more common, with each service responsible for its own data consistency and reacting to events asynchronously.     |
| Complexity            | Managing the interactions between microservices and ensuring proper communication can lead to complexity, especially in large systems.            | Focuses on decoupled event processing, which can simplify communication and make the system more adaptable to change.                      |
| Use Cases             | Suitable for applications with diverse functionalities and independent business capabilities, such as social media platforms or e-commerce sites. | Well-suited for scenarios where events are central to the application logic, such as real-time data processing, IoT, or complex workflows. |
