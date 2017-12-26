Kata Docker
===========
> Learn how to create a simple stack (Database + DB Admin tool + Applicative Server) with docker-compose file.

Instructions
------------

* Make sure you have already installed both [Docker Engine] and [Docker Compose]. You don’t need to install [NodeJS], it is provided by Docker images

* Clone this repository

* Create a docker-compose.yml file to the root of our project

* Create a service **app** :
    - Image: [node:8.9]
    - Port: 3000
    - Volume: **current folder** to **/app**
    - Environment: **NODE_ENV**
    - Working dir: **/app**
    - User: **node**
    - Command: **npm start**

* Create a service **db** :
    - Image: [MongoDB]
    - Port: 27018

* Create a service **dbv** :
    - Image: [Mongo-express]
    - Port: 8081
    - Environment: **ME_CONFIG_MONGODB_SERVER** and **ME_CONFIG_MONGODB_PORT**
    - Depends on: **db**


* Verify that the **package.json** file contains a [startup script]


# Execution

```bash
$ docker-compose up
```

# Help

* https://docs.docker.com/compose/compose-file/#service-configuration-reference
* https://github.com/nodejs/docker-node/blob/master/README.md#how-to-use-this-image
* https://nodejs.org/dist/latest-v8.x/docs/api/


[startup script]: https://docs.npmjs.com/misc/scripts#default-values
[Docker Engine]: https://docs.docker.com/engine/installation/
[Docker Compose]: https://docs.docker.com/compose/install/
[MongoDB]: https://hub.docker.com/_/mongo/
[Mongo-express]: https://hub.docker.com/_/mongo-express/
[node:8.9]: https://hub.docker.com/_/node/
[NodeJS]: https://nodejs.org