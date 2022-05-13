https://spring.io/guides/gs/messaging-redis/

https://redis.io/download/#redis-downloads

https://redis.io/docs/getting-started/installation/install-redis-on-windows/
>- Install Redis on Windows  
>- Install or enable WSL2  
>- Install Redis  
>> sudo apt-add-repository ppa:redislabs/redis 
>> sudo apt-get update  
>> sudo apt-get upgrade  
>> sudo apt-get install redis-server  
>> ~Then start the Redis server like so:  
>> sudo service redis-server start  
>- Connect to Redis  
>>  redis-cli  
>> 127.0.0.1:6379> ping  
>> PONG


>- Install on Ubuntu  
>>You can install recent stable versions of Redis from the official packages.redis.io APT repository. Add the repository to the apt index, update it, and then install:
> 
>>curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg  
>>echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list  
>>sudo apt-get update  
>>sudo apt-get install redis


> * This example uses Spring Boot’s default RedisConnectionFactory, an instance of JedisConnectionFactory that is based on the Jedis Redis library.   
 https://github.com/redis/jedis
> * 

### Messaging with Redis

> console Result:   
<pre>
"C:\Program Files\Java\jdk-18.0.1.1\bin\java.exe" "-javaagent:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2021.2.1\lib\idea_rt.jar=1931:C:\Program Files\JetBrains\IntelliJ IDEA Community Edition 2021.2.1\bin" -Dfile.encoding=UTF-8 -classpath C:\githubdev\springGuides\startSpringGuides\target\classes;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-web\2.6.7\spring-boot-starter-web-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter\2.6.7\spring-boot-starter-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot\2.6.7\spring-boot-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-autoconfigure\2.6.7\spring-boot-autoconfigure-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-logging\2.6.7\spring-boot-starter-logging-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\ch\qos\logback\logback-classic\1.2.11\logback-classic-1.2.11.jar;C:\Users\kimwoosung\.m2\repository\ch\qos\logback\logback-core\1.2.11\logback-core-1.2.11.jar;C:\Users\kimwoosung\.m2\repository\org\apache\logging\log4j\log4j-to-slf4j\2.17.2\log4j-to-slf4j-2.17.2.jar;C:\Users\kimwoosung\.m2\repository\org\apache\logging\log4j\log4j-api\2.17.2\log4j-api-2.17.2.jar;C:\Users\kimwoosung\.m2\repository\org\slf4j\jul-to-slf4j\1.7.36\jul-to-slf4j-1.7.36.jar;C:\Users\kimwoosung\.m2\repository\jakarta\annotation\jakarta.annotation-api\1.3.5\jakarta.annotation-api-1.3.5.jar;C:\Users\kimwoosung\.m2\repository\org\yaml\snakeyaml\1.29\snakeyaml-1.29.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-json\2.6.7\spring-boot-starter-json-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\core\jackson-databind\2.13.2.1\jackson-databind-2.13.2.1.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\core\jackson-annotations\2.13.2\jackson-annotations-2.13.2.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\core\jackson-core\2.13.2\jackson-core-2.13.2.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\datatype\jackson-datatype-jdk8\2.13.2\jackson-datatype-jdk8-2.13.2.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\datatype\jackson-datatype-jsr310\2.13.2\jackson-datatype-jsr310-2.13.2.jar;C:\Users\kimwoosung\.m2\repository\com\fasterxml\jackson\module\jackson-module-parameter-names\2.13.2\jackson-module-parameter-names-2.13.2.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-tomcat\2.6.7\spring-boot-starter-tomcat-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\apache\tomcat\embed\tomcat-embed-core\9.0.62\tomcat-embed-core-9.0.62.jar;C:\Users\kimwoosung\.m2\repository\org\apache\tomcat\embed\tomcat-embed-el\9.0.62\tomcat-embed-el-9.0.62.jar;C:\Users\kimwoosung\.m2\repository\org\apache\tomcat\embed\tomcat-embed-websocket\9.0.62\tomcat-embed-websocket-9.0.62.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-web\5.3.19\spring-web-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-beans\5.3.19\spring-beans-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-webmvc\5.3.19\spring-webmvc-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-aop\5.3.19\spring-aop-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-context\5.3.19\spring-context-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-expression\5.3.19\spring-expression-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-core\5.3.19\spring-core-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-jcl\5.3.19\spring-jcl-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\joda-time\joda-time\2.10.14\joda-time-2.10.14.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-thymeleaf\2.6.7\spring-boot-starter-thymeleaf-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\thymeleaf\thymeleaf-spring5\3.0.15.RELEASE\thymeleaf-spring5-3.0.15.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\org\thymeleaf\thymeleaf\3.0.15.RELEASE\thymeleaf-3.0.15.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\org\attoparser\attoparser\2.0.5.RELEASE\attoparser-2.0.5.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\org\unbescape\unbescape\1.1.6.RELEASE\unbescape-1.1.6.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\org\thymeleaf\extras\thymeleaf-extras-java8time\3.0.4.RELEASE\thymeleaf-extras-java8time-3.0.4.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\boot\spring-boot-starter-data-redis\2.6.7\spring-boot-starter-data-redis-2.6.7.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\data\spring-data-redis\2.6.4\spring-data-redis-2.6.4.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\data\spring-data-keyvalue\2.6.4\spring-data-keyvalue-2.6.4.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\data\spring-data-commons\2.6.4\spring-data-commons-2.6.4.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-tx\5.3.19\spring-tx-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-oxm\5.3.19\spring-oxm-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\org\springframework\spring-context-support\5.3.19\spring-context-support-5.3.19.jar;C:\Users\kimwoosung\.m2\repository\io\lettuce\lettuce-core\6.1.8.RELEASE\lettuce-core-6.1.8.RELEASE.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-common\4.1.76.Final\netty-common-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-handler\4.1.76.Final\netty-handler-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-resolver\4.1.76.Final\netty-resolver-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-buffer\4.1.76.Final\netty-buffer-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-codec\4.1.76.Final\netty-codec-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\netty\netty-transport\4.1.76.Final\netty-transport-4.1.76.Final.jar;C:\Users\kimwoosung\.m2\repository\io\projectreactor\reactor-core\3.4.17\reactor-core-3.4.17.jar;C:\Users\kimwoosung\.m2\repository\org\reactivestreams\reactive-streams\1.0.3\reactive-streams-1.0.3.jar;C:\Users\kimwoosung\.m2\repository\redis\clients\jedis\4.2.0\jedis-4.2.0.jar;C:\Users\kimwoosung\.m2\repository\org\slf4j\slf4j-api\1.7.36\slf4j-api-1.7.36.jar;C:\Users\kimwoosung\.m2\repository\org\apache\commons\commons-pool2\2.11.1\commons-pool2-2.11.1.jar;C:\Users\kimwoosung\.m2\repository\org\json\json\20211205\json-20211205.jar;C:\Users\kimwoosung\.m2\repository\com\google\code\gson\gson\2.8.9\gson-2.8.9.jar com.example.messagingredis.MessagingRedisApplication

