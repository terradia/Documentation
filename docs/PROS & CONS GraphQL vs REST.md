In this document, we will describe the principles of GraphQL and REST in term of APIs.

The goal of this document is to compare both technologies, evaluate which one is more appropriate for Terradia.

# API REST
Rest is not really a technology of APIs but more a way to create API, kind of a coding style, an API Style.

The goal of Rest is to define a general way to create APIs that uses all the features and HTTP Verbs.

resource : In Rest API, a resource is a data in the database : for example a user in the DB is a resource. In Rest you are manipulating resources through the API.

There are 5 main ways to consume a REST Api, it is byt calling routes with there HTTP verbs :
- GET : When you want to get data.
- POST : When you want to create a resource.
- DELETE : When you want to delete resources. 
- PUT : When you want to edit some parts of a resource.
- PATCH : When you want to edit all elements of a resource.

In fact, create a RestFul API is a really clean and neat way to create an API that is clean for the developers to use.

## PROS & CONS :
### PROS :
- It is a really standard way to create APIs nowadays
- There are a lot of helpers to create this type of APIs

### CONS : 
- You always get all the data form a resource which can lead to very fat JSONs
- It is hard to implement
- There is a lot to learn to create an API that is fully RestFul.

# GraphQL API
GraphQL is a technology created by Facebook to change the way we consume resources of servers.
The principle of GraphQL is that you only ask the data you want to have, and you will not GET / EDIT data that you don't want / need to edit or get.

All request are done with one HTTP verb : "POST"

There is two type of requests in GraphQL : 
- Query
- Mutation
- There is also the Subscriptions put that is not the point.

## PROS & CONS
### PROS : 
- It is really fast
- Really easy to learn to use
- You only the data you need, nothing less, nothing more
- Relations between resources are implemented natively
- The Technology is going to be really mature.

### CONS :
- It could be harder to create
- It is not the most standard way to create APIs
