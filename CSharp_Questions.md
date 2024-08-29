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
##### delegates type
It allows you to treat methods as first-class objects, which means you can pass methods as parameters, store them in variables, and invoke them dynamically
Delegates are often used to implement event handling, callbacks, and asynchronous programming.
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
Level 0 - The Swamp of POX (Plain Old XML) - Url should not have underscore instead use - one url
Level 1 - Resources - different urls to interact with different resources
Level 2 - HTTP Verbs - Get, Post, Put, Patch, Delete - Headers - Query Parameters - Status Codes
Level 3 - Hypermedia Controls - Content Negotiation (Accept, Content-Type) - HATEOAS (Add ralated links in response for explorable) - Versioning

