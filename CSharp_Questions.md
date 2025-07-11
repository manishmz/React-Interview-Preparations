# Questions

##### bff - design pattern
The BFF (Backend for Frontend) design pattern is an architectural pattern that is commonly used in microservices-based systems. It involves creating a dedicated backend service specifically tailored to the needs of a frontend application or client.
issue - Each mocriservice is responsible for a specific business capability and exposes its own API. For frontend, it can be challenging to consume multiple microservices directly, as it may result in increased complexity, performance issues, and tight coupling between the frontend and backend.
Advantage
- The BFF acts as a proxy between the frontend and the backend microservices, providing a dedicated API that is optimized for the frontend's requirements. It encapsulates the complexity of aggregating data from multiple services, handling authentication and authorization, and adapting the responses to fit the frontend's needs.
##### Iterator design pattern
Iterator is a behavioral design pattern that lets you traverse elements of a collection without exposing its underlying representation (list, stack, tree, etc.).
- Problem solved:
The Iterator Pattern solves the problem of iterating over a collection of objects without exposing the details of the collection's implementation. It decouples the client code from the internal structure of the collection, making it easier to iterate over different types of collections without modifying the client code.
##### Decorator design  pattern
- The decorator design pattern is a structural design pattern that allows you to add new behaviors or responsibilities to individual objects dynamically without altering their structure. It's a flexible alternative to subclassing for extending functionality, allowing you to add or remove features at runtime. 
- Extending a class is the first thing that comes to mind when you need to alter an object’s behavior. However, inheritance has several serious caveats that you need to be aware of.
Inheritance is static. You can’t alter the behavior of an existing object at runtime. You can only replace the whole object with another one that’s created from a different subclass.
Subclasses can have just one parent class. In most languages, inheritance doesn’t let a class inherit behaviors of multiple classes at the same time.
One of the ways to overcome these caveats is by using Aggregation or Composition  instead of Inheritance. Both of the alternatives work almost the same way: one object has a reference to another and delegates it some work, whereas with inheritance, the object itself is able to do that work, inheriting the behavior from its superclass.
https://refactoring.guru/design-patterns/decorator
![image](https://github.com/user-attachments/assets/cf1d55dc-1c93-4fc4-a86f-26a38ecdfdb3)
![image](https://github.com/user-attachments/assets/18e01335-5012-4709-b420-796066531034)
##### Command design pattern
https://refactoring.guru/design-patterns/command
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
  - Action<T> : return type is void, ex: Action<int, string>
  - Predicate<T> : return type is true or false, Predicate<int, string>
##### How are events are different from delegates
Events are encapsulation over delegates. they help to implement publisher/subscriber model
##### Covariance and Contravariance
- Covariance allows a method to return a more derived type than specified by the generic parameter.
  Keyword: out
  Used with: Generic interfaces and delegates
  Direction: Output (return values)
  ```
  IEnumerable<string> strings = new List<string>();
  IEnumerable<object> objects = strings; // Valid because of covariance
  ```
  Here, IEnumerable<out T> is covariant, so IEnumerable<string> can be assigned to IEnumerable<object>.
- Contravariance allows a method to accept parameters of a less derived type than specified by the generic parameter.
  Keyword: in
  Used with: Generic interfaces and delegates
  Direction: Input (method parameters)
  ```
  Action<object> actObject = obj => Console.WriteLine(obj);
  Action<string> actString = actObject; // Valid because of contravariance
  ```
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
- Using middleware
```cs
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
  if (env.IsDevelopment())
    app.UseDeveloperExceptionPage(); // will show exception page with stack trace
  else
    app.UseExceptionHandler("/error"); // For production, call custom api "/error"
}
```
- Using IExceltionFilter
  Create an exception filter class that implements the IExceptionFilter interface. This interface defines the OnException method, which is called when an exception occurs.
  Register the exception filter in the Startup.cs file of your ASP.NET Core application within the ConfigureServices method.
  ```cs
  public void ConfigureServices(IServiceCollection services)
  {
     services.AddControllers(options => { options.Filters.Add<GlobalExceptionFilter>(); });
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
##### How to scale microservices
1. Horizontal scaling: Add more instances of similar service, and add loadbalancer to distribute the request
2. Functional Decompositor: Split the service into multiple macro service based on functionality. eg: microserivce does searching + product listing + product availability then divide into three services searching, product lisiting + product availability
3. Data Partioning: Partition service based on data. eg: scale user service based on usernames, like 1st service will have data from A-M and other will have from N-Z.
##### API Gateway
- Lets say we have multiple services, now for client to communicate with multiple services it need to have all the endpoints to services. Instead of this we create a service called API Gateway which recieve request from client and call services as per need.
- Lets say I want product info contains data from different different services like orders, review + rating, inventory, shipping. Now instead of fetching data seperatly from each microservice from client, we will call gateway and then gateway will fetch data from microservices sync or parallely.
- Authentication, single place to do so for every api, no need to implement authentication in every microservices.
- SSL certificate, use https for API Gateway and for API Gateway to microservices we can use http without ssl, so no need to implement ssl certificate in every microservice. Also from API Gateway to microservices we can use different protocol.
- It also use load balancer
##### Service Registry
- Service Registry is service or database which contains all the endpoints (ipaddress and portno) to the microservices and their instances.
- So when new instance is register, microservice will communicte to service registry which will add new endpoint.
- Microservice pill servcie registry in intervals, if any intervals failed then service registry consider that the instance is dead and remove the entry.
##### Circuit Breaker
- a circuit breaker is implemented as a state machine that monitors the availability and health of a remote service or resource. It helps prevent cascading failures and provides fault tolerance by temporarily "breaking" the circuit and redirecting requests to an alternative path when the remote service is experiencing issues.
- The circuit breaker operates based on a set of predefined thresholds and rules. When the number of failures or errors exceeds a certain threshold within a specified time window, the circuit breaker trips and enters an open state. In this state, subsequent requests to the remote service are not forwarded, and instead, a fallback mechanism is triggered. The fallback mechanism can be used to return cached data, provide default values, or invoke alternative services.
- After a certain period of time, known as the "timeout" or "retry interval," the circuit breaker enters a half-open state. In this state, a limited number of requests are allowed to pass through to the remote service to check if it has recovered. If these requests succeed, the circuit breaker resets and returns to a closed state, allowing normal operation. However, if any of the requests fail, the circuit breaker re-enters the open state, extending the timeout period before retrying.
#### Scenario based questions
##### In web apis if we want to allow requests from only particular region, how we can achieve it
1. IP-Based Filtering:
- Obtain the IP address of incoming requests.
- Determine the region associated with each IP address. You can use a geolocation database or an IP-to-location mapping service to map IP addresses to regions.
- Maintain a whitelist or blacklist of IP addresses or regions that are allowed or denied access to your API.
- Before processing each request, check if the IP address or region of the request is allowed or denied based on your whitelist or blacklist.
- If the IP address or region is allowed, proceed with processing the request. Otherwise, return an appropriate error response or deny access.
2. Geolocation-Based Filtering:
- Extract the geolocation information from incoming requests. This information can be obtained from the user's browser or through other means such as headers or cookies.
- Determine the region associated with the geolocation information.
- Maintain a whitelist or blacklist of regions that are allowed or denied access to your API.
- Before processing each request, check if the region of the request is allowed or denied based on your whitelist or blacklist.
- If the region is allowed, proceed with processing the request. Otherwise, return an appropriate error response or deny access.
It's important to note that IP-based or geolocation-based filtering may not be foolproof as IP addresses can be spoofed or VPNs can be used to bypass these filters. Therefore, it's recommended to combine these filtering techniques with other security measures such as authentication and rate limiting to enhance the security of your web API.
##### Website is slow investigate the root cause and provide solution
1. on browser side - issues website is loading slow at start. Solution: use cdn for images and files, use lazy load for some pages
2. on server side - some apis are slow while retrieivng data or performing any operation. Solutions: use optimize code, redis cache, pagination, async (user don't need to wait for response). architecture solution is to use distrirbuted servers, if computation takes times try to do precomputation.
3. on database side - some queries are slow. Solutions: Optimize the query by removing unnecessary joins, fetch require columns and data, apply indexes on search column (single or multiple column), if database contains data not quering on it then archieve the data in another database, architecture solution is to use horizontal sharding
##### Event Driven
##### Kafka queue
Producers, Brokers, Topics, Partitions, Consumers
ack = 0, ack = 1, ack = all

#### SQL
##### ACID Properties
ACID is an acronym that stands for Atomicity, Consistency, Isolation, and Durability. These properties are fundamental principles in database systems, including SQL databases, to ensure reliable and transactional operations. Let's explore each property:
1. Atomicity: Atomicity guarantees that a transaction is treated as a single, indivisible unit of work. It means that either all the changes made within a transaction are committed, or none of them are. If any part of the transaction fails, the entire transaction is rolled back, and the database returns to its previous state.
2. Consistency: Consistency ensures that a transaction brings the database from one valid state to another. It enforces integrity constraints, such as data type validation, referential integrity, and other rules defined in the database schema. In other words, the database remains in a consistent state before and after the execution of a transaction.
3. Isolation: Isolation ensures that concurrent transactions do not interfere with each other. Each transaction should execute as if it is the only transaction running on the system. Isolation prevents issues like dirty reads (reading uncommitted data), non-repeatable reads (reading different values in the same transaction), and phantom reads (seeing new rows inserted by other transactions).
4. Durability: Durability guarantees that once a transaction is committed, its changes are permanent and will survive any subsequent failures, such as power outages or system crashes. The committed data is stored in non-volatile memory (usually disk storage) and can be recovered even in the event of a system failure.
##### Different types of keys
In SQL databases, there are several types of keys that can be used to establish relationships between tables and ensure data integrity. Here are some commonly used key types:
1. Primary Key: A primary key is a unique identifier for each record in a table. It ensures that each row in the table is uniquely identified and helps in maintaining data integrity.
2. Foreign Key: A foreign key is a field in one table that refers to the primary key in another table. It establishes a relationship between two tables and enforces referential integrity.
3. Unique Key: A unique key ensures that the values in a column or a set of columns are unique across all rows in a table. Unlike a primary key, a unique key can contain null values.
4. Composite Key: A composite key is a combination of two or more columns that uniquely identifies a record in a table. It is used when a single column cannot uniquely identify a record.
5. Candidate Key: A candidate key is a column or a set of columns that can be chosen as a primary key. It satisfies the uniqueness and non-nullability requirements of a primary key. A candidate key is any column or set of columns that can potentially serve as a primary key, while a primary key is the specific candidate key that is chosen to uniquely identify records in a table.
6. Alternate Key: An alternate key is a candidate key that is not chosen as the primary key. It can be used as a unique identifier for a record.
#### Difference between Temp table and Temp variable
In SQL, temporary tables and table variables are used to store temporary data within a session or a specific scope. They are similar in concept but have some differences in terms of their usage and behavior.
1. Temporary Table:
   - A temporary table is a table that is created and exists only for the duration of a session or a specific transaction.
   - It is stored in the tempdb database and can be accessed by multiple users or sessions.
   - Temporary tables can be created using the CREATE TABLE statement and can have indexes, constraints, and other table properties.
   - They can be used to store intermediate results, perform complex calculations, or temporarily store data for further processing.
   - Temporary tables are automatically dropped when the session or transaction ends, or they can be explicitly dropped using the DROP TABLE statement.
2. Table Variable:
   - A table variable is a variable that can hold a result set or a table-like structure within a specific scope, such as a stored procedure or a batch of statements.
   - It is declared using the DECLARE statement, followed by the table structure definition.
   - Table variables are stored in memory and have a limited scope within the batch or procedure where they are declared.
   - They do not support indexes or constraints, and their structure cannot be altered once declared.
   - Table variables are useful for storing small to medium-sized result sets or intermediate data within a specific scope without the need for physical disk storage.
   - They are automatically deallocated when the scope ends.

In summary, temporary tables are physical tables that exist for the duration of a session or transaction, while table variables are variables that hold table-like structures within a specific scope. Temporary tables offer more flexibility and functionality, while table variables are lightweight and suitable for smaller data sets. The choice between them depends on the specific requirements and use case.
##### Difference between function and stored procedure
In SQL, both functions and stored procedures are database objects that can be used to encapsulate and execute a set of SQL statements. However, there are some key differences between them:
1. Purpose:
- Function: A function is designed to return a single value or a table variable as a result. It is typically used to perform calculations, transformations, or data manipulations and can be used in SQL queries as part of expressions or in SELECT statements.
- Stored Procedure: A stored procedure is used to group a set of SQL statements together to perform a specific task or operation. It can contain input and output parameters and can be used to modify data, retrieve data, or perform complex business logic.
2. Return Value:
- Function: A function must return a value or a table variable. It can be used in expressions or assigned to variables.
- Stored Procedure: A stored procedure does not have to return a value. It can modify data, perform operations, or generate output using output parameters or result sets.
3. Usage:
- Function: Functions are commonly used in SQL queries, such as in SELECT, WHERE, or JOIN clauses, to perform calculations or transformations on data.
- Stored Procedure: Stored procedures are often used to encapsulate complex business logic, perform data modifications, or execute a series of steps as a single unit of work.
4. Transaction Control:
- Function: Functions cannot modify data directly or perform transaction control statements like COMMIT or ROLLBACK. They are read-only and deterministic.
- Stored Procedure: Stored procedures can modify data, perform transaction control, and execute multiple SQL statements within a single transaction.
5. Execution:
- Function: Functions are called as part of an SQL statement or expression, and their results are immediately available.
- Stored Procedure: Stored procedures are executed using the EXECUTE or EXEC statement, and they can have input and output parameters.
In summary, functions are primarily used to return values or table variables and are often used in SQL queries, while stored procedures are used to group SQL statements together to perform specific tasks or operations and can modify data and perform complex business logic. The choice between them depends on the specific requirements and use case.
```sql
CREATE FUNCTION CalculateDiscount(@price DECIMAL(10,2), @discountRate DECIMAL(4,2))
RETURNS DECIMAL(10,2)
AS
BEGIN
  DECLARE @discountedPrice DECIMAL(10,2)
  SET @discountedPrice = @price - (@price * @discountRate)
  RETURN @discountedPrice
END
```
```sql
CREATE PROCEDURE GetRecordsByCategory
@category VARCHAR(50)
AS
BEGIN
  SELECT * FROM YourTable WHERE Category = @category;
END
```
##### TSQL query to get nth highest salary
using CTE (Common Table Expression)
```sql
with table1 (name, salary) as (	Select top(nth) name, salary from employee order by salary desc)
Select top 1 name from table1 order by salary;
```
```sql
with table1 as (
select name, salary, ROW_NUMBER() over (order by salary desc) as row_num from employee
)
select name, salary from table1 where row_num = nth
```
Instead row_number use dense_rank will give us the proper result if employee will have same salaries.
##### ROW_NUMBER
```
ROW_NUMBER ( )   
 OVER ( PARTITION BY col_1,col_2… ORDER BY col_3,col_4.. ASC or DESC) AS column_name
```
'Partion by' creates partion then row_number will gives row_numbers for every partition. 
example 'partition by section order by roll_no asc'
name | section | roll_number | row_number
--- | --- | --- | ---
Raju | A | 101 | 1
Shyam | A | 102 | 2
Minal | A | 103 | 3
Pooja | A | 104 | 4
Aarti | B | 201 | 1
Shubham | B | 202 | 2
Kartik | B | 203 | 3
##### ROW_NUMBER vs RANK vs DENSE_RANK
SALARY | ROW_NUMBER | RANK | DENSE_RANK
--- | --- | --- | ---
1000   | 1          | 1    | 1
1500   | 2          | 2    | 2
1500   | 3          | 2    | 2
2000   | 4          | 4    | 3
2200   | 5          | 5    | 4
2500   | 6          | 6    | 5
2500   | 7          | 6    | 5
2500   | 8          | 6    | 5
3000   | 9          | 9    | 6

Syntax are same for all just need to use rank, dense_rank or row_number
##### Execution plan viewer
### C# .net questions
##### new vs virtual vs override
##### IDisposable vs Descructor VS Finalize
In C#, IDisposable, destructors, and finalizers are mechanisms used for resource management and cleanup in object-oriented programming. Here's an explanation of each:
1. IDisposable:
- IDisposable is an interface in C# that defines a method called Dispose() which is used to release unmanaged resources held by an object.
- Classes that implement the IDisposable interface typically hold unmanaged resources such as file handles, database connections, or network sockets.
- The Dispose() method should be called explicitly by the consumer of the object to release these unmanaged resources when they are no longer needed.
- It is recommended to implement the IDisposable interface when a class holds unmanaged resources to ensure proper cleanup.
2. Destructor:
- In C#, a destructor is a special method defined in a class using the ~ClassName() syntax (e.g., ~MyClass()).
- Destructors are used for releasing unmanaged resources and performing cleanup tasks when an object is garbage collected by the .NET runtime.
- Destructors are non-deterministic, meaning you cannot predict when they will be called by the garbage collector.
- It is not recommended to rely on destructors for resource cleanup, as they are less predictable compared to the Dispose() method.
3. Finalize method:
- In C#, the Finalize() method is a special method that serves as the finalizer for a class. It is automatically called by the garbage collector before an object is reclaimed.
- The Finalize() method is used to release unmanaged resources and perform cleanup tasks similar to a destructor.
- It is important to note that the Finalize() method should be overridden only when necessary, as it adds overhead to the garbage collection process.
- The Finalize() method is typically used as a backup mechanism for releasing unmanaged resources if the Dispose() method was not called.
In summary:
- Use the IDisposable interface to implement resource cleanup for objects that hold unmanaged resources.
- Avoid relying on destructors for resource cleanup due to their non-deterministic nature.
- Use the Finalize() method as a backup mechanism for releasing unmanaged resources if the Dispose() method was not called.
Proper resource management is crucial in C# to prevent memory leaks and ensure efficient use of system resources.
##### Extension methods
```
public static class Extensions
{
  public static void RemoveAll<TKey, TValue>(this IDictionary<TKey, TValue> @this, Func<TKey, TValue, bool> predicate) =>
			@this.Keys
				.ToList()
				.Where(key => predicate(key, @this[key]))
				.ForEach2(key => @this.Remove(key));
}

public static bool IsNullOrEmpty([NotNullWhen(false)] this string? @this) =>
			string.IsNullOrEmpty(@this);
```
##### Linq group by
```
  persons.Add(new Person { PersonID = 1, car = "Ferrari" }); 
  persons.Add(new Person { PersonID = 1, car = "BMW" }); 
  persons.Add(new Person { PersonID = 2, car = "Audi" });
  var res = persons.GroupBy(it => it.PersonID, it => it.car).Select(g => new {PersonID = g.Key, Cars = g.ToList()});
```
##### First vs Single
- First or First(x => //some condition) will return first object from list, If no element present then throws error
- Single or Single(x => //some condiiton) will return single object from a sequence that satisfies a specified condition. If there are more than one records, it will throw exception
- The FirstOrDefault method returns the first element from a sequence that satisfies a specified condition, or a default value if no such element is found. 
- SingleOrDefault, if sequence contain more than one value then it will return default value.
##### Singleton

##### Startup class
##### middleware and its function
```
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;

public class CustomMiddleware
{
	private readonly RequestDelegate _next;

	public CustomMiddleware(RequestDelegate next)
	{
		_next = next;
	}

	public async Task InvokeAsync(HttpContext context)
	{
		// Logic before the next middleware
		await context.Response.WriteAsync("Custom Middleware - Before\n");
		await _next(context);
		// Logic after the next middleware
		await context.Response.WriteAsync("Custom Middleware - After\n");
	}
}
```
##### Dependency injection
- Dependency Injection (DI) is a design pattern commonly used in .NET development to achieve loose coupling between classes and manage dependencies more effectively. In DI, the dependencies of a class are provided from the outside rather than created within the class itself. This allows for better maintainability, testability, and flexibility in your codebase.
- In .net framework used Unity nuget package
##### SOLID principles
The SOLID principles are a set of five design principles in object-oriented programming that aim to make software designs more maintainable, flexible, and easier to understand. Each principle focuses on a specific aspect of software design and encourages developers to write clean, modular, and extensible code.
1. Single Responsibility Principle (SRP):
- This principle states that a class should have only one reason to change, meaning it should have only one responsibility or job.
- Example: A User class should be responsible for managing user data and authentication, but not for sending emails. Sending emails should be handled by a separate EmailService class.
2. Open/Closed Principle (OCP):
- The Open/Closed Principle states that classes should be open for extension but closed for modification. This means that you should be able to add new functionality to a class without modifying its existing code.
- Example: Using interfaces and inheritance to extend the behavior of a class without changing its core implementation.
3. Liskov Substitution Principle (LSP):
- The Liskov Substitution Principle states that objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program.
- Example: If you have a Rectangle class and a Square class that inherits from Rectangle, you should be able to substitute a Square object wherever a Rectangle object is expected.
4. Interface Segregation Principle (ISP):
- The Interface Segregation Principle suggests that clients should not be forced to depend on interfaces they do not use. It promotes creating specific interfaces for specific client needs.
- Example: Instead of having a single large interface with many methods, break it down into smaller, more focused interfaces that are tailored to specific client requirements.
5. Dependency Inversion Principle (DIP):
- The Dependency Inversion Principle states that high-level modules should not depend on low-level modules. Both should depend on abstractions. Additionally, abstractions should not depend on details; details should depend on abstractions.
- Example: Using Dependency Injection to decouple classes and inject dependencies, allowing for easier testing and flexibility in changing implementations without modifying existing code.
##### Interface vs Abstract class
- Interface: Defines a contract for classes to implement, specifying method signatures without implementations. Classes can implement multiple interfaces but cannot contain any implementation details.
- Abstract Class: Provides a partial implementation with both abstract and concrete methods. Cannot be instantiated on its own but serves as a base for subclasses to inherit from and extend. Subclasses must implement abstract methods defined in the abstract class.
##### JWT token
- JWT stands for JSON Web Token, which is a compact and self-contained way to securely transmit information between parties as a JSON object. It is commonly used for authentication and authorization in web applications.
- A JWT token consists of three parts: a header, a payload, and a signature. The header typically contains the type of token and the signing algorithm i.e meta data about token, the payload contains the claims (data) ex: {userId: 123, exp: 234544, role: "admin"}, and the signature is used to verify that the sender of the JWT is who it says it is.
- refresh token is used to get new jwt token, if previous jwt token expired.
##### Local storage vs Session storage vs Cookie in browser
Local Storage, Session Storage, and Cookies are all ways to store data in the browser, but they have some key differences in terms of lifespan, storage capacity, and accessibility.
1. Local Storage:
- Data stored in Local Storage persists even after the browser is closed and reopened.
- The data stored in Local Storage has no expiration time unless explicitly removed.
- Local Storage has a larger storage capacity compared to Session Storage.
```
localStorage.setItem('key', 'value'); // set
const value = localStorage.getItem('key'); // get
localStorage.removeItem('key'); // remove
```
2. Session Storage:
- Data stored in Session Storage is available only for the duration of the page session (i.e., until the browser tab is closed).
- The data stored in Session Storage is cleared when the browser tab is closed.
- Session Storage has a smaller storage capacity compared to Local Storage.
```
sessionStorage.setItem('key', 'value');
const value = sessionStorage.getItem('key');
sessionStorage.removeItem('key');
```
3. Cookies:
- Cookies are small pieces of data stored on the client-side that persist across different sessions.
- Cookies have an expiration time that can be set when creating the cookie.
- Cookies have a limited storage capacity compared to Local Storage and Session Storage.
```
document.cookie = 'key=value; expires=Sun, 31 Dec 2023 23:59:59 GMT';
const cookieValue = document.cookie;
// Delete a cookie (by setting expiration date in the past)
document.cookie = 'key=; expires=Thu, 01 Jan 1970 00:00:00 GMT';
```
##### Startup.cs class in .net core
- The Startup class serves as the entry point for ASP.NET Core applications, allowing you to configure the application's behavior before it begins handling requests. 
- ConfigureServices:
This method is responsible for registering services that the application will use. These services are reusable components that provide functionality, such as database connections, logging, or third-party APIs. Services are registered using the IServiceCollection interface, which is passed to the ConfigureServices method. 
- Configure:
This method defines the application's request processing pipeline, which determines how incoming HTTP requests are handled. It specifies the order in which middleware components are invoked to process requests. 
- Hosting:
In ASP.NET Core, the application host (e.g., IWebHost) is responsible for creating and configuring the Startup class and initializing the application. 
- Example:
In a typical ASP.NET Core application, you might use the ConfigureServices method to register a database context, add logging services, and configure options. In the Configure method, you would set up the request pipeline, potentially including middleware for routing, authentication, and serving static files. 
- Modern Approach:
In newer versions of ASP.NET Core (e.g., ASP.NET Core 8), a minimal API approach is often used, where the application's configuration and request handling are defined directly in the Program.cs file instead of the Startup.cs file. While the Startup.cs is not strictly required in these cases, it can still be used for more complex applications or when maintaining a clear separation of concerns is desired.
```
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}

public class Startup
{
    public Startup(IConfiguration configuration)
    {
        Configuration = configuration;
    }

    public IConfiguration Configuration { get; }

    public void ConfigureServices(IServiceCollection services)
    {
         // Register services here
   	 services.AddControllers();
   	 services.AddDbContext<MyDbContext>(
		options => options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection"))
	);
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
	// Configure the HTTP request pipeline here
	if (env.IsDevelopment())
	{
	   app.UseDeveloperExceptionPage();
	}
	else
	{
	    app.UseExceptionHandler("/Home/Error");
	    app.UseHsts();
	}

	app.UseHttpsRedirection();
	app.UseStaticFiles();
	app.UseRouting();
	app.UseAuthentication();
	app.UseAuthorization();
	app.UseEndpoints(endpoints =>
	{
	     endpoints.MapControllerRoute(
	     name: "default",
	     pattern: "{controller=Home}/{action=Index}/{id?}");
	});
    }
}
```
##### Concurrency vs Parallelism
###### Concurrency
- **Definition**: Concurrency is about dealing with multiple tasks at once, but not necessarily doing them simultaneously. Its a feel of parallelism, which feels like multiple task are working in parallel, instead it execute one task for sometime and switch other task, and then switch back process the first task and continuing doing this until the tasks gets complete.
- **Goal**: Efficiently manage multiple tasks by switching between them.
- **Analogy**: A single chef cooking multiple dishes by switching between them. (Mom cooking lunch/dinner in home)
- **Implementation**: Often involves threads on single core, coroutines, or async/await.
- **Use Case**: Useful when tasks are I/O-bound (e.g., reading files, network requests)

###### Parallelism
- **Definition**: Parallelism is about executing multiple tasks at the same time using multiple processors or cores.
- **Goal**: Speed up computation by dividing work across processors.
- **Analogy**: Multiple chefs each cooking a different dish at the same time. (Restaraunt chef cooking each dish)
- **Implementation**: Involves multi-core CPUs, GPUs, or distributed systems.
- **Use Case**: Ideal for CPU-bound tasks (e.g., large-scale computations, simulations).

##### Asynchronous vs Threading
###### Threading
- What it is: Running multiple threads (lightweight processes) in parallel.
- How it works: Each thread has its own execution path and can run simultaneously on multiple CPU cores.
- Best for: CPU-bound tasks (e.g., heavy computations).
- Resource usage: Threads are relatively heavy; too many can lead to high memory usage and context-switching overhead.
- Example use case: Image processing, data crunching, simulations.
###### Async
- What it is: A way to write non-blocking code using a single thread.
- How it works: Uses an state machine to keeps track of where the method should resume after each await.
- Best for: I/O-bound tasks (e.g., file access, web requests, database calls).
- Resource usage: Very lightweight; can handle thousands of operations with minimal threads.
- Example use case: Web servers, downloading files, calling APIs.

##### IEnumerable vs IQuereable
1. IEnumerable:
- Represents a collection that can be enumerated using a foreach loop.
- Suitable for in-memory collections like arrays, lists, and other IEnumerable implementations.
- Executes queries on the client-side (in-memory) after fetching all the data from the data source.

2. IQueryable:
- Represents a query that can be executed against a specific data source (like a database) that supports IQueryable.
- Suitable for querying databases using LINQ providers like Entity Framework, LINQ to SQL, etc.
- Translates LINQ queries into SQL queries and executes them on the server-side, allowing for more efficient querying by leveraging the capabilities of the underlying data source.

Feature | IEnumerable | IQueryable
--- | --- | ---
Namespace | System.Collections | System.Linq
Data Source | In-memory collections | Remote data sources (e.g., DB)
Query Execution | In-memory | At the data source
Performance | Less efficient for large data sets | More efficient for large data sets
Use Case | LINQ to Objects | LINQ to SQL/Entities

##### Thread vs Task
In C#, both threading and tasks are used for parallel programming to execute multiple operations concurrently. However, there are some key differences between threading and tasks:
1. Threading:
- Threading involves creating and managing threads explicitly using the Thread class in the System.Threading namespace.
- Threads are lower-level constructs that directly map to operating system threads.
- With threading, you have more control over the thread's lifecycle, synchronization, and resource management.
- Threading requires manual management of thread creation, starting, stopping, and synchronization using techniques like locks, mutexes, and semaphores.
2. Task:
- Tasks are a higher-level abstraction introduced in the Task Parallel Library (TPL) in .NET Framework 4.0.
- Tasks represent asynchronous operations and provide a simpler and more efficient way to write parallel code compared to threading.
- Tasks use a thread pool under the hood, which manages the execution of tasks on available threads from the pool.
- Tasks support features like continuation, cancellation, exception handling, and composition, making it easier to work with asynchronous operations.
- Tasks can be created using the Task class or the Task.Run method, which queues the task to the thread pool.

In summary, while threading provides more control and flexibility at a lower level, tasks offer a higher-level abstraction that simplifies parallel programming and asynchronous operations. Tasks are generally preferred for most parallel programming scenarios due to their ease of use and built-in features for managing asynchronous operations.

##### Database connection in .Net
1. ADO.NET:
- ADO.NET (ActiveX Data Objects) is a core data access technology in .NET for connecting to databases.
- You can use classes like SqlConnection, SqlCommand, SqlDataAdapter, etc., to interact with databases.
- Example:
```
using System.Data.SqlClient;
   string connectionString = "Data Source=ServerName;Initial Catalog=DatabaseName;User ID=UserName;Password=Password";
   using (SqlConnection connection = new SqlConnection(connectionString))
   {
	connection.Open();
    // Perform database operations
    }
```
2. Entity Framework:
- Entity Framework is an ORM (Object-Relational Mapping) framework that simplifies database interactions by mapping database tables to .NET objects.
- You can use DbContext and DbSet to interact with the database using LINQ queries.
- Example:
```
using Microsoft.EntityFrameworkCore;
var options = new DbContextOptionsBuilder<MyDbContext>().UseSqlServer("connectionString").Options;
using (var context = new MyDbContext(options)) {
  var products = context.Products.ToList();
  // Perform database operations
 }
3. Dapper:
- Dapper is a micro ORM that provides high-performance data access by mapping query results to objects.
- It allows you to write SQL queries and map the results to objects easily.
