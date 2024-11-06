

# Guideline
- [Guideline](#guideline)
- [Goal](#goal)
- [Types](#types)
- [Architectures](#architectures)
- [Authentications](#authentications)
- [Authorizations](#authorizations)
- [Protocols](#protocols)
- [Video References](#video-references)


# Goal

# Types

Microservices, SOA (Service-Oriented Architecture), and Monolithic Architecture are three different architectural approaches that can be used for developing software applications. 

**Monolithic Architecture** is a traditional approach where the entire application is developed as a single, cohesive unit. All the components of the application are tightly coupled and run in the same process. It can be easier to develop and test a monolithic application, but it can become difficult to maintain and scale as the application grows in size and complexity.

**SOA** is an architectural approach that focuses on creating reusable services that can be accessed by different applications. In SOA, services are loosely coupled and can be developed and deployed independently. This makes it easier to maintain and scale the application, as changes to one service do not necessarily affect other services. However, implementing SOA can be complex and requires a lot of effort in designing and managing the services.

**Microservices** is a more recent approach that is similar to SOA, but with a greater emphasis on small, independent services that are developed and deployed separately. Each microservice is responsible for a specific business function and communicates with other microservices through lightweight APIs. This approach allows for greater scalability and flexibility, as changes to one microservice do not affect the operation of other microservices. However, implementing a microservices architecture can also be complex due to the need for managing and coordinating the interactions between the different microservices.

In summary, each architecture has its benefits and drawbacks, and the choice of architecture depends on the specific needs of the application. Monolithic architecture can be a good fit for small applications with simple functionality, while SOA and microservices are more suitable for larger, complex applications that require scalability and flexibility.

# Architectures
Microservice architectures can be categorized into various structural patterns based on their design principles and communication patterns. Here are some of the common categories of microservice structures:

- Domain-Driven Design (DDD)
- API Gateway
- Event-Driven Architecture (EDA)
- Data-Driven Architecture (DDA)
- Function-Driven Architecture (FDA)
- Hybrid Architecture


1. **Domain-driven microservices:** These microservices are organized around business domains and encapsulate the business logic and data for those domains. They are designed to model the business domain in a way that reflects the language and concepts of the domain experts. They often use domain-driven design principles such as bounded contexts, aggregates, and entities to define the boundaries and interactions of the microservices.

2. **Event-driven microservices:** These microservices use an asynchronous, event-based communication pattern to handle complex workflows and processes. They often use a message broker to distribute events between microservices and can be designed to be resilient to failure and scale dynamically.

3. **API-driven microservices:** These microservices provide an interface for other services and applications to communicate with the microservices architecture. They are designed to be self-contained and independent, with a well-defined API that can be easily consumed by other services.

4. **Data-driven microservices:** These microservices are organized around specific data sets and are responsible for storing and managing those data sets. They can be designed to be highly scalable and often use modern data stores such as NoSQL or distributed databases.

5. **Function-driven microservices:** These microservices are organized around specific functions or tasks, such as image processing or data transformation. They can be designed to be highly specialized and often use serverless or function-as-a-service platforms such as AWS Lambda or Google Cloud Functions.

6. **Hybrid microservices:** These microservices combine multiple structural patterns to create a more flexible and adaptable architecture. For example, a microservice might be both domain-driven and event-driven, or both data-driven and function-driven, depending on its specific requirements.

These categories are not mutually exclusive, and microservice architectures often combine multiple structural patterns to create a more flexible and adaptable architecture. The choice of structural pattern depends on the specific requirements and constraints of the project, as well as the expertise and preferences of the development team.


# Authentications

Authentication is a critical aspect of microservices architecture, as it ensures that only authorized users or services can access the microservices. Here are some possible ways of handling authentication in microservices:

1. Token-based Authentication: Token-based authentication is a popular mechanism for securing microservices. It involves generating a token (such as a JSON Web Token or JWT) that contains information about the user or service, which is then used to authenticate subsequent requests. The token is usually signed and encrypted to prevent tampering.

2. OAuth 2.0: OAuth 2.0 is an open standard for authentication and authorization that is commonly used in microservices architectures. It allows users to grant third-party applications access to their resources without sharing their credentials, by generating access tokens that are validated by the microservices.

3. Mutual TLS (mTLS): Mutual TLS is a security mechanism that involves using Transport Layer Security (TLS) certificates to authenticate both the client and the server. It ensures that the client is who it claims to be and that the communication between the client and the server is encrypted and secure.

4. API Gateways: An API gateway can act as a central authentication and authorization point for microservices. It can authenticate users or services using various methods, such as OAuth 2.0 or mTLS, and then route the requests to the appropriate microservices.

5. Single Sign-On (SSO): Single sign-on is a mechanism that allows users to authenticate once and then access multiple microservices without having to authenticate again. It can be implemented using various standards and protocols, such as SAML or OpenID Connect.

6. Custom Authentication: In some cases, it may be necessary to implement a custom authentication mechanism that is tailored to the specific requirements of the microservices architecture. This can be more complex and time-consuming, but it allows for greater flexibility and control over the authentication process.

When designing an authentication mechanism for microservices, it's important to consider factors such as security, scalability, and ease of use. It's also important to keep in mind that authentication is just one part of a comprehensive security strategy, which should also include measures such as authorization, encryption, and monitoring.


# Authorizations
Authorization is the process of determining whether a user or service is allowed to perform a particular action or access a particular resource. Here are some ways to handle authorizations in microservices:

1. Role-based Access Control (RBAC): RBAC is a common approach to authorization, where users or services are assigned roles that define their permissions. Each role is associated with a set of permissions, which determine what actions or resources the user or service can access. The microservices can then check the user or service's role when processing requests and grant or deny access accordingly.

2. Attribute-based Access Control (ABAC): ABAC is a more fine-grained approach to authorization, where access decisions are based on attributes of the user or service, such as their department, location, or job title. ABAC policies define rules that specify which attributes are required for accessing particular resources or performing particular actions. The microservices can then evaluate the attributes of the user or service when processing requests and grant or deny access accordingly.

3. Policy-based Access Control (PBAC): PBAC is a flexible approach to authorization, where access decisions are based on policies that define the conditions under which access is granted or denied. Policies can be defined using a variety of factors, such as user roles, attributes, time of day, and more. The microservices can then evaluate the policies when processing requests and grant or deny access accordingly.

4. Attribute-based Encryption (ABE): ABE is a technique that encrypts data using attributes of the user or service, such as their department or job title. Only users or services with the appropriate attributes can access the encrypted data.

When implementing authorization in microservices, it's important to consider factors such as scalability, performance, and security. It's also important to define clear policies and rules for access control and to regularly review and update them to ensure they remain effective and up-to-date. Additionally, it's important to implement proper logging and monitoring to detect and respond to unauthorized access attempts.


# Protocols

There are several protocols that are commonly used in microservices architecture. Here are some of the most common ones and their reasons for being used:

1. REST (Representational State Transfer): REST is a lightweight protocol that is commonly used in microservices architecture for communication between services. It is based on HTTP and uses simple, standardized methods (such as GET, POST, PUT, and DELETE) to access and manipulate resources. REST is often used because it is easy to implement, scalable, and can be used by a wide variety of clients and programming languages.

2. gRPC: gRPC is a high-performance, open-source protocol that is designed for communication between microservices. It uses Protocol Buffers, a binary serialization format, and supports multiple languages. gRPC is often used because it is fast, efficient, and supports bidirectional streaming, which allows for real-time communication between services.

3. GraphQL: GraphQL is a query language and runtime that is commonly used in microservices architecture for querying and manipulating data. It allows clients to specify the data they need and the shape of the response, which can reduce the amount of data transferred over the network. GraphQL is often used because it is flexible, efficient, and can be used to unify data from multiple microservices.

4. Apache Kafka: Apache Kafka is a distributed streaming platform that is commonly used in microservices architecture for event-driven communication between services. It allows services to publish and subscribe to events in real-time, which can help to decouple services and improve scalability. Apache Kafka is often used because it is fast, scalable, and supports high-throughput, real-time messaging.

5. AMQP (Advanced Message Queuing Protocol): AMQP is a messaging protocol that is commonly used in microservices architecture for reliable, asynchronous communication between services. It supports multiple messaging patterns, such as point-to-point and publish-subscribe, and can be used with a variety of messaging brokers. AMQP is often used because it is reliable, scalable, and can be used to integrate with legacy systems.

The choice of protocol depends on the specific requirements and characteristics of the microservices architecture, such as performance, scalability, and the need for real-time communication or event-driven architecture. It's important to choose a protocol that meets the needs of the architecture and is well-supported by the tools and frameworks being used.


# Video References
- what is microservice and when to use? (https://www.youtube.com/watch?v=lTAcCNbJ7KE&t=200s)
- what is api Gateway in microservice workflow? (https://www.youtube.com/watch?v=6ULyxuHKxg8)
- 