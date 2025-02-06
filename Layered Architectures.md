Also known as the **n-tier** architecture pattern.

**Structure:** Organized the system into [[horizontal layers]], each layer performing a specific role within the application.

>[!Note]
>Each layer is designed to do it's own task and does not interfere with other layers.


Most of the layered architectures contains four common layers:
1. **Presentation**
	Handling all user interface and browser communication logic.
2. **Business**
   Executes business logic associated with the request.
3. **Persistence**
   Manages communication between the business layer and the database layer.
4. **Database**
   Responsible for storing and retrieving data.
   
>[!Note]
>**Business** and **Persistence** may be dissolved into one layer when needed.

### Drawbacks of layered architectuers
- **Granularity** low: The individual components within a layer may be highly coupled and interdependent, making it difficult to isolate and change specific parts of the system without affecting others.
- Can be slow due to strict communication in closed layers.

### Closed vs Open layered architecture

![[Pasted image 20250107224456.png]]
#### Closed Layer
- A request must pass through each layer sequentially.
- A layer can only interact with the layer immediately below it.
- No skipping layers.
- Stronger encapsulation.
##### When used
- When enforcing strict **layer separation** for maintainability.
- When changes in lower layers should not affect upper layers.
- Common in **enterprise and large-scale** applications.
#### Open Layer
- A request may skip layers when appropriate.
- Greater freedom but with increased responsibility to maintain the architecture's integrity.
- Useful for scenarios where performance optimizations are critical or some layers don't need to process specific tasks.
##### When used
- When performance is **critical** and direct access is needed.
- When certain layers do not add significant business value.
- Suitable for **small applications** where flexibility is needed.
### Pattern Analysis

| Category            | Low/High | Reason                                                                                                                                                                                                                                                                                                                                    |
| ------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Agility             | Low      | Overall agility is the ability to respond quickly to a constantly changing environment.Any significant changes often require modifications across multiple layers.                                                                                                                                                                        |
| Rate of deployment  | Low      | Each layer depends on others, so deploying changes often requires testing and deploying multiple layers together.                                                                                                                                                                                                                         |
| Testability         | High     | Because components belong to specific layers in the architecture, other layers can be mocked or stubbed, making this pattern is relatively easy to test. A developer can mock a presentation component or screen to isolate testing within a business component, as well as mock the business layer to test certain screen functionality. |
| Performance         | Low      | The strict communication flow in closed layers adds overhead.                                                                                                                                                                                                                                                                             |
| Scalability         | Low      | Layered architecture doesn’t inherently support horizontal scalability. Each layer can become a bottleneck if not designed with scalability in mind.                                                                                                                                                                                      |
| Rate of development | High     | Clear separation of concerns allows developers to work on individual layers in parallel without affecting others.                                                                                                                                                                                                                         |

## Considerations

**Watch out** for:
- **[[Architecture sinkhole anti-pattern]]**: 
  This anti-pattern describes the situation where requests flow through multiple layers of the architecture as simple pass-through processing with little or no logic performed within each layer. For example, assume the presentation layer responds to a request from the user to retrieve customer data. The presentation layer passes the request to the business layer, which simply passes the request to the persistence layer, which then makes a simple SQL call to the database layer to retrieve the customer data. The data is then passed all the way back up the stack with no additional pro‐ cessing or logic to aggregate, calculate, or transform the data.
  Every layered architecture will have at least some scenarios that fall into the architecture sinkhole anti-pattern. The key, however, is to analyze the percentage of requests that fall into this category. The 80-20 rule is usually a good practice to follow to determine whether or not you are experiencing the architecture sinkhole anti-pattern
- **Monolithic Tendency:**
  Another consideration with the layered architecture pattern is that it tends to lend itself toward monolithic applications, even if you split the presentation layer and business layers into separate deployable units. While this may not be a concern for some applications, it does pose some potential issues in terms of deployment, general robust‐ ness and reliability, performance, and scalability.
## Pattern Example
To illustrate how layered architecture works, consider a request from user to retrieve a particular customer's information:
![[Pasted image 20250206182729.png]]

- **Customer Screen**: Doesn't know how to retrieve the data, or what business logic needed to process the data. Once it receives request to get the customer information, then it forwards the request to the **customer delegate** module.
- **Customer Delegate**: Forwards requests to the appropriate business layer module and ensures correct data handling.
- **Business Layer (Customer Object)**: The customer object in the business layer is responsible for aggregating all of the information needed by the business request (in this case to get customer information). This module calls out to the customer dao (data access object) module in the persistence layer to get customer data, and also the order dao module to get order information. These modules in turn execute SQL statements to retrieve the corresponding data and pass it back up to the customer object in the business layer
- **Persistence Layer (DAO Modules)**: Executes SQL queries to retrieve customer and order data.
- **Data Flow**:
    1. Customer Screen → Customer Delegate
    2. Customer Delegate → Business Layer
    3. Business Layer → DAO Modules (Customer & Order)
    4. DAO Modules → Business Layer → Customer Delegate → Customer Screen



## Practice Problems

1. Why is “the ease of deployment” considered to be difficult (LOW)  in the case of layered architecture whereas, “the  ease of development criteria” considered to be easy (HIGH)?
**Ans:** 

The reasons are given below:
**Low ease of deployment:**
- **[[Granularity]]** low: The individual components within a layer may be highly coupled and interdependent, making it difficult to isolate and change specific parts of the system without affecting others. 
- All dependent layers need thorough testing before deployment.
**High ease of development**
- **Separation of Concerns:** Each layer has a clear responsibility, making it easier to focus on specific tasks.
- **Parallel Development:** Teams can work on different layers simultaneously.
- **Reusability:** Common components in layers like services or persistence speed up development.


2. Analyze the ratings of overall agility, testability, scalability, and performance of Layered Architecture.
Ans: 
![[Layered Architectures#Pattern Analysis]]

