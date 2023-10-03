Before you start using the project, make sure to follow the steps below. Please ensure that your configurations are complete before running the project

1. Clone the project from `GitHub`

2. Configure the `YAML` files.

3. Add dependencies.

4. Start the Config Server first.

5. Start the other services of the project.

6. Conduct tests using Swagger.

7. Begin to enjoy!


## **Cloning the Repository:**

1. Open the Terminal or Command Prompt.

2. Navigate to the directory where you want to clone the project. For example, if you want to create it in a folder on your desktop, type: `cd Desktop`.

3. Then, use the following command to clone the project:

   ```bash
   git clone <https://github.com/keremturak/hr-management-back-end.git>
   ```
   
   ```bash
   git clone <https://github.com/keremturak/hr-management-front-end.git>
   ```






## Configure the YAML files.

👉[Go To Yaml File](https://keremturak.github.io/HR-Management-Documentation/config-server/#config-microservice)

## Add Dependencies

|      | Tech     | Url |
|----| -------- | ------- |
|1| Spring Boot Data Jpa  | implementation 'org.springframework.boot:spring-boot-starter-data-jpa'    |
|2| tymelift | "org.thymeleaf:thymeleaf-spring5:3.0.11.RELEASE"    |
|3| springDataMongodb  | "org.springframework.boot:spring-boot-starter-data-mongodb:${versions.springBoot}"    |
|4| postgreSql  | "org.postgresql:postgresql:${versions.postgreSql}"    |
|5| springBootRabbitMQ  | "org.springframework.boot:spring-boot-starter-amqp:${versions.springBoot}"    |
|6| Spring Boot Web | implementation 'org.springframework.boot:spring-boot-starter-web'     |
|7| Lombok    |compileOnly 'org.projectlombok:lombok'-----annotationProcessor 'org.projectlombok:lombok'    |
|8| MySql  | implementation 'mysql:mysql-connector-java:8.0.33'    |
|9| Swagger Ui | implementation 'org.springdoc:springdoc-openapi-starter-webmvc-ui:2.1.0'     |
|10| Mapstruct    | implementation 'org.mapstruct:mapstruct:1.5.5.Final'   |
|11| Spring Boot Starter Mail  | implementation 'org.springframework.boot:spring-boot-starter-mail:3.1.1'   |
|12| javaJWT  | "com.auth0:java-jwt:${versions.jwt}"    |
|13| springCloudConfigServer | 	"org.springframework.cloud:spring-cloud-config-server:${versions.springCloud}"    |
|14| springCloudConfigClient | 	"org.springframework.cloud:spring-cloud-config-client:${versions.springCloud}"    |
|15| springCloudConfigStarter | 	"org.springframework.cloud:spring-cloud-starter-config:${versions.springCloud}"    |
|16| Validator | 	implementation  'org.hibernate.validator:hibernate-validator:8.0.0.Final'    |
|17| springCloudStarterApiGateway | 	"org.springframework.cloud:spring-cloud-starter-gateway:${versions.springCloud}"    |
|18| springCloudCircuitBreaker | 	"org.springframework.cloud:spring-cloud-starter-circuitbreaker-resilience4j:${versions.circuitBreaker}"    |
|19| springCloudCircuitReactor | 	"org.springframework.cloud:spring-cloud-starter-circuitbreaker-reactor-resilience4j:${versions.circuitBreaker}"    |
              



A plain codeblock:

```
Some Code here
def myfuntion()
//some comment
```
## Requirements

Some more code with the `py` at the start:

```	py
import tensorflow as tf
def whatever()
```
#### Environment Variables
`${MONGO_USERNAME_COMPANY}`
`${MONGO_PASS_COMPANY}` 
`${MONGO_USERNAME_COMMENT}` 
`${MONGO_PASS_COMMENT}` 
`${MONGO_USERNAME_USER}` 
`${MONGO_PASS_USER}` 
`${POSTGRES_PASS}` 
`${RABBITMQ_USERNAME}` 
`${RABBITMQ_PASS}` 
`${MAIL_USERNAME}` 
`${MAIL_PASSWORD}` 



## Starting the Config Server
You can start the `ConfigServerApplication` inside the config server, and this way, you can see which port it is running on.



<div style="text-align:center">
    <img src="https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/starting-config-server-1.png?raw=true" alt="Açıklama buraya" width="1000" height="100">
</div>
<div style="text-align:center">
    <img src="https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/starting-config-server-2.png?raw=true" alt="Açıklama buraya" width="1000" height="1000">
</div>







## Starting the Other Service

You should run the auth, user, comment, company, and mail services as applied in the example above.

## Conduct tests using Swagger.

👉[Go To End Points](https://keremturak.github.io/HR-Management-Documentation/Project%20Offerings/#end-points)

## Begin to enjoy!


<div style="text-align:center">
    <img src="https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/employee_dashboard.png?raw=true)https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/employee_dashboard.png?raw=true" alt="Açıklama buraya" width="1000" height="100">
</div>





