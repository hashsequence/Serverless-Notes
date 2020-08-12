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

* Recap : At its core Containers allow you to package up all your code and dependencies into a box, serverless is a model where you dont need to wory about the servers and management of server infrastructure, and its scales as you use up more resources automatically.

* Serverless Services includes:

    - amazon lambda, dynamodb, etc

* container and orchestration services:

    -docker, kuberernetes

* Whats the environment differences
    - serverless

        - maintained by cloud provider

        - cant install software in underlying environment (but can install code libraries)

    - containers
        - users can control underlying infrastructure, vm size, os, etc
        - can install almost any software 
        - can have prepackaged stuff (docker images)
    
* use cases
    - serverless
        - event driven architecture
            - spins up when needed and does its thing and shutsdown
        - unpredictable traffic, so we only pay what we use
        - microservices 
            - code can be modular without software dependencies
            - more cloud native
    - containers
        - faster migration to cloud with other softwares 
            -webserver, appserver, apps requiring thirdparty software
        - suited for predictable traffic, since you control resources
        - microservices
            -easy to move api with dependencies


## How do we build a serverless provider from scratch 


As a regular joe with no graduate level experience on serverless architecture, here
is what I would do with my limited knowledge on serverless architecture based on my research via google and scihub

### Run a Serverless Provider via Docker and Kubernetes 

Problem With this approach is the overhead of when theres a new user and no existing running docker and they need to spin up a new one, this is the cold start 
overhead. There is also the problem with idle users and causing wasted resources

What OpenWhisk does it spins up multiple containers with the required dependencies to run a function and shutsdown paused containers when its not being used 

So now we must consider how to schedule when to spin up and shutdown containers,
so we have the question of scheduling 

we also need to consider the problem of state:
How would we build a system of dealing with a mutable but distributed state
accross multiple containers starting up and shutting down


## References:

* https://hackernoon.com/what-is-serverless-architecture-what-are-its-pros-and-cons-cc4b804022e9


* [Provider-Friendly Serverless Framework For Latency Critical Applications](http://conferences.inf.ed.ac.uk/EuroDW2018/papers/eurodw18-Shillaker.pdf)