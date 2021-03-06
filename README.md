# Spring XD Container
This Docker image runs a Spring XD container in [distributed mode](http://docs.spring.io/spring-xd/docs/1.0.0.BUILD-SNAPSHOT/reference/html/#running-distributed-mode). It expects
to connect to a ZooKeeper ensemble, an HSQLDB server and a middleware instance using
environment variables that adhere to the Docker link conventions.

The admin port (9393) is exposed, so that a REST client (for example a Spring XD shell) can connect to it.


Sample usage, assuming other Docker containers are running:

	docker run --name container1 \
	    --link zookeeper:zookeeper \
	    --link hsqldb:hsqldb \
	    --link redis:redis \
	    springxd/container

The middleware can be [redis](https://hub.docker.com/_/redis/) (`--link <name>:redis`) or [rabbitmq](https://hub.docker.com/_/rabbitmq/) (`--link <name>:rabbitmq`).
