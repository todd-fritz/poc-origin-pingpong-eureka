# poc-origin-pingpong-eureka

Shamelessly borrowed from [Spring Cloud Ping-Pong Example] (https://github.com/bijukunjummen/spring-cloud-ping-pong-sample).

The originating project has been modified to deploy to OpenShift Origin (v3) as separate containers (hence isolated git repos).  This repo has an automated build process that triggers after a push to regenerate a docker image saved to dockerhub.

This project is based on spring cloud, spring boot, and eureka.  Hysterix is included (refer to monitor project).

Five, separate repositories are used for the example (by deployment order):
1. [poc-origin-pingpong-eureka](https://github.com/todd-fritz/poc-origin-pingpong-eureka)
2. [poc-origin-pingpong-config](https://github.com/todd-fritz/poc-origin-pingpong-config)
3. [poc-origin-pingpong-monitor](https://github.com/todd-fritz/poc-origin-pingpong-monitor)
4. [poc-origin-pingpong-ping](https://github.com/todd-fritz/poc-origin-pingpong-ping)
5. [poc-origin-pingpong-pong](https://github.com/todd-fritz/poc-origin-pingpong-pong)

## Running on a Local Machine
Running it all local is simple, do the following in sequence, in four different terminal windows:

* Start up Eureka (source,java)
  `cd poc-origin-pingpong-eureka`
  `mvn spring-boot:run`
  Eureka can be accessed at this URL:  http://localhost:8761/

* Start up Config server (source,java)
`cd poc-origin-pingpong-config`
`mvn spring-boot:run`

* Start up Pong Service (source,java)
`cd poc-origin-pingpong-pong`
`mvn spring-boot:run`

* Start up Ping Service (source,java)
`cd poc-origin-pingpong-ping`
`mvn spring-boot:run`


If all the applications have come up cleanly, the endpoint should be available at http://localhost:8080
