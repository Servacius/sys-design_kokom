## How to design system
>*'Picking the "**right**" architecture = Picking the right battles + Managing trade-offs' by [Primal Skill](https://primalskill.blog/wins-and-trade-offs-in-software)*

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