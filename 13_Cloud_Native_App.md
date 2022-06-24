# Cloud-Native Applications
Applications optimized for running on a cloud-environment, i.e, it is optimized for exploring the economic advantages of cloud computing. Usually, it is resilient and scalable. Usually also distributed, leveraging the advantages of service-oriented approaches (microservices, SOA).

* A cloud-native application is an application **optimized for running on a cloud-infrastructure** (IaaS or PaaS) having the essential characteristics of being scalable and resilient.
* One of the main goals of a cloud-native application is to use its underlying cloud-resources as **economically efficiently** as possible.
* Each phase in the application life-cycle has to be adapted and optimized for running in a cloud-environment.
* A cloud-native application is typically designed as a **distributed application** built up from **stateless components** (employing asynchronous communication).

## Implementing CNA development
The following aspects need to be addressed:

**Architecture:** Application needs to be designed for scalability and resilience. Maybe move towards Service Oriented Architecture / Microservices Architecture.

**Organization:** Agile teams; implement DevOps principles and methodologies; Twelve-Factor Application.

**Process:** Automated Software Development / Deployment / Management Pipeline.

## General observations
iCloud and Hotmail are NOT cloud computing! Running in the web is not a synonym for cloud computing. To define if an app or a service is Cloud Computing, it must fulfill the 5 NIST definitions.

Kubernets are similar to OpenStack. They are both **Cluster Managers**. Neither of them virtualize anything. OpenStack manages VMs, while Kubernetes orchestrate containers.

With PaaS, a developer codes an application in whetever language fits him better, then provision a web-server + elastic database and things are ready to go.

In OpenStack we need HEAT to implement pay-as-you-go and elastic provisioning of resources.

MySQL is not Cloud-Native

**A Docker file is a declarative file to state what are the dependencies, i.e., what is needed.**

## Break-out Session
**Discuss in groups what are the requirements to migrate to Cloud-Native.**<br>
There are technical aspects and human aspects, which often times are opposing. A company sometimes need to change its organisational structure and/or budget planning to adopt a cloud-environment or migrate to cloud-native applications. It also involves training for enabling personal to use cloud related tools, like Kubernetes and containers. Some useful questions are, to whom will the applications be offered? Geographical coverage? Number of users, etc? How rapidly should it grow/contract? Will there be fluctuations on demand? Based on the answers, choose the right service model (IaaS, PaaS, FaaS, SaaS) and the deployment-model (public, private, hybrid). Pay attention to the SLA. 

Is the database cloud friendly? (MySQL, NoSQL) a database should be scalable. Move to Microservices is often necessary. Many of these services will be serverless (stateless). Developments need to adapted for this new approach. Code needs to be Service-oriented, where individual services are loosely coupled, reusable and stateless. That means, the service must be designed to be disposable.

Kubernetes is constantly replacing containers. If a pod fails, it can be redeployed somewherelse. Configuration is done with environment variables because they are a lightweight and resilient solution to make portable configuration.