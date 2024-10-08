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
6. Modularity
7. Security and Privacy
8. Data Privacy and Ethics
9. Encaptulation and Abstraction
10. Document Everything

#### 1. Scalability
Scalability refers to the systems ability to handle the increased workload and user demand without a significant decrease in performance. There are two types of scaling.
- Vertical scaling: It requires to upgrade the current servers or machines
- Horizontal scaling: It requires adding a few more servers or nodes.
For example: E-commernce stores handle millions or billions of monthly active users. In the festival the trafic will increased, and need to be vertical and horizontal scaling to handle the increased number of users while maintaining the performance of their website or application.
#### 2. Reliability and Fault Tolerance
Realibility measures if the system works as expected without crashes
Fault tolerance onvolves designing a system to continue functioning even in the precense of hardware failures, software bugs or other unexpected errors.
#### 3. Availability
Availability refers to the readiness and accessibility of a system or service to users at any given time or how much time the system is operational and available to users.
Example: Platforms like Netflix or Payment service ensure that their system is highly available and their user can access the content every time. Application like that rely on load balancing and db replicas to handles failure.
#### 4. Maintainability 