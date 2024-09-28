# Questions

##### bff - design pattern
The BFF (Backend for Frontend) design pattern is an architectural pattern that is commonly used in microservices-based systems. It involves creating a dedicated backend service specifically tailored to the needs of a frontend application or client.
issue - Each mocriservice is responsible for a specific business capability and exposes its own API. For frontend, it can be challenging to consume multiple microservices directly, as it may result in increased complexity, performance issues, and tight coupling between the frontend and backend.
Advantage
- The BFF acts as a proxy between the frontend and the backend microservices, providing a dedicated API that is optimized for the frontend's requirements. It encapsulates the complexity of aggregating data from multiple services, handling authentication and authorization, and adapting the responses to fit the frontend's needs.
##### 3 level api design - Use LinkGenerator class in Microsoft.AspNetCore.Routing
1. Presentation Layer
2. Business Logic Layer
3. Data Access Layer
##### microsoft api design guidelines
1. Consistency: APIs should follow consistent naming conventions, parameter ordering, and error handling patterns. This helps developers understand and use the APIs more easily.
2. Simplicity: APIs should be designed to be simple and focused, providing only the necessary functionality. Avoid unnecessary complexity or exposing implementation details.
3. Clarity: APIs should have clear and descriptive names for methods, properties, and parameters. Use meaningful and self-explanatory names to make the API intentions clear.
4. Versioning: Plan for future changes and consider versioning strategies to ensure backward compatibility and smooth transitions when introducing breaking changes.
5. Error Handling: Provide clear and meaningful error messages and use appropriate HTTP status codes to indicate the outcome of API requests. Handle errors consistently across the API.
6. Security: Implement secure authentication and authorization mechanisms to protect sensitive data and resources. Follow security best practices, such as using HTTPS for secure communication.
7. Performance: Optimize API performance by minimizing unnecessary round trips, reducing payload sizes, and implementing caching mechanisms where applicable.
8. Documentation: Provide comprehensive and up-to-date documentation for the API, including usage examples, code samples, and explanations of behavior and limitations.
9. Testing and Validation: Thoroughly test and validate the API to ensure its correctness, reliability, and robustness. Consider unit testing, integration testing, and user acceptance testing.
##### post patch put
- POST is used for creating new resources.
- PATCH is used for partial updates to existing resources.
- PUT is used for complete replacements or updates to existing resources.
##### middlewares
Function which handle http request or http response
##### event emitter - angular

##### ci/cd, jenkins, lamda
##### onion architecture -nopcommerce
It is a layered approach that aims to separate concerns and dependencies within the application.
1. Core Layer:
- Business entities: Classes representing core domain concepts like products, customers, orders, etc.
- Interfaces: Contracts defining the operations and behaviors that other layers can rely on.
- Services: Implementations of business logic and operations specific to the e-commerce domain.
2. Infrastructure Layer:
- Data access components: Repositories or data access objects (DAOs) responsible for interacting with the database or other data sources.
- External services integrations: Classes handling communication with external systems like payment gateways, shipping providers, or email services.
- Caching mechanisms: Components for caching frequently accessed data to improve performance.
- Logging: Utilities for logging application events and errors.
3. Application Layer:
- Controllers: In the case of nopCommerce, ASP.NET Core MVC controllers that handle user requests, perform input validation, and orchestrate interactions between the presentation layer and the core layer.
- View models: Classes representing the data required by the views to render the UI.
- Application services: Classes that encapsulate application-specific logic, such as managing shopping carts, processing orders, or handling user authentication.
4. Presentation Layer:
- Views: Razor views or other UI templates responsible for rendering the user interface.
- Controllers (part of the presentation layer): Handle user interactions, retrieve data from the application layer, and pass it to the views for display.
- UI components: Reusable UI elements like navigation menus, product listings, or shopping cart widgets.

##### Object class - functions
Object is the base class for all other classes
Here are some commonly used functions and methods provided by the Object class in C#:
1. ToString():
The ToString() method returns a string representation of the object. By default, it returns the fully qualified name of the class.
2. Equals(object obj):
The Equals() method compares the current object with the specified object for equality. By default, it checks if the two objects refer to the same memory location. However, this method is often overridden in derived classes to provide custom equality comparisons based on specific attributes or properties.
3. GetHashCode():
The GetHashCode() method returns a hash code value for the object. The hash code is typically used in data structures like hash tables to efficiently store and retrieve objects.
4. GetType():
The GetType() method returns the Type object that represents the runtime type of the current instance. It can be used to obtain information about the class, such as its name, base class, implemented interfaces, etc.
5. MemberwiseClone():
The MemberwiseClone() method creates a shallow copy of the current object. It copies the values of all fields from the original object to the new object. If a deep copy is required, a custom cloning mechanism should be implemented.
6. Finalize():
The Finalize() method is called by the garbage collector before an object is reclaimed. It can be overridden to perform any necessary cleanup or resource release operations.
##### Delegate and it types
It allows you to treat methods as first-class objects, which means you can pass methods as parameters, store them in variables, and invoke them dynamically
Delegates are often used to implement event handling, callbacks, and asynchronous programming.
Types of Delegates:
- Single cast
- Multicast
- Generic Delegates
  - Func<para1, para2, returntype> or Func<T, TResult>
  - Action<T> : return type is void
  - Predicate<T> : return type is true or false
##### angualr pacakges
##### Restrict api request of different region
1. IP-based Filtering:
- Obtain the IP address of the incoming request using
HttpContext.Connection.RemoteIpAddress
in ASP.NET Core or
HttpContext.Current.Request.UserHostAddress
in ASP.NET.
- Create a whitelist or blacklist of IP ranges or specific IP addresses for the allowed or restricted regions.
- Compare the incoming IP address with the whitelist or blacklist to determine whether to allow or deny the request.
- If the IP address is not within the allowed range, return an appropriate HTTP response (e.g., 403 Forbidden) to restrict access.
2. Geolocation Service:
- Use a geolocation service or API (such as MaxMind GeoIP2 or IP2Location) to determine the country or region of the incoming request based on its IP address.
- Create a whitelist or blacklist of allowed or restricted countries or regions.
- Retrieve the geolocation information for the incoming request's IP address using the geolocation service.
- Check if the country or region of the request is within the allowed list. If not, return an appropriate HTTP response to restrict access.

On Cloud side:
1. Virtual Network (VNet) Peering
2. Network Security Groups (NSGs)

##### Difference between List and Array
1. Size flexibility:
- Arrays have a fixed size that is determined at the time of declaration and cannot be changed later. You need to specify the size explicitly.
- Lists, on the other hand, have a dynamic size and can grow or shrink as needed. They automatically resize themselves when elements are added or removed.
2. Memory allocation:
- Arrays allocate a contiguous block of memory to store elements. The memory is allocated in a single chunk, which can be more efficient in terms of memory usage.
- Lists internally use an array but provide a wrapper around it. When the list needs to grow beyond its current capacity, a new larger array is created, and the elements from the old array are copied to the new one. This resizing process incurs some overhead.
3. Flexibility in adding/removing elements:
- Arrays have a fixed size, so adding or removing elements requires creating a new array with the desired size and copying the existing elements. This can be inefficient if you frequently need to modify the collection's size.
- Lists provide methods like Add(), Remove(), and Insert() that allow you to easily add, remove, or insert elements at any position without worrying about resizing or shifting elements manually.
4. Performance:
- Arrays generally have better performance for random access and indexing since they provide direct access to elements using an index.
- Lists, being a wrapper around an array, also support indexing but may have slightly slower performance due to the additional layer of abstraction.
5. Additional functionality:
- Lists provide additional methods and properties that make working with collections easier, such as Count, Sort, Find, ForEach, etc.
- Arrays have fewer built-in methods and require more manual coding for common operations.
##### 4 Maturity Levels of REST API Design
- Level 0 - The Swamp of POX (Plain Old XML) - Url should not have underscore instead use - one url
- Level 1 - Resources - different urls to interact with different resources
- Level 2 - HTTP Verbs - Get, Post, Put, Patch, Delete - Headers - Query Parameters - Status Codes
- Level 3 - Hypermedia Controls - Content Negotiation (Accept, Content-Type) - HATEOAS (Add ralated links in response for explorable) - Versioning

##### Extensions method - WhereNot in linq
```cs
    public static IEnumerable<T> WhereNot<T>(this IEnumerable<T> list, Func<T, bool> func1)
    {
        return list.Where( x => !func1(x));
    }

    public static IEnumerable<T> Where(this IEnumerable<T> list, Func<T, bool> func1)
    {
        foreach (var ele in list)
        {
            if (func1(ele))
                yield return ele;
        }
    }
```

##### Static Constructor
A static constructor is used to initialize any static data, or to perform a particular action that needs performed once only. It is called automatically before the first instance is created or any static members are referenced.

Static constructors have the following properties:

- A static constructor does not take access modifiers or have parameters.
- A static constructor is called automatically to initialize the class before the first instance is created or any static members are referenced.
- A static constructor cannot be called directly.
- The user has no control on when the static constructor is executed in the program.
- A typical use of static constructors is when the class is using a log file and the constructor is used to write entries to this file.
  ```cs
    public class Logger
    {
        private static StreamWriter logFile;
        static Logger()
        {
            logFile = new StreamWriter("log.txt");
        }
    
        public static void Log(string message)
        {
            logFile.WriteLine(message);
            logFile.Flush();
        }
    }
  ```
##### Type of constructor
- Default Constructor
- Parameterized Constructor
- Copy Constructor
- Static Constructor
- Private Constructor 

#### .Net Core
Open source, cross platform (independent of OS), a improved version of .net framework contains richer functionlaity.
##### .Net core and .Net framework difference
- Using core can't create Desktop application, supports web, mobile developement
- .Net framework needs .Net framework to be installed on windows
- .Net framework doesn't support dependecy injection
- .Net core only supports Rest api service
- .Net core has good performance and scalability
- .Net core supports microserve architecture
##### Routing
- Mechanism to map request url to controller and action method
  Two types of Routing
  - Conventional Routing : We give pattern to match with url- using MapControllerRoute or MapDefaultControllerRoute middleware
  - Attribute Routing : [Route("")] attribute is used to define the routing. Used MapControllers middleare in program.cs
  - We can use both conventional and attribute routing in same application. If attribute route ([Route]) is not present then conventional routing will use
  - MapGet, MapPost, MapPut, MapDeleted are methods for Routing
