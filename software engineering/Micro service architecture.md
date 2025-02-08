
- Breaks the system down into a collection of smaller deployable independent units.
- Each service has its own logic and the database as well as perform the specific functions.
- Services intercommunicate with some lightweight mechanisms, often an HTTP resource API
- Easy maintainability, Scalability, and low coupling
- Time to market is reduced.
- Services can be scaled up or down easily and independently.

Microservices architecture is gaining traction as an alternative to monolithic and service-oriented architectures (SOA). It is built on the concept of **separately deployed units**, where each component functions independently, enabling streamlined deployment, scalability, and decoupling.

A key concept in this architecture is the **service component**, which can range from a single function to a significant portion of an application. Determining the right level of granularity for these components is a major design challenge.

Microservices follow a **distributed architecture**, meaning components are fully decoupled and communicate via protocols like REST, SOAP, or AMQP. This architecture evolved in response to challenges in monolithic and SOA-based applications:

- **Monolithic applications** suffer from tightly coupled components, making changes, testing, and deployment difficult. Microservices solve this by enabling independent development and deployment of components.
- **SOA-based applications** are often complex and expensive. Microservices simplify services by reducing orchestration and making service access more straightforward.

## Architecture Topologies
- **API REST-Based Topology**
    
    - Ideal for exposing small, self-contained services via an API.
    - Uses fine-grained service components that perform specific business functions.
    - Typically found in cloud-based RESTful web services (e.g., Google, Yahoo, Amazon).
      ![[Pasted image 20250208080255.png]]
      
- **Application REST-Based Topology**
    
    - Suitable for traditional web-based or fat-client business applications.
    - Uses a separate user-interface layer to access service components via REST.
    - Service components are coarser-grained and represent business functions rather than single-action services.
    - Common in small to medium-sized business applications with low complexity.
      ![[Pasted image 20250208080312.png]]
- **Centralized Messaging Topology**
    
    - Uses a lightweight message broker (e.g., ActiveMQ, HornetQ) instead of REST for communication.
    - Found in larger applications requiring advanced queuing, asynchronous messaging, and better scalability.
    - Avoids traditional SOA complexity by using a simple message broker for transport without orchestration.
    - Issues like single points of failure are mitigated with broker clustering and federation.
	![[Pasted image 20250208080329.png]]

- **Avoiding Orchestration**: If orchestration is required between service components, the services are likely too fine-grained. Similarly, if inter-service communication is needed to process a single request, the components may be improperly partitioned.
- **Shared Database**: For inter-service data dependencies, a shared database can be used instead of invoking other service components, preventing tight coupling.
- **Shared Functionality**: Common functionality across services can be duplicated in each service, avoiding inter-service dependencies but violating the DRY (Don’t Repeat Yourself) principle.
  
## Considerations
  Microservices offer several advantages:

- They provide better **scalability** and **continuous delivery**, allowing real-time production deployments and reducing the need for large, scheduled deployment windows.
- **Deployment flexibility**: Only the services that change need to be deployed, enabling continuous availability during updates.


## Pattern Analysis
| **Factor**              | **Rating** | **Analysis**                                                                                                                                                        |
|-------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Overall agility**      | High       | Change is isolated to individual service components, enabling fast and easy deployment. The loose coupling of services also facilitates quick adaptation to change.  |
| **Ease of deployment**   | High       | Microservices' fine-grained, independent nature allows for "hot deployments" at any time, reducing deployment risks and minimizing the impact of failed deployments.   |
| **Testability**          | High       | Testing is easier due to service isolation. Regression testing for individual components is simpler than testing an entire monolithic application.                  |
| **Performance**          | Low        | Distributed architecture can limit performance, though high-performance applications can still be built using microservices.                                        |
| **Scalability**          | High       | Each service component can be individually scaled, allowing for fine-tuned scaling to match specific needs, such as handling high throughput for certain functions.   |
| **Ease of development**  | High       | Smaller, isolated components reduce the risk of changes affecting other parts of the system, simplifying development and reducing the need for cross-team coordination. |


**Trade offs:**
- Extra complexity, cross-cutting concerns, and cost.
- less suitable for complex [[transactions]] because of the difficulty of synchronizing activities across distributed systems.
- The freedom of every team to choose its own technology comes at a cost.
- Intellectual control of the total system may be difficult because of the large number of microservices.
