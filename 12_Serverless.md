# Serverless Computing
Can be thought of as yet another layer of abstraction on top of PaaS in which the application itself is managed by the provider and the developers **only focus on the functions** of the code. The developers upload a code and the provider deploys and excecute it. Important to notice that **scalability, elasticity and (high-)availability are all managed by the provider**, whereas on PaaS the developer must take care to make the application HA.

Some important aspects of serverless computing:
* Mostly used with interpreted languages
* Effemeral. Usually the **Functions** are deployed in a container that might last one invokation
* **All functions are stateless**
* Can be thought of as an extention of microservices
* **Functions are typically executed based on events**

Obs: Containers, per se, are not serverless, because they do have a state (volumes can be attached) and their resources are defined in the declaration file (like Docker file).

## Serverless Computing vs. Microservices
* Microservices offer persistence, serverless don't
* Microservices run on dedicated infrastructure (like a cluster managed by Kubernetes), while serverless may or may not share a infrastructure
* Serverless **Actions** are portable, while microservices are specific to one infrastructure
* Serverless **Functions** may run on an scheduled base or be triggered upon an **Event**
* In serverless, the runtime of a function is limited, while a microservice can run undefinitely

## OpenWhisk
Platform for deploying serveless computing. Uses containers for containment of data. Support multiple languages.

### Action
Is a stateless function triggered by an external API call or a trigger.<br>
Multiple Actions can be concatenated together in a **Sequence**. a collection of **Actions** is called a **Package**. We can look at it as a library of actions.

### Trigger
An **Event** in general. Can be a HTTP GET/POST, messages in a message queueing (MQTT), modifications of documents or databases, etc.

**Triggers** are nothing else than entries in a list. Openwhisk then tries to find matching rules which lead to the execution of actions (or sequences). The execution order of the actions is, however, random. Therefore, the sequence of excecution may not match the sequence at which the triggers happened.

### Rule
Binds a **Trigger** to an **Action**. A single trigger can run multiple **Actions** as long as there are rules linking this **Trigger** to these **Actions**.


### Carefull with containers
As mentioned, OpenWhisk use containers, which can be reused by different **Actions**. If reused, a container maintain the state of the process. Reusing containers is definetely more efficient, but might have concurrency and security issues.