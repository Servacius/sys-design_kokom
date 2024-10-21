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
=======

#### 5. 