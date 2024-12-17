
- Breaks the system down into a collection of smaller deployable independent units.
- Each service has its own logic and the database as well as perform the specific functions.
- Services intercommunicate with some lightweight mechanisms, often an HTTP resource API
- Easy maintainability, Scalability, and low coupling
- Time to market is reduced.
- Services can be scaled up or down easily and independently.

**Trade offs:**
- Extra complexity, cross-cutting concerns, and cost.
- less suitable for complex [[transactions]] because of the difficulty of synchronizing activities across distributed systems.
- The freedom of every team to choose its own technology comes at a cost.
- Intellectual control of the total system may be difficult because of the large number of microservices.
