## How to design system
>*'Picking the "**right**" architecture = Picking the right battles + Managing trade-offs' by [Primal Skill](https://primalskill.blog/wins-and-trade-offs-in-software#:~:text=Picking%20the%20%22right%22%20software%20architecture%2C%20for%20example%2C%20is%20like%20picking%20the%20right%20battles%20and%20then%20managing%20the%20trade%2Doffs)*

Choosing the right system design or architecture requires careful consideration of various factors. The process involves understanding both the technical and business requirements, followed by balancing trade-offs in scalability, performance, security, and maintainability. Here's a structured approach to help guide your thought process when deciding the right system design:

#### 1. Understand Business Requirements
- **Identify the key features :** It is about what functionality must the system provide? This includes the core use cases, expected user interactions, and essential workflows.
- **Clarify the non-functional requirements (NRFs):** This includes factors like:
  - **Scalability:** Will the system need to support millions of users? Will traffic grow gradually or exponentially?
  - **Performance:** Are there latency or response time requirements Do certain operation need to be real-time?
  - **Reliability:** What is the acceptable downtime? Should the system offer 99.99% availability or higher?
  - **Security:** What level of data protection and user authentication is required? Are there regulatory compliance needs?
  - **Data Consistency:** Does the system need to ensure immediate consistency (ACID properties), or is eventual consistency acceptable?
  - **Maintainability:** How frequently will the system need updates? Is it critical to have continous deployment or rapid feature development?
- **Constraints:** Identify any constraints or limitations that the system may face. These could be technical, budgetary, or organizational.
  - **Key Considerations:**
    - What is the budget for the system? Are there cost restrictions for resources (servers, databases)?
    - Are there hardware or software limitations (e.g., existing infrastructure)?
    - Does the team have expertise in certain technologies or architectures(e.g., cloud native, microservices)?
    - Are there time constraints for deployments?

**Though Process:** The clearer your understanding of the requirements , the easier it becomes to pick an architecture that aligns with those needs. Ensure that you capture both immadiate needs and potential future scaling considerations. Constraints help narrow down the architectural choices. For example, budget constraints might make a monolithic architecture more attractive than a microservice-based or another architecture.
<<<<<<< HEAD

#### 2. Assess the Workload Characteristics
Analyze the expected workload to decide how to handle traffic, storage, and processing needs.
- **Key Considerations:**
  - What is the **expected load**? (like number of users, API calls per second, data volume)
  - Is the load **consistent** or **spiky**? If spiky , can the system dinamically scale to handle the spike?
  - Will the system require real-time processing (like low latency applications), or is batch processing sufficient?

**Tough Process:** If the system will handle high traffic or real-time data, architectures that support horizontal scaling (like microservice) may be preferable. For smaller systems with predictable workloads, a simpler architecture might suffice.

#### 3. Determine Scalability and Performance Needs
Consider how the system will scale over time and how performance will be optimized. Plan for both short-term and long-term scalability needs. Understand whether the system needs to handled increased traffic, users, or data volume.
  - **Key Considerations:**
    - **Horizontal vs Vertical Scaling:** Add more machines(horizontal) or upgrade existing ones (vertical).
    - Does the system need to scale globally (like serving users for multiple regions)?
    - Should the architecture allow for dinamyc scaling (like using cloud service)?
  
**Though Process:** If scalability is a key concernn, architecture like microservices, with independent services that can scale separately, are better suited. If traffic is expected to be low initially, a monolithic or modular architecture might be chosen and evolved over time.  

#### 4. Design for Availability and Fault Tolerance
- Determine how critical uptime is for your system and what kind of fault tolerance is necessary.
- **Key Consideration:**
  - How much downtime is acceptable accross regions (like multi-region deployment)?
  - What are the key failure points, and how will you  mitigate them (like load balancers, failover mechanisms)?

**Thought Process:** Systems that require high availability (like financial or healthcare systems) may require redundancy, replication, and automatic failover mechanisms, pushing you towards more fault-tolerance architectures like microservices. If downtime is acceptable, simpler architectures can be chosen.

#### 5. Decide on the Right Database and Data Management Strategy
Choose a data storage strategy that aligns with the system's performance, scalability, and consistency needs.
- **Key Consideration:** Will the system use a relational (SQL) or NoSQL database? This depends on whether data consistency or flexibility is more important.
- Will you need the data be partitioned? Will you need sharding to distribute data across multiple databases?
- Do you need strong consistency or can the system work with eventual consistency? And many more, i will explain some of theorem that will help us to choose database with CAP Theorem, and PACELC Theorem in another chapter.

**Though Process:** Large, distributed systems might benefit from NoSQL solutions with eventual consistency for performance, while highly transactional system (like banking) will favor SQL databases with ACID quarantees (will add another chapter to explain ACID). If the system deals with a lot of unstructured or semi-structured data, NoSQL databases may be more appropriate.

#### 6. Choose the Right Architecture Pattern
Based on the previous steps , we must select carefully the architecture pattern that best meets the system's requirements.
- **Key Considerations:**
  - **Monolithic:** Simple to build and deploy but harder to scale. Good for small applications or MVPs.
  - **Microservices:** More complex but allows for independent scaling, fault tolerance and flexibility. Suitable for large, complex systems.
  - **Event-Driven:** Useful for real-time data processing where components need to react to events.
  - **Layered Architecture:** Divides the system into layers (UI, business logic, data access), making it easier to manage but less scalable than microservices.


**Thought Process:** Match the architecture to complexity, scaling needs, and expertise of your team. For example, if you expect to iterate quickly and the project is small, a monolithic approach might be better, with an eye on refactoring to microservices later.

#### 7. Address Security Concerns Early On
Ensure the architecture incorporates the necessary security mechanism to protect the system.
- **Key Considerations:**
  - What kind of authentication and authorization is required? (like OAuth2, JWT, role-based access control)
  - How will sensitive data be protected (like encryption in transit and at rest)?
  - How will the system be protectedagainst threats like DDoS attacks, SQL injection or XSS?

**Thought Process:** How will users authenticate and what permissions will they have (authorization)?, What sensitive data needs encryption, and how will you manage encryption keys?, Security concerns may affect your choice of architecture: for example, a microservices architecture may require more robust distributed security measures.

#### 8. Consider the Development and Maintenance Effort
Think about how the system will evolve and how easy it will be to maintain and update.
- **Key Considerations:**
  - Modularity and Maintainability: Keep code modular to allow for easy changes and testing.
  - Team Expertise: What technologies and patterns are your team most comfortable with?
  - Documentation and Testing: Ensure the system is well-documented and has automated testing in place.

**Thought Process:** Choose an architecture that the development team can support effectively. If the team is new to microservices, a monolithic approach might be simpler at first. Keep the system modular to allow individual components to be updated or replaced without affecting the whole system.

#### 9. Evaluate Cost Implications
Estimate the costs of building, running and maintaining the system.
- **Key Considerations:**
  - Operational Costs: Cloud infrastructure (like AWS, Azure, GCP), bandwidth, database storage, server costs.
  - Development Costs: Complexity of building the system, time to market, team size.
  - Trade-offs: Cheaper systems may require more manul scaling, while costlier ones (like serverless) might offer better automation and scaling.

**Thought Process:** Can you afford dynamic scaling via cloud services, or should you manage infrastructure manually?. Consider the trade-off between upfront costs vs long-term operational savings (like microservices might be costly upfront but save money in scaling later).

#### 10. Select the Right Architecture Pattern
Based on all the previous steps, choose the architecture that best fits your needs.
- **Key Considerations:**
  - **Monolithic:** Simple to build but difficult to scale and maintain as the system grows.
  - **Microservices:** More complex but allows independent services to scale, update and maintain.
  - **Event-Driven:** Useful for real-time, low-latency systems that need to react to events.
  - **Serverless:** Reduces operational overhead and scales automatically, but might be more expensive depending on usage.
  - and *many more*
  
**Thought Process:** Choose monolithic for simpler, smaller or MVPs with low complexity. Opt for microservices if scalability, independent deployment, and fault isolation are priorities. Event-Driven architecture are ideal for systems requireing real-time, asyncronous processing.

#### 11. Plan for Monitoring, Observability and Maintainance
Design the system to be easily monitored and maintainable, with observability in place from the start.
- **Key Considerations:**
  - **Monitoring Tools:** Use tools like Prometheus, Grafana, or New Relic to monitor system health, performance and usage.
  - **Logging:** Implement centralized logging if possible (like ELK Stack) to track errors and events.
  - **Automated Alerts:** Set up alerts for critical system failures or performances issues like Pager Duty.
  
**Thought Process:** Observability is critical in modern, distributed systems. Ensure you can detect issues before they impact users. In microservices architectures, distributed tracing (like Jaeger) is essential to track requests across multiple services. Design for easy maintenanceby automating updates and patches where possible.


>**The right architecture is often a balance of multiple factors, and it's essential to prioritize based on the system's goals and future growth.**