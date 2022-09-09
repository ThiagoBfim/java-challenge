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
- [ ] Don't forget to include Swagger, and the test.


----------

### Challenges LVL 1:

- [ ] Include this rank top movies in the cache (Hazelcast), and get from it using RateLimiter (https://resilience4j.readme.io/docs/ratelimiter) as failover. 
- [ ]  Publish your project in the Cloud with Heroku (or another PaaS).
- [ ]  Find other API to get Movies, and update the first endpoint to use template method design pattern to be able to get the movies from bove APIs. Use a CircuitBreak for that. If you have any problem with one API you should get from the other API as a failover. (You can try that changing the API Key)


----------

### Challenges LVL 2:

- [ ] Run your application using Docker, create a docker file.
- [ ] Include Spring Actuator.
- [ ] Create the files to deploy the application using kubernetes.
- [ ] Include the probes from actuator in your deployment.yml
- [ ] Update your probes in case of hazelcast go down the application should restart
- [ ] Do the deployment into sandbox Openshift (https://developers.redhat.com/developer-sandbox)

----------

### Challenges LVL 3:

- [ ] Include SonarCloud in your project, make sure the coverage is above 70% and you don't have a loud code smell.
- [ ] Include a pipeline, you can use gitHub Actions, or Travis CI, use what you prefer.
- [ ] Your CI pipeline should include [build, test, sonar]
- [ ] Include also CD in your pipeline, it should be able to deploy in your PaaS (Heroku) or in your Openshift.

### References

* WebClient: https://www.baeldung.com/spring-5-webclient
* Feign: https://www.baeldung.com/intro-to-feign
* Hazelcast: https://docs.spring.io/spring-boot/docs/2.0.x/reference/html/boot-features-hazelcast.html
* Failover: https://medium.com/lydtech-consulting/failover-and-circuit-breaker-with-resilience4j-14a57a43c0da
