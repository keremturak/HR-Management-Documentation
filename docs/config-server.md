## Config microservice

#### api-gateway-service-application

``` yaml
server:
  port: 80

spring:
  application:
    name: api-gateway-service
  main:
    web-application-type: reactive
  cloud:
    gateway:
      globalcors:
        add-to-simple-url-handler-mapping: true
        cors-configurations:
          '[/**]':
            allowedOrigins: "*"
            allowedHeaders: "*"
            allowedMethods:
              - GET
              - POST
              - PUT
              - DELETE
      default-filters:
        - RewritePath= /(?<segment>.*) , /api/v1/$\{segment}
      routes:
        - id: auth-service
          uri: http://localhost:9090
          predicates:
            - Path=/auth/**
          filters:
            - DedupeResponseHeader=Access-Control-Allow-Credentials Access-Control-Allow-Origin
            - name: CircuitBreaker
              args:
                name: auth
                fallbackUri: forward:/fallback/auth
        - id: user-service
          uri: http://localhost:9095
          predicates:
            - Path=/user/**
          filters:
            - DedupeResponseHeader=Access-Control-Allow-Credentials Access-Control-Allow-Origin
            - name: CircuitBreaker
              args:
                name: user
                fallbackUri: forward:/fallback/user
        - id: mail-service
          uri: http://localhost:7071
          predicates:
            - Path=/mail/**
          filters:
            - DedupeResponseHeader=Access-Control-Allow-Credentials Access-Control-Allow-Origin
            - name: CircuitBreaker
              args:
                name: mail
                fallbackUri: forward:/fallback/mail
        - id: company-service
          uri: http://localhost:9091
          predicates:
            - Path=/company/**
          filters:
            - DedupeResponseHeader=Access-Control-Allow-Credentials Access-Control-Allow-Origin
            - name: CircuitBreaker
              args:
                name: company
                fallbackUri: forward:/fallback/company
        - id: comment-service
          uri: http://localhost:9093
          predicates:
            - Path=/comment/**
          filters:
            - DedupeResponseHeader=Access-Control-Allow-Credentials Access-Control-Allow-Origin
            - name: CircuitBreaker
              args:
                name: comment
                fallbackUri: forward:/fallback/comment
```


#### auth-application

``` yaml
server:
  port: 9090

spring:
  mvc:
    servlet:
      cors:
        allow-credentials: false
  datasource:
    driver-class-name: org.postgresql.Driver
    url: "jdbc:postgresql://localhost:5432/AuthDB"
    username: "postgres"
    password: ${POSTGRES_PASS}
  jpa:
    hibernate:
      ddl-auto: update
  rabbitmq:
    host: localhost
    port: 5672
    username: ${RABBITMQ_USERNAME}
    password: ${RABBITMQ_PASS}
```

#### comment-application

```yaml
server:
  port: 9093

spring:
  data:
    mongodb:
      host: localhost
      port: 27017
      database: hrcommentdb
      username: ${MONGO_USERNAME_COMMENT}
      password: ${MONGO_PASS_COMMENT}
  rabbitmq:
    host: localhost
    port: 5672
    username: ${RABBITMQ_USERNAME}
    password: ${RABBITMQ_PASS}

```
#### company-application

```yaml
server:
  port: 9091

spring:
  data:
    mongodb:
      host: localhost
      port: 27017
      database: hrcompanydb
      username: ${MONGO_USERNAME_COMPANY}
      password: ${MONGO_PASS_COMPANY}
  rabbitmq:
    host: localhost
    port: 5672
    username: ${RABBITMQ_USERNAME}
    password: ${RABBITMQ_PASS}


```
#### mail-application

```yaml
server:
  port: 7071

spring:
  mail:
    username: ${MAIL_USERNAME}
    password: ${MAIL_PASSWORD}
    host: smtp.gmail.com
    port: 587
    properties:
      mail:
        smtp:
          auth: true
          starttls:
            enable: true
  rabbitmq:
    host: localhost
    port: 5672
    username: ${RABBITMQ_USERNAME}
    password: ${RABBITMQ_PASS}

```

#### user-application

```yaml
server:
  port: 9095

  tomcat:
    max-http-header-size: 819200

spring:
  data:
    mongodb:
      host: localhost
      port: 27017
      database: hruserdb
      username: ${MONGO_USERNAME_USER}
      password: ${MONGO_PASS_USER}
  rabbitmq:
    host: localhost
    port: 5672
    username: ${RABBITMQ_USERNAME}
    password: ${RABBITMQ_PASS}

```