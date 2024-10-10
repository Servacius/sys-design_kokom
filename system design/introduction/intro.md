## System Design Mastery

### *What is System Design?*
System design has become a required skill for software developers and IT proffessionals. The term 'system design' refers to step by step process of defining the architecture, modules, data, component, and interface for a system to satisfy specified requirements. We can say that it's a preplanned archirtectural structure of the software.

### *Why we learn system design?*
There are some multiple obvious reasons why we learn how to design a system:

1. **Create blueprint for development**
So the pre-design of the system will work as a blueprint that developers/teams can follow before write the code. 
2. **To achieve efficiency and cost-effectiveness**
A thoughful and well-designed system is more efficient than other system and can lead to cost savings by effeciently managing the resources of the systems. ***Remember*** investing in scaling before it is needed is sometime not a smart business proposition, however, some forethought into the design can save valuable time and resources in the future.

### *How to: System Design?*
- **Understand the problem**: Have an understanding about the problem you are trying to solve by gather the information, identify users/client needs and the constraint or limitation of the system that we want to build
- **Identify the scope of the system**: Define the scope of the system, either what the system can do and cannot do.
- **Research and analyze existing systems**: We can learn from similar system that worked well in the past or in the current system, and use it to make a decision for designing a system.
- **Create high-level design**: We start with describing the component of the system and how the components will react each other. This inclue a rough diagram of the system architecture or a flowchart oulining the fow.(Note: high-level Design describe how everything works as a single organism. And low-level design describe each one organ or part in detail.)
- **Refine the design**: As we work on the details of the system we refine it couple of times until we have complete and detailed design that meets all the requirements
- **Remember to document the design** : Create detailed documentation of the design for future reference so that its can be maintain
- **Continuously monitor and improve the system**
  

### Common Principles of System Design
Here is some common system design concepts that every developer should know and some of it will be topics that we used later as a trade-off when we decide the architecture:
1. Scalability
2. Reliability and Fault Tolerance 
3. Availability
4. Maintainability
5. Performance Optimization
6. Separation of Concerns
7. Security
8. Consistency and Data Integrity
9. Resilience
10. Monitoring and Observability
11. Cost Efficiency

#### 1. Scalability
Scalability refers to the systems ability to handle the increased workload and user demand without a significant decrease in performance. There are two types of scaling.
- Vertical scaling: It requires to upgrade the current servers or machines
- Horizontal scaling: It requires adding a few more servers or nodes.

**Why it matters** : Systems are often built with future growth in mind. Over time, user demand and data loads increase, and the system should handle this growth without performance degradation.
#### 2. Reliability and Fault Tolerance
Realibility measures if the system works as expected without crashes
Fault tolerance onvolves designing a system to continue functioning even in the precense of hardware failures, software bugs or other unexpected errors.

**Why it matters** : Systems inevitablt encounter issues, from network failures to hardware malfunctions. Your system shold "fail gracefully" instead of going down completely.
#### 3. Availability
Availability refers to the readiness and accessibility of a system or service to users at any given time or how much time the system is operational and available to users.

**Why it matters** : Users expect systems to be aavilable almost all the time, even in the face of failure, for example : What happens when a server crashes? How does the system recover? We can build redundancy through multiple servers, data replication and failure mechanisms, to ensure that if a component fails, another one takes over seamlessly.
#### 4. Maintainability
Maintainability focuses on making systems easy to maintain, troubleshoot, and update throughout the system development. High maintainability can be achieved by well-documented code, modular architecture, and version control practices.
And make the developer take less time and effort to understand the system.

**Why it matters** : Over time, systems evolve-features are added, bugs are fixed and performance improvements are made. A maintainable system is easier to update without introducing new issues. We can handle this by writing a clean, modular code adhering to established best ppractices and patterns (like SOLID principles, etc), use version control, continuous integration and continuous deployment to maintain and improve the system over time.
#### 5. Performance Optimization
Performance optimization involves designing a system with high response time annd optimal throughput while using the available resources, queries optimizeed, etc. Consider the trade-offs: sometimes optimizing performance might comppromise maintainability or consistency, so it's about balancung different priorities.

**Why it matters** : Users expect system to be fast and responsive, with minimal delays.
#### 6. Separation of Concerns
Devide our system into different layers, tipically presentation UI, business logic and data access layers, and many more. This separation makes the system more flexible ; changes to one concern don't ripple through unrelated areas.

**Why it matters** : Mixing responsibilites in a system leads to tangled logic that's hard to manage.
#### 7. Security
Just like the title its about the user ans system security, it involves protecting the system from attacks, unauthorized access and data breaches. how can unauthorized users be prevented from accessing the system? Implement strong authentication and authorization (e.g., OAUTH2, JWT tokens). We protect the transmitted data by encrypt it using HTPPS.

**Why it matters** : Protecting user data and preventing unauthorized access are fundamental, especially for sensitive data like personal information or financial records.
#### 8. Consistency and Data integrity
Consistency refers to the same data being populated & retrieved across all the nodes at any given point in time. In a distributed system, we are have to choose between strong consistency (data is always syncronized or real time data is sync accross all nodes) and eventual consistency (data will eventually syncronized). Use transaction management and proper database design to ensure data integrity.

**Why it matters** : Inconsistent or corrupted data can result in poor user experiences, failed transaction or system crashes. Evaluate this use case : Is consistency more critical (e.g banking transaction) or is it acceptable for some users lightly delayed data (e.g., e-commernce product availability)
#### 9. Resilience
Resilience is about how can the system handle overloads or temporary service failures. We can implement graceful degradation, where the system still works but with reduced functionality

**Why it matters** : Systems must continue to operate under stress or failures and recover quickly when thigns go wrong.
#### 10. Monitoring and Observability
Make sure to have a clear system for monitoring , ensure that metrics that matter the most being tracked. Use logs, tracing and metrics to get a full picture of system behavior and identify potential bottlenecks or failure points.

**Why it matters** : Without visibility into how the system is performing, you can't diagnose problems or optimize its performance.
#### 11. Cost Efficiency
When we talk about designing system of course we won't far from cost money. So we must consider autoscaling to meet demand dynamically instead of provisioning excess capacity that sits idle. Looks for ways to reduce costs without compromising performance.

**Why it matters** : Resources like servers, storage, and bandwith cost money, so systems need to balance performance, reliability, and cost.

> Each of these principles balances trade-offs and constraints to meet the system's goals. The art of system is figuring out which principles are most important based on the system's context and business requirements.