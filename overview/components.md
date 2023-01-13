# BKCI 组件

![](../.gitbook/assets/image%20%2815%29.png)

* Blue whale continuous integration platform \(bk-ci \ for short) is based on kotlin/java/js/go/lua/shell and other languages to write and implement, using a complete separation of front and back, plug-in development, with highly available and scalable service architecture design.**Front-end & Interface Gateway\(WebAPI Gateway & FrontEnd\):**
  * **WebAPI Gateway:** by OpenResty, including the docking user login and identity authentication, and the back-end API of the **Consul** service discovery forwarding lua script and Nginx configuration
  * **FrontEnd:** pure front-end project based on VUE, contains a sequence of static resources such as js,img and html.
* **BackEnd\(MicroService BackEnd\):** written in Kotlin/Java, using SpringCloud framework of microservice architecture design, the following is introduced in the order of the start of each microservice module.
  * **Project:** Project management, responsible for managing the pipeline of projects, multiple modules depend on this.
  * **Log:** Build logging service, responsible for receiving logs of builds for forwarding storage and query output.
  * **Ticket:** Credential management service, stores user's credential information, such as code base account password/SSL/Token etc.
  * **Repository:** Codebase management service, stores user's codebase, depends on Ticket's linkage.
  * **Artifactory:** Artifactory service, which implements only a simplified version of the access artifacts functionality and can be extended to dock its own storage system.
  * **Environment:** builder service, importing builders and managing builder clusters with environment for build scheduling concurrency.
  * **Store:** R&D store service, responsible for managing pipeline extension plugins and pipeline template functions, including plugins & template upgrades up and down, linked with process and artifactory.
  * **Process:** Pipeline management, the core service responsible for managing pipeline and pipeline scheduling functions.
  * **Dispatch:** Build dispatcher, responsible for receiving builder start events of the pipeline and distributing them to the corresponding builders for processing.
  * **Plugin:** Plugin extension service of the service, currently empty, mainly used to provide for the subsequent expansion of some back-end services linked with the front-end page, such as docking all kinds of CD platform, test platform, quality inspection platform, etc., with the front-end page configuration, imagine a lot of space.
* **Resource service layer\(Resource\):** Including the provision of storage and the necessary basic middleware, etc.
  * **Storage\(Storage service\):** A sequence of storage service/middleware etc. depend on the base environment.
    * **MySQL/MariaDB:** The main database storage for bk-ci, available mysql 5.7.2 /mariadb 10.x to store relational data for all the above microservices.
    * **Redis:** Core service cache, version 3.x, caches builder information and build-time information and provides distributed locking operations, etc.
    * **ElasticSearch:** Log storage, log module docked to ES to do access to build logs.
    * **RabbitMQ:** Core message queue service, bk-ci's pipeline event mechanism is based on RabbitMQ to stream event messages.
    * **FileSystem:** This block mainly provides services for artifactory, used to store plug-ins, build products and other binary file services, can be docked to file or cloud storage class, extended in artifactory service module.
    * **Consul:** As a service discovery Server for microservices, you need to build Consul Server, and install Consul on the machine where bk-ci microservices are deployed and run as Agent at the same time. You can build a cluster directly with bk-ci microservice deployment machine \ (2 \) and start directly with consul server and agent to reduce the number of machines required.
  * **Agent\(builder\):** The builder is a server/PC responsible for running CI packaged compiled builds, which is dependent on compiled environments such as go, gcc, java, python, nodejs, etc., plus running two parts of the service process written and implemented by bk-ci.

    * **DevopsDaemon:** Responsible for guarding and starting DevopsAgent.
    * **DevopsAgent:** Responsible for communicating with **Dispatch** and **Environment** microservices, upgrading the entire **Agent** and starting and destroying the **Worker**\ (task executor\) process.
    * **Worker:** Written and implemented in Kotlin, it is a file named agent.jar,, the real executor of tasks. It is pulled up and run by **DevopsAgent** via jre, after which it will be responsible for communicating with the **Process microservice module**, picking up plugin tasks and executing and reporting the results \(**Log&Process**\).

