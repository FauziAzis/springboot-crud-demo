# springboot-crud-demo

Spring Boot CRUD demo is demonstrating how to implement simple CRUD operations with a `Product` entity.

## What's inside 
This project is based on the [Spring Boot](http://projects.spring.io/spring-boot/) project and uses these packages :
- Maven
- Spring Core
- Spring Data (Hibernate & MySQL)
- Spring MVC (Tomcat)
- [Thymleaf](https://thymeleaf.org)

![demo](https://cl.ly/sEGH/Screen%20Recording%202018-06-11%20at%2010.34%20AM.gif)

## Installation 
The project is created with Maven, so you just need to import it to your IDE and build the project to resolve the dependencies

## Database configuration 
Create a MySQL database with the name `springbootdb` and add the credentials to `/resources/application.properties`.  
The default ones are :

```
spring.datasource.url=jdbc:mysql://localhost:3306/springbootdb
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
```

## Oracle Database + HikaryCP Configuration
* Download and add `ojdbc` according to database version `https://www.oracle.com/database/technologies/faq-jdbc.html`
```
mvn install:install-file -Dfile=path/to/your/ojdbc6.jar -DgroupId=com.oracle -DartifactId=ojdbc6 -Dversion=11.2.0.4 -Dpackaging=jar
```
* Edit `pom.xml` and add following dependency
```
<!--Oracle OJDBC -->
<dependency>
    <groupId>com.oracle</groupId>
    <artifactId>ojdbc6</artifactId>
    <version>11.2.0.2.0</version>
</dependency>

<!-- HikariCP connection pool -->
<dependency>
    <groupId>com.zaxxer</groupId>
    <artifactId>HikariCP</artifactId>
</dependency>
```
* Create Oracle Schema `springdb` with password `root` and add the credentials to `/resources/application.properties` The default ones are :
```
# Oracle settings
spring.datasource.url=jdbc:oracle:thin:@localhost:1521:xe
spring.datasource.username=springdb
spring.datasource.password=root

# HikariCP settings
spring.datasource.hikari.connection-timeout=60000
spring.datasource.hikari.maximum-pool-size=5
```

## Spring Boot Dev Tools
Add Spring Boot Dev Tools dependency to make development process easy. Developer does not have to restart after making changes
```
<!-- DevTool -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-devtools</artifactId>
</dependency>
```

## Change Default Port 
Go to `/resources/application.properties` and add following line `server.port:80`

## Usage 
Run the project through the IDE and head out to [http://localhost/](http://localhost/)

or 

run this command in the command line:
```
mvn spring-boot:run
```
