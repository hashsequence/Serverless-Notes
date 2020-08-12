# Serverless-Notes
Personal Research on Serverless

## What Is Serverless?

Serverless is a cloud computing execution model where the cloud provider 
automatically manages and allocates server resources at runtime


Serverless applications are event driven and cloud based and we only need
to manage the  third-party services, client-side logic and cloud-hosted remote procedure calls


Function as a service (faas) is a category of cloud computing services that provides a platform allowing customers to develop, run, and manage application functionalities without the complexity of building and maintaining the infrastructure, faas is one way to achieve serverless


these are the current famous cloud providers 

* AWS Lambda
* Google Cloud Functions
* Azure Functions
* IBM OpenWhisk
* Alibaba Function Compute
* Iron Functions
* Auth0 Webtask
* Oracle Fn Project
* Kubeless


advantages of serverless include:
* pay as u use
    - charged based on number of executions, memory use per / unit of time

* scaling 
    - automatic since te cloud provider will take care of you for this


## Function as a Service (FaaS)

FaaS is an implementation of Serverless architecture where engineers can
deploy as an individual function or business logic

principles of Faas:

* complete management of servers
* invocation based billing
* event driven and instant scaling

key properties:

* independed, server-side, like functions of a programming langauge 
* stateless - cant save anything from one invocation to the next
* ephemeral - spin up quickly and shutdown when not being used


examples of frameworks to implement serverless

Sparta is a framework that transforms a go application into a self-deploying AWS Lambda powered service

[gosparta](gosparta.io)
[serverless](https://www.serverless.com/)

## Difference between Serverless and Containers


## References:

* https://hackernoon.com/what-is-serverless-architecture-what-are-its-pros-and-cons-cc4b804022e9

