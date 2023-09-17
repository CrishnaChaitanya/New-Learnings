https://www.youtube.com/watch?v=rv4LlmLmVWk&ab_channel=TechWorldwithNana -- the best video 

Why microservices?
--> So before microservices, developers/companies used 'MONOLITHIC' service, In a monolithic architecture all the components of a project are placed into one unit/package.
Let's take an example of a shopping website - the componets such as 'user-auth' , 'product-catelog', 'shopping-cart' are all placed into once unit which gets deployed and scaled as 1 unit.
- App must be written in 1 tech stack
- Teams need to work carefully so that they do not effect each other's code
- So its 1 artifact, so you must re-deploy the entire application on each update.

Challanges with this Monolithic servies
=======================================
1. Application is too large and complex - as the application grew in size this architecture became unstable
2. Parts are more tangled into each other
3. You can only scale the entire application insted of a specific serivice - suppose on a high demand day a particular component is experiencing big load, we will have to scale the entire application insted of just that service, this is cost ineffective.
4. Difficult if services need different dependency versions
5. Release process takes longer as on every update the entire application needs to be tested
6. A bug in a module can bring down the entire application.

SO TO SOLVE ALL THESE ISSUES WE USE MICROSERVICES

What are microservices?
-------------------------
- Split the application into smaller independent services
- 1 microserivce per 1 job
- self contained and independent - seperate CI/CD  ( this is called loose coupling )
- services can be built and deployed seperately
- So in the shopping website example; it can be divided into differnt microservices such as "shopping cart","products","payment" etc....how we divide the project into microservices should be based on business logic and not technical logic
- Each microservices has its own version

HOW TO MICROSERVICES COMMUNICATE WITH EACH OTHER ?
--------------------------------------------------
- with the help of API's
- Each service has its own api
- Another way of communication b/w microservices is using "MESSAGE BROKER" like RabbitMQ *****
- The differnce b/w both is message brokers use Async communication
- And the main use of microservices is that each microservice can be developed using whatever tech stack of choice, so "payment" microserivce can be biult using nodejs and "products" service cna be built using Java etc..
- Each team can develope their microservice without affecting other teams.


to nbe continued .............
