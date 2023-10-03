Before you start using the project, make sure to follow the steps below. Please ensure that your configurations are complete before running the project

1. Clone the project from `GitHub`

2. Configure the `YAML` files.

3. Add dependencies.
4. Requirements

5. Start the Config Server first.

6. Start the other services of the project.

7. Conduct tests using Swagger.

8. Begin to enjoy!


## **Cloning the Repository:**

![Sample Image](https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/GitHub_logo_2013.svg.png?raw=true)

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
![Sample Image]([\img\Gradle_logo.png])

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
              


## Requirements
![Sample Image](/img/requirements-1.png)

- Java 8 SE or newer versions are required.
- The application serves as a server for API file operations, saving multiple files to the image folder under resources.
- The application utilizes both PostgreSQL and MongoDB as databases.
- Docker must be installed to initialize both MongoDB and RabbitMQ.
- Exercise caution as numerous validation checks are in place when performing operations. Adhere to these validations for smooth operation.

---

## MongoDB Dockerize

![Sample Image](img\MongoDB_Fores-Green.svg.png)

 **Install Docker**

Ensure you have Docker installed on your system. You can download and install Docker from the [official Docker website](https://www.docker.com/get-started).



 **Pull MongoDB Docker Image:**

Open a terminal or command prompt and execute the following command to pull the official MongoDB Docker image:

```bash
docker pull mongo
```

 **Run MongoDB as a Docker Container:**

After pulling the image, you can run a MongoDB container using the following command:

    ```bash
    docker run -d --name mongodb-container -p 27017:27017 mongo
    ```

- `mongodb-container`: This is the name you assign to your Docker container. You can choose a different name if you prefer.
- `27017:27017`: This maps the port 27017 of the Docker container to the same port on your localhost.

## RabbitMQ Dockerize

![Sample Image](\img\RabbitMQ_logo.svg.png)

1. **Pull RabbitMQ Docker Image:**

    This command downloads the RabbitMQ Docker image.

2. **Running the RabbitMQ Container:**

    To start the RabbitMQ container, use the following command:

    ```bash
    docker run -d --name rabbitmq-container -p 5672:5672 -p 15672:15672 rabbitmq:3-management
    ```

    - `rabbitmq-container`: This is the name you assign to your Docker container. You can choose a different name if you prefer.
    - `5672:5672` and `15672:15672`: These map the ports used by RabbitMQ.

3. **Accessing the RabbitMQ Management Interface:**

    Open your browser and go to [http://localhost:15672](http://localhost:15672) to access the RabbitMQ management interface. The default username and password are "guest/guest".

4. **Stopping and Removing the RabbitMQ Container:**

    To stop and remove the RabbitMQ container, you can use the following commands:

    - Stop:

        ```bash
        docker stop rabbitmq-container
        ```

    - Remove:

        ```bash
        docker rm rabbitmq-container
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
<br>
<div style="text-align:center">
    <img src="https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/starting-config-server-2.png?raw=true" alt="Açıklama buraya" width="1000" height="1000">
</div>







## Starting the Other Service

You should run the auth, user, comment, company, and mail services as applied in the example above.

## Conduct tests using Swagger.

👉[Go To End Points](http://127.0.0.1:8000/Project%20Offerings/#end-points)

## Begin to enjoy!


<div style="text-align:center">
    <img src="https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/employee_dashboard.png?raw=true)https://github.com/keremturak/HR-Management-Documentation/blob/main/docs/img/employee_dashboard.png?raw=true" alt="Açıklama buraya" width="1000" height="100">
</div>





