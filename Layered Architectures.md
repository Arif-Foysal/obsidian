Also known as the **n-tier** architecture pattern.

**Structure:** Organized the system into layers, each layer performing a specific role within the application.

>[!Note]
>Each layer is designed to do it's own task and does not interfere with other layers.


Most of the layered architectures contains four common layers:
1. **Presentation**
	Handling all user interface and browser communication logic.
2. **Business**
   Executes business logic
3. **Persistence**
   Manages communication between the business layer and the database layer.
4. **Database**
   Responsible for storing and retrieving data.
   
>[!Note]
>**Business** and **Persistence** may be dissolved into one layer when needed.

### Drawbacks of layered architectuers
- **Granularity** low: The individual components within a layer may be highly coupled and interdependent, making it difficult to isolate and change specific parts of the system without affecting others. 
### Closed vs Open layered architecture

![[Pasted image 20250107224456.png]]
#### Closed Layer
- A request must pass through each layer sequentially.
- A layer can only interact with the layer immediately below it.
- No skipping layers.
- Stronger encapsulation.
#### Open Layer
- A request may skip layers when appropriate.
- Greater freedom but with increased responsibility to maintain the architecture's integrity.
- Useful for scenarios where performance optimizations are critical or some layers don't need to process specific tasks.



### Characteristics

| Category           | Low/High | Reason                                                                                                                                                             |
| ------------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Agility            | Low      | Overall agility is the ability to respond quickly to a constantly changing environment.Any significant changes often require modifications across multiple layers. |
| Rate of deployment | Low      | Each layer depends on others, so deploying changes often requires testing and deploying multiple layers together.                                                  |
| Testability        | High     | The separation of concerns in layered architecture makes it easier to test each layer independently.                                                               |
| Performance        | Low      | The strict communication flow in closed layers adds overhead.                                                                                                      |
| Scalibility        | Low      | Layered architecture doesn’t inherently support horizontal scalability. Each layer can become a bottleneck if not designed with scalability in mind.               |


## Practice Problems

1. Why is “the ease of deployment” considered to be difficult (LOW)  in the case of layered architecture whereas, “the  ease of development criteria” considered to be easy (HIGH)?
**Ans:** 

The reasons are given below:
**Low ease of deployment:**
- **Granularity** low: The individual components within a layer may be highly coupled and interdependent, making it difficult to isolate and change specific parts of the system without affecting others. 
- All dependent layers need thorough testing before deployment.
**High ease of development**
- **Separation of Concerns:** Each layer has a clear responsibility, making it easier to focus on specific tasks.
- **Parallel Development:** Teams can work on different layers simultaneously.
- **Reusability:** Common components in layers like services or persistence speed up development.


2. Analyze the ratings of overall agility, testability, scalability, and performance of Layered Architecture.
Ans: 
![[Layered Architectures#Characteristics]]

