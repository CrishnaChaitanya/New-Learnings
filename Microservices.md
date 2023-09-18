https://www.youtube.com/watch?v=rv4LlmLmVWk&ab_channel=TechWorldwithNana -- the best video 

Why microservices?
--> So before microservices, developers/companies used 'MONOLITHIC' service, In a monolithic architecture all the components of a project are placed into one unit/package.
Let's take an example of a shopping website - the components such as 'user-auth', 'product-catelog', and 'shopping-cart' are all placed into one unit which gets deployed and scaled as 1 unit.
- App must be written in 1 tech stack
- Teams need to work carefully so that they do not affect each other's code
- So it is 1 artifact, so you must re-deploy the entire application on each update.

Challenges with this Monolithic service
=======================================
1. Application is too large and complex - as the application grew in size this architecture became unstable
2. Parts are more tangled into each other
3. You can only scale the entire application instead of a specific service - suppose on a high-demand day a particular component is experiencing a big load, we will have to scale the entire application instead of just that service, this is cost-ineffective.
4. Difficult if services need different dependency versions
5. The release process takes longer as on every update the entire application needs to be tested
6. A bug in a module can bring down the entire application.

SO TO SOLVE ALL THESE ISSUES WE USE MICROSERVICES

What are microservices?
-------------------------
- Split the application into smaller independent services
- 1 microserivce per 1 job
- self-contained and independent - separate CI/CD  ( this is called loose coupling )
- services can be built and deployed separately
- So in the shopping website example; it can be divided into different microservices such as "shopping cart", "products", "payment" etc....how we divide the project into microservices should be based on business logic and not technical logic
- Each microservice has its own version

HOW TO MICROSERVICES COMMUNICATE WITH EACH OTHER?
--------------------------------------------------
- one way is with the help of APIs
- Each service has its own API
- Another way of communication b/w microservices is using "MESSAGE BROKER" like RabbitMQ *****
- The difference b/w both is message brokers use Async communication
- And the main use of microservices is that each microservice can be developed using whatever tech stack of choice, so the "payment" microservice can be built using nodejs and the "products" service can be built using Java, etc..
- Each team can develop their microservice independently without affecting other teams.

Challenges with microservices
------------------------------
- Configure the communication between services - since there are a lot of independent components; the communication between them becomes an issue

- more difficult to monitor with multiple instances of each service distributed across servers.

- Tools are being developed to manage this complexity and one such popular tool is "Kubernetes"

CI/CD pipelines for microservices
=================================
We have two options to maintain the CI/CD pipelines for microservices:
1. Monorepo
2. Polyrepo

Monorepo - all the microservices are put into one repo, and different components are kept in their respective folder and all these folders in one repo. 
- makes code management and development easier
- changes can be tracked together, tested together, and released together.
- Challenges: Tight coupling for projects, and bigger code means git interaction becomes slow.
- All projects and teams are affected if there is some issue.
- But there are big companies such as Google and Facebook that use the Monorepo style.

Polyrepo - for each service, we create a separate git service.
- This is a preferred approach as it becomes to maintain a CI/CD pipeline and etc
- loosely coupled
- Challenges: cross-cutting changes are more difficult
- switching b/w projects is tedious
- searching, testing and debugging are more difficult

