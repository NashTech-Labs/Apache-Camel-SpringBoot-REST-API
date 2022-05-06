# spring-camel-rest-dsl
How to expose Rest API using Spring Boot with Apache Camel

## Dependencies we have to add for apache camel

<dependency>
			<groupId>org.apache.camel</groupId>
			<artifactId>camel-spring-boot-starter</artifactId>
			<version>2.24.0</version>
		</dependency>
<dependency>
			<groupId>org.apache.camel</groupId>
			<artifactId>camel-servlet-starter</artifactId>
			<version>2.24.0</version>
		</dependency>
<dependency>
			<groupId>org.apache.camel</groupId>
			<artifactId>camel-jackson</artifactId>
			<version>2.24.0</version>
		</dependency>

##  Rest APIs
### Post method
restConfiguration().component("servlet").port(9090).host("localhost").bindingMode(RestBindingMode.json);

		rest().post("/addOrder").consumes(MediaType.APPLICATION_JSON_VALUE).type(Order.class).outType(Order.class)
				.route().process(processor).endRest();

http://localhost:9090/addStudent

{

"name":"akshit",

"email":"akshit@gmail.com",

"course":"MCA"

}

### Get method

http://localhost:9090/getStudent 

it will return all students list