##### Dependency Injection scopes/lifetimes
Singleton, Scoped, and Transient are different lifetimes or scopes used in dependency injection (DI) frameworks. They determine how instances of dependencies are created and managed within an application.
1. Singleton: In the Singleton lifetime, only one instance of a dependency is created and shared throughout the entire application.
2. Scoped: In the Scoped lifetime, a new instance of a dependency is created for each scope or request.
3. Transient: In the Transient lifetime, a new instance of a dependency is created every time it is requested.
##### Handle Global Exception
```cs
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
  if (env.IsDevelopment())
    app.UseDeveloperExceptionPage(); // will show exception page with stack trace
  else
    app.UseExceptionHandler("/error"); // For production, call custom api "/error"
}
```
##### Logging
Logging log data into console if project runs through console, log into output window of visual studio, also log into file using logging framework Nlog and Serilog.
##### Identity
Identity is a membership system that provides authentication and authorization functionalities for web applications. It simplifies the process of managing user accounts, roles, and permissions.
Identity allows you to easily add user registration, login, and password management features to your application. It also provides features like account confirmation, password reset, two-factor authentication, and external authentication providers (e.g., Microsoft, Google, Facebook).
- Package: Microsoft.AspNetCore.Identity
```cs
public void ConfigureServices(IServiceCollection services)
{
  // Other service configurations
  services.AddDbContext(options => options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
  services.AddDefaultIdentity(options => options.SignIn.RequireConfirmedAccount = true)
  .AddEntityFrameworkStores();
  // Other service configurations
}
```
Create a new `ApplicationDbContext` class that inherits from `IdentityDbContext`
#### Microservice
A microservice is an architectural style that structures an application as a collection of small, loosely coupled, and independently deployable services. Each service focuses on a specific business capability and communicates with other services through well-defined APIs.
1. Scalability: Microservices allow individual services to be scaled independently based on their specific needs. This enables better resource utilization and the ability to handle varying levels of load efficiently.
2. Flexibility and Agility: Microservices promote flexibility and agility in development. Since each service is independent, teams can work on different services simultaneously, using different technologies and programming languages. This allows for faster development, deployment, and updates without impacting the entire application.
3. Fault Isolation: In a monolithic application, a single bug or failure can bring down the entire system. With microservices, failures are isolated to individual services, reducing the impact on the overall application. It also makes it easier to identify and fix issues since services are smaller and more focused.
4. Independent Deployment: Microservices can be deployed independently, allowing for continuous delivery and deployment. This means that updates or bug fixes can be rolled out to specific services without affecting the entire application. It also enables A/B testing and gradual feature rollout.
5. Technology Diversity: Microservices allow for the use of different technologies and frameworks within the same application. Each service can choose the most appropriate technology stack for its specific requirements. This flexibility enables teams to leverage the best tools and technologies for each service.
6. Team Autonomy: Microservices enable teams to work independently on different services. Each team can have ownership and autonomy over their respective services, making it easier to manage and scale development efforts. This also promotes faster decision-making and reduces dependencies between teams.
7. Resilience and Fault Tolerance: Microservices architecture promotes resilience by isolating failures and providing fault tolerance. If one service fails, it does not bring down the entire application. Services can be designed to handle failures gracefully and recover quickly.
8. Improved Maintainability: With smaller and more focused services, it becomes easier to understand, test, and maintain the codebase. Changes or updates to a specific service have minimal impact on other services, reducing the risk of introducing bugs or breaking functionality.

- Cons: While microservices architecture offers several advantages, it also has some potential drawbacks that need to be considered:
1. Increased Complexity: Microservices introduce additional complexity compared to monolithic architectures. Managing a distributed system with multiple services requires careful coordination and monitoring. The complexity of inter-service communication, data consistency, and deployment can be challenging to handle.
2. Operational Overhead: With multiple services, there is an increased operational overhead. Each service needs to be deployed, monitored, and managed independently. This can require additional infrastructure, tools, and expertise to ensure the smooth operation of the entire system.
3. Distributed System Challenges: Microservices rely on network communication between services. This introduces challenges such as latency, network failures, and service discovery. Ensuring reliable communication and handling failures gracefully can be complex.
4. Data Consistency: Maintaining data consistency across multiple services can be challenging. As each service has its own database, ensuring data integrity and synchronization becomes more complex. Implementing distributed transactions or eventual consistency patterns may be necessary.
5. Service Dependencies: Microservices often have dependencies on other services. Changes in one service may require corresponding changes in dependent services. Managing these dependencies and coordinating updates can be challenging, especially in large-scale systems.
6. Testing and Debugging: Testing and debugging in a microservices environment can be more complex. With multiple services interacting, it becomes important to test the integration between services, handle different service versions, and simulate various failure scenarios.
7. Development and Deployment Complexity: Developing and deploying microservices requires additional tooling and infrastructure. Continuous integration and deployment pipelines need to be set up for each service, which can increase development and maintenance efforts.
8. Performance Overhead: Microservices introduce additional network communication, which can impact performance compared to a monolithic architecture. The overhead of inter-service communication and potential latency can affect response times and overall system performance.
9. Learning Curve: Adopting microservices requires a shift in mindset and new skills for developers and operations teams. Understanding the principles, best practices, and tools associated with microservices architecture may require a learning curve and additional training.
##### Sync and Async communications
1. Sync Communication: example rest api, will wait for response
2. Async Communication: example message queue, apache kafka
  There are two types of messaged base communication
  - Point to Point: it has one producer which produces the message and the only one reciever consumes it, after consumed the message deleted automatically. ex. message queue, Rabbit MQ, AWS SQS
  - Publisher and Subscriber: it has one publisher which publishes the message and send it to the topic and have multiple subscribers which consume the message. ex. Kafka, AWS SNS
In message base communication, producer and consumer must know the message structure/format of the communication.
Event Based Async communication, the consumer don't need to know about the details of the message.
##### SAGA Design Pattern
The SAGA design pattern is a way to manage distributed transactions in a microservices architecture. It helps maintain data consistency across multiple services by coordinating a series of local transactions.
Problem Trying to resolve
- Lets say we are ordering food from zomato/swiggy: Choose your food > Add to cart and checkout > Make payment > order gets delivered > Mark order as completed
- In monolythic if any one of the operation failed we can rollback easily due to same transaction
- But in microservice we have different services with different database, if lets say coukdn't able to deliver the order due to unavailability of delivery guys. In this case rollback from all microservice its difficult.
- We use SAGA in this case. 
The SAGA pattern addresses this by breaking down a long-running transaction into a series of smaller, local transactions. Each local transaction represents a step in the overall business transaction. If any step fails, compensating actions are performed to undo the changes made by previous steps. So we reverted all the changes. In distributed rollback is not possible so we kind of undo the changes.
![image](https://github.com/user-attachments/assets/0f4c7b8c-ee73-42d1-b8ed-32b9a93fb46e)
There are two types of SAGA implementation
1. Choreography: communicate with other service using single common message broker. Advantages: Easy to implement, doesn't introduce a single point of failure. Disadvantage: backtracting is very difficult, who calls whom, risk of cyclic dependency.
2. Orchestrator: It handles all the trasaction and tells participant which operation to perform based on the event. Disadvatges: single point of failure, design complexity
##### CQRS Design Pattern
CQRS (Command Query Responsibility Segregation) is a design pattern commonly used in microservice architectures. It separates the responsibilities of handling commands (write operations) and queries (read operations) into separate components.
CQRS architecture provides a solution by separating the responsibilities of write and read operations, enabling scalability, performance optimization, and flexibility in complex applications like e-commerce systems.
##### How to handle data consistency in microservice architecture
- Sychronous communication
- Asynchronous communication
- CQRS
- Event sourcing : Serires of events like order is placed then add order, which triggers payment event. and if payament failed it triggers rollback of order
- Distributed transaction / 2 pahse commit - uses synchronous communication
- SAGA Pattern - uses asynchronous communication
##### 2 phase commit (2PC)
In microservice architectures, distributed transactions can be implemented using the Two-Phase Commit (2PC) protocol. The 2PC protocol is a coordination mechanism that ensures atomicity and consistency across multiple services involved in a distributed transaction.
Here's how the 2PC protocol works:

1. Coordinator: There is a coordinator service that initiates and manages the distributed transaction. It acts as the central authority responsible for coordinating the participating services.
2. Participants: Each participating service involved in the transaction is called a participant. These participants can be individual microservices or databases.
3. Phase 1 - Prepare: The coordinator sends a prepare request to all participants, asking them to prepare for the transaction. Each participant checks if it can successfully execute the transaction and replies with either a vote to commit or a vote to abort.
4. Phase 2 - Commit or Abort: Based on the responses received in the prepare phase, the coordinator decides whether to commit or abort the transaction. If all participants voted to commit, the coordinator sends a commit request to all participants. If any participant voted to abort or if there was a failure during the prepare phase, the coordinator sends an abort request to all participants.
##### Difference between 2 PC and SAGA
2 Phase Commit | SAGA Pattern
--- | ---
Strong consistency | Eventual consistency
Synchronous | Asynchronous
Blocking | Non Blocking
Complexity | Simplicity
Performance overhead | Better performance
##### Reverse Proxy
A reverse proxy is a server or service that sits between client devices and web servers. It acts as an intermediary, receiving requests from clients and forwarding them to the appropriate backend servers. The response from the backend server is then sent back to the client through the reverse proxy.
The main purpose of a reverse proxy is to distribute incoming client requests across multiple backend servers, improving performance, scalability, and reliability. It can also provide additional functionality such as load balancing, caching, SSL termination, and security features like authentication and authorization.
Reverse proxies are commonly used in web applications, especially in scenarios where there is a need for high availability, fault tolerance, and efficient handling of client requests. They can be implemented as hardware appliances, software applications, or even as part of a web server software. Some popular reverse proxy solutions include Nginx, Apache HTTP Server with mod_proxy, and HAProxy.
##### Strategies use for logging and monitoring
In a .NET microservice environment, there are several strategies you can use for monitoring and logging. Here are some common approaches:
1. Application Logging: Implement structured logging within your microservices using a logging framework like Serilog or NLog. Configure log levels and log to a centralized location such as a file, database, or log management system. Include relevant information in logs, such as timestamps, request/response details, and contextual information.
2. Distributed Tracing: Use distributed tracing frameworks like OpenTelemetry or Application Insights to trace requests across multiple microservices. This allows you to visualize the flow of requests, identify bottlenecks, and troubleshoot performance issues.
3. Metrics Collection: Instrument your microservices with metrics libraries like Prometheus or StatsD to collect and expose key performance indicators (KPIs) such as response times, error rates, and resource utilization. Use a monitoring system like Grafana or Azure Monitor to visualize and alert on these metrics.
4. Health Checks: Implement health checks in your microservices to periodically verify their availability and functionality. Expose an endpoint that returns the health status of the service, including dependencies like databases or external services. Monitoring systems can then periodically query these endpoints to ensure the overall health of the system.
5. Log Aggregation and Analysis: Centralize your logs using tools like ELK Stack (Elasticsearch, Logstash, Kibana), Splunk, or Azure Monitor Logs. These tools allow you to aggregate logs from multiple microservices, search and filter logs, create dashboards, and set up alerts based on specific log patterns or anomalies.
6. Error Monitoring: Utilize error monitoring tools like Sentry or Raygun to capture and track exceptions and errors occurring within your microservices. These tools provide detailed error reports, stack traces, and notifications, enabling you to quickly identify and resolve issues.
##### Distributed Tracing
Distributed tracing is a technique used in microservices architectures to track and monitor requests as they flow through multiple services. It provides visibility into the entire request lifecycle, allowing you to understand how requests are processed across different services and identify any performance bottlenecks or errors.
In distributed tracing, a unique identifier, called a trace ID, is assigned to each incoming request. As the request passes through various services, each service adds its own span, which represents a specific operation or action within that service. This span contains information such as the start time, end time, duration, and any relevant metadata. Spans are linked together using the trace ID, creating a trace that represents the complete journey of the request.
By collecting and analyzing these traces, you can gain insights into the overall performance and behavior of your microservices. Distributed tracing helps you identify latency issues, understand dependencies between services, detect errors, and optimize the performance of your system.
To implement distributed tracing, you typically need a distributed tracing system or tool that can collect and aggregate trace data from different services. Popular distributed tracing systems include Jaeger, Zipkin, and OpenTelemetry. These systems provide libraries or agents that you can integrate into your microservices to automatically generate and propagate trace information.