.   ____          _            __ _ _
/\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
\\/  ___)| |_)| | | | | || (_| |  ) ) ) )
'  |____| .__|_| |_|_| |_\__, | / / / /
=========|_|==============|___/=/_/_/_/
:: Spring Boot ::                (v2.6.7)

2022-05-13 11:20:32.766  INFO 25996 --- [           main] c.e.m.MessagingRedisApplication          : Starting MessagingRedisApplication using Java 18.0.1.1 on DESKTOP-ILNB4AE with PID 25996 (C:\githubdev\springGuides\startSpringGuides\target\classes started by kimwoosung in C:\githubdev\springGuides\startSpringGuides)
2022-05-13 11:20:32.771  INFO 25996 --- [           main] c.e.m.MessagingRedisApplication          : No active profile set, falling back to 1 default profile: "default"
2022-05-13 11:20:33.537  INFO 25996 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Multiple Spring Data modules found, entering strict repository configuration mode!
2022-05-13 11:20:33.540  INFO 25996 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Bootstrapping Spring Data Redis repositories in DEFAULT mode.
2022-05-13 11:20:33.565  INFO 25996 --- [           main] .s.d.r.c.RepositoryConfigurationDelegate : Finished Spring Data repository scanning in 8 ms. Found 0 Redis repository interfaces.
2022-05-13 11:20:34.316  INFO 25996 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-05-13 11:20:34.327  INFO 25996 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-05-13 11:20:34.328  INFO 25996 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.62]
2022-05-13 11:20:34.457  INFO 25996 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-05-13 11:20:34.457  INFO 25996 --- [           main] w.s.c.ServletWebServerApplicationContext : Root WebApplicationContext: initialization completed in 1605 ms
2022-05-13 11:20:35.395  INFO 25996 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-05-13 11:20:36.099  INFO 25996 --- [           main] c.e.m.MessagingRedisApplication          : Started MessagingRedisApplication in 3.959 seconds (JVM running for 4.549)
2022-05-13 11:20:36.101  INFO 25996 --- [           main] c.e.m.MessagingRedisApplication          : Sending message...
2022-05-13 11:20:36.120  INFO 25996 --- [    container-2] com.example.messagingredis.Receiver      : Received <Hello from Redis!>

Process finished with exit code 0
</pre>
