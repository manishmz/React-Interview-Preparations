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
delegates type
angualr pacakges
Restrict api request of different region
Difference between List and Array

4 Maturity Levels of REST API Design

0- The Swamp of POX - Url should not have underscore instead use - one url
1- Resources - different usrl to interact with different resources
2 - Methods - Get, Post, Put, Patch, Delete - Headers - Query Parameters - Status Codes
3 - Hypermedia Controls - Content Negotiation (Accept, Content-Type) - HATEOAS (Add ralated links in response for explorable) - Versioning

