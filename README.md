# Challenge with Java BE

This is a simple project with a challenge for Backend developrs.

## In this project you will learn:

* Consuming API (Feign)
* Creating API REST (Spring Web)
* Create a database (Spring Data)
* Create a CircuitBreak (Resilience4J)
* Different Roles (Spring Security)
* Cache with Hazelcast
* Swagger
* Sonar
* CI/CD
* Docker
* Kubernetes
* Deploy in Cloud

## Tasks: 

### Create your API REST


- [ ] Create the authentication using JWT
- [ ] Create two roles ADMIN, USER
- [ ] Create an endpoint to return the JWT (5 minutes of timeout), receive the username and password
- [ ] Create an endpoint to consume an API from IMDB (https://imdb-api.com/) and populate your database (you can use WebClient or Feign to consume the API). This API could be called just by the ADMIN user, see @Secured and Roles in Spring Security.
- [ ] Create an endpoint to create a user, this user will have just a USER role. (The user should have a username and a password, be careful when saving the user password)
- [ ] Create an endpoint to update the permission to this user to ADMIN and/or USER role. This API could be called just by the ADMIN user, see @Secured and Roles in Spring Security.

### Upgrade your API REST

- [ ] Create an endpoint to list all the movies.
- [ ] Create an endpoint to include a movie to the user (favorite list)
- [ ] Create an endpoint to exclude the movie from the favorite list
- [ ] Each time the user includes the movie in the favorite list add one "star" to the movie
- [ ] Create an endpoint to list the top 10 movies, the movies with more stars.
- [ ] Create an endpoint to list the favorite movies per user.
- [ ] Don't forget to include Swagger/OpenAPI, and the test.

#### Content to help:

* Book: REST API - Design Rulebook : Mark Masse: https://www.oreilly.com/library/view/rest-api-design/9781449317904/
* Spring Data: https://www.baeldung.com/the-persistence-layer-with-spring-data-jpa
* Spring REST - Full Tutorial: https://www.baeldung.com/rest-with-spring-series
* Spring REST: https://spring.io/guides/tutorials/rest/
* Open API: https://www.baeldung.com/spring-rest-openapi-documentation
* WebClient: https://www.baeldung.com/spring-5-webclient
* Feign: https://www.baeldung.com/intro-to-feign



----------

### Challenges LVL 1:

- [ ] Include this rank top movies in the cache (Hazelcast), and get from it using RateLimiter (https://resilience4j.readme.io/docs/ratelimiter) as failover. 
- [ ] Publish your project in the Cloud with Heroku (or another PaaS).
- [ ] Find other API to get Movies, and update the first endpoint to use template method design pattern to be able to get the movies from bove APIs. Use a CircuitBreak for that. If you have any problem with one API you should get from the other API as a failover. (You can try that changing the API Key)

#### Content to help:

* Guide to Resilience4j: https://www.baeldung.com/resilience4j
* Caching with Spring Boot and Hazelcast: https://hazelcast.com/blog/spring-boot/
* Template Method: https://refactoring.guru/design-patterns/template-method
* Failover: https://medium.com/lydtech-consulting/failover-and-circuit-breaker-with-resilience4j-14a57a43c0da

----------

### Challenges LVL 2:

- [ ] Run your application using Docker, create a docker file.
- [ ] Include Spring Actuator.
- [ ] Create the files to deploy the application using kubernetes.
- [ ] Include the probes from actuator in your deployment.yml
- [ ] Update your probes in case of hazelcast go down the application should restart
- [ ] Do the deployment into sandbox Openshift (https://developers.redhat.com/developer-sandbox)

#### Content to help:

* Spring Boot Actuator: https://www.baeldung.com/spring-boot-actuators
* Spring Boot with Docker: https://spring.io/guides/gs/spring-boot-docker/
* Template Method: https://refactoring.guru/design-patterns/template-method
* Kubernetes Tutorial: https://medium.com/@javatechie/kubernetes-tutorial-run-deploy-spring-boot-application-in-k8s-cluster-using-yaml-configuration-3b079154d232
* Book: Modernizing Enterprise Java: https://developers.redhat.com/e-books/modernizing-enterprise-java

----------

### Challenges LVL 3:

- [ ] Include SonarCloud in your project, make sure the coverage is above 70% and you don't have a loud code smell.
- [ ] Include a pipeline, you can use gitHub Actions, or Travis CI, use what you prefer.
- [ ] Your CI pipeline should include [build, test, sonar]
- [ ] Include also CD in your pipeline, it should be able to deploy in your PaaS (Heroku) or in your Openshift.

#### Content to help:

* SonarCloud Integration with SpringBoot-Maven: https://medium.com/@bethecodewithyou/sonarcloud-integration-with-springboot-maven-5820180ef764
* How to build a CI/CD pipeline with GitHub Actions in four simple steps: https://github.blog/2022-02-02-build-ci-cd-pipeline-github-actions-four-steps/
* The twelve-factor: https://12factor.net/
* Travis CI: https://www.travis-ci.org/

