https://spring.io/guides/gs/accessing-data-neo4j/

git clone https://github.com/spring-guides/gs-accessing-data-neo4j.git

### Accessing Data with Neo4j


https://neo4j.com/download-thanks/?edition=community&release=4.4.6

<pre>
2022-05-13 18:01:15.607  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : Started AccessingDataNeo4jApplication in 3.318 seconds (JVM running for 3.861)
2022-05-13 18:01:16.084  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : Before linking up with Neo4j...
2022-05-13 18:01:16.086  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Greg's teammates => []
2022-05-13 18:01:16.086  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Roy's teammates => []
2022-05-13 18:01:16.086  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Craig's teammates => []
2022-05-13 18:01:16.794  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : Lookup each person by name...
2022-05-13 18:01:16.855  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Greg's teammates => [Roy, Craig]
2022-05-13 18:01:16.880  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Roy's teammates => [Craig]
2022-05-13 18:01:16.898  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : 	Craig's teammates => []
2022-05-13 18:01:16.935  INFO 14116 --- [  restartedMain] c.e.a.AccessingDataNeo4jApplication      : The following have Greg as a teammate...
2022-05-13 18:01:17.001  INFO 14116 --- [ionShutdownHook] o.neo4j.driver.internal.InternalDriver   : Closing driver instance 40473508
2022-05-13 18:01:17.003  INFO 14116 --- [ionShutdownHook] o.n.d.i.async.pool.ConnectionPoolImpl    : Closing connection pool towards localhost:7687
</pre>