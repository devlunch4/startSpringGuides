https://spring.io/guides/gs/actuator-service/

git clone https://github.com/spring-guides/gs-actuator-service.git

### Building a RESTful Web Service with Spring Boot Actuator

> $ curl localhost:8080/hello-world  
{"id":1,"content":"Hello, Stranger!"}

//

> $ curl localhost:8080/hello-world  
curl: (52) Empty reply from server  
$ curl localhost:9000/hello-world  
{"id":1,"content":"Hello, Stranger!"}  
$ curl localhost:9001/actuator/health  
{"status":"UP"}   >>> Down..