## How to design system
>*'Picking the "**right**" architecture = Picking the right battles + Managing trade-offs' by [Primal Skill](https://primalskill.blog/wins-and-trade-offs-in-software#:~:text=Picking%20the%20%22right%22%20software%20architecture%2C%20for%20example%2C%20is%20like%20picking%20the%20right%20battles%20and%20then%20managing%20the%20trade%2Doffs)*

Choosing the right system design or architecture requires careful consideration of various factors. The process involves understanding both the technical and business requirements, followed by balancing trade-offs in scalability, performance, security, and maintainability. Here's a structured approach to help guide your thought process when deciding the right system design:

#### 1. Understand Business Requirements
- **Identify the key features :** It is about what functionality must the system provide? This includes the core use cases, expected user interactions, and essential workflows.
- **Clarify the bob-functionale requirements (NRFs):** This includes factors like:
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
