##### What are the main cloud service models? Explain the difference between IaaS, PaaS and SaaS with Azure example?
1. Infrastructure as a Service (IaaS):
- In IaaS, the cloud provider offers virtualized computing resources over the internet. This includes virtual machines, storage, and networking.
- Users have control over the operating system, applications, and configurations, but the provider manages the infrastructure.
- Example: In Azure, Azure Virtual Machines (VMs) provide IaaS where you can create and manage virtual machines in the cloud.
2. Platform as a Service (PaaS):
- PaaS provides a platform allowing customers to develop, run, and manage applications without dealing with the underlying infrastructure.
- It typically includes development tools, database management systems, and middleware.
- Example: Azure App Service is a PaaS offering in Azure that allows developers to build, deploy, and scale web apps and APIs.
3. Software as a Service (SaaS):
- SaaS delivers software applications over the internet on a subscription basis. Users access the software through a web browser.
- The provider manages everything including the application, data, runtime, servers, storage, and networking.
- Example: Microsoft Office 365 is a SaaS offering from Microsoft that provides access to popular office applications like Word, Excel, and PowerPoint online.
In summary, IaaS provides virtualized computing resources, PaaS offers a platform for application development and deployment, and SaaS delivers software applications over the internet. Each model differs in terms of the level of control and management provided by the cloud provider.

##### What is Hybrid Cloud?
Hybrid Cloud = On-premises + Azure Cloud

##### Your team wants to avoid purchasing servers for a new app. What azure model would you suggest?
- Recommend Paas like Azure app service
- It removes the need to manage servers and allow the team to focus on code while Azure handles hosting, scaling and updates.

##### What is a Resource in Azure? How is it different form a Service in Azure?
- A resource in Azure is any individually manageable component (an instance of service) that you can create, configure, and use in the cloud.
- For example, Azure Service is like a class and Azure Resource is like an object or instance of that class.

##### What are Resource Groups in Azure? Why do we use them in projects.
- In Azure, a Resource Group is a logical container that holds related Azure resources such as virtual machines, storage accounts, web apps, databases, and more. Resource Groups help you manage and organize your Azure resources efficiently. Here are some key points about Resource Groups and why we use them in projects:
1. Logical Grouping: Resource Groups allow you to logically group related resources together for easier management. This helps in organizing resources based on different criteria such as environment (dev, test, prod), application, or department.
2. Resource Management: With Resource Groups, you can manage all the resources within a group collectively. This includes deploying, updating, monitoring, and deleting resources as a single unit.
3. Access Control: Resource Groups provide a way to manage access control and permissions at the group level. You can assign role-based access control (RBAC) to users or groups for all resources within a Resource Group.
4. Billing and Cost Management: Resource Groups help in tracking costs and managing billing for a specific project or application. You can view cost analytics and budget alerts at the Resource Group level.
5. Resource Lifecycle Management: Resource Groups simplify the lifecycle management of resources. When you delete a Resource Group, all resources within it are also deleted, helping in clean-up and resource optimization.
6. Deployment and Automation: Resource Groups are often used in deployment scripts and automation workflows. You can deploy templates that define the infrastructure for an application within a Resource Group.
Overall, Resource Groups in Azure provide a way to manage, organize, and secure your Azure resources effectively. They play a crucial role in project management by simplifying resource management, access control, cost tracking, and automation.

##### What are azure virtual machine? When would you use them in a project?
- Azure Virtual Machines (VMs) are cloud based virtual servers that allow user to run application without needing physical hardware. A computer in a cloud.

##### What is Azure App Service? For what purpose can you use them?
- Azure App Service is fully managed Platform as a service (PaaS) that enables developers to host web application, APIs and mobile backends without managing the underlying infrastructure.

##### What are Azure Functions? Have you ever used them in your projects? Why?
- Azure fucntions is a serverless compute service in Azure that lets you run code in response to events without managing infrastructure (servers).
- Advantage: It automatically scales and executes only when triggered, making it cost-efficient and lightweight.
- Each function start with a method marked by the [FunctionName("FunctionNameHere")] attribute
- Run is the method that executes when the function is triggered.
- In parameter of Run specify the type of trigger like [HttpTrigger()], BlobTrigger, timers
- We have triggers for finding accounts whose licenses are expired, are about to expire, or thier trial period is over.

##### A developer adds Azure function code inside their main app. What's the risk?
- Mixing functions code inside the app increase coupling, hurt scalability, and affects performance.

##### What is the difference between Azure function and Function App?
- Function App is a container of Azure functions.

##### What is Azure Storage? What are the types of Azure Storage?
- Blob  Storage: Use to store unstructured data liek images, videos and backups.
- File Storage: Provides cloud based shared file storage.
- Table Storage: Stores large scale NoSQL key valued data for first lookups.
- Queue Storage: Manages message-based communication between applicaitions.

 ##### What is Azure SQL Database? How is it different form regular SQL server?
 - Azure SQL Database is fully managed, cloud based relational database service provided by Microsoft on Azure. It built on teh SQL Server engine. but it is offered as PaaS.
