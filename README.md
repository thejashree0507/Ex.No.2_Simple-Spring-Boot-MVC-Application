# Exp_2_Simple-Spring-Boot-MVC-Application

## AIM:
To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM:
1.Create a New Spring Boot Project:

2.Use Spring Initializr

3.Add dependencies:

- Spring Web

- Thymeleaf

4.Set Up Project Structure:

- Create the main class annotated with @SpringBootApplication

- Create a Controller class using @Controller

- Add HTML templates under src/main/resources/templates

- Create a Controller:

- Define a method to handle HTTP GET requests using @GetMapping

- Return a view name (HTML page name) from the controller

- Pass data to the view using Model object

5. Create a Model (Optional):

Define a simple POJO class if you need to pass structured data to the view

6. Create View Pages (HTML using Thymeleaf):

Create an HTML file inside the templates folder

Use Thymeleaf syntax (e.g., ${name}) to render dynamic content

7. Run the Application:

Run the Spring Boot application from your IDE or command line

Access the Application:

Open a browser and navigate to http://localhost:8082/
## PROGRAM
```
spring-mvc-demo/
├── src/
│   └── main/
│       ├── java/
│       │   └── com.example.mvc/
│       │       ├── MvcApplication.java
│       │       └── HomeController.java
│       └── resources/
│           ├── templates/
│           │   └── index.html
│           └── application.properties
├── pom.xml
```
### pom.xml :

<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
                             http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>spring-mvc-demo</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>Spring MVC Demo</name>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.1.2</version>
    </parent>

    <dependencies>
        <!-- Spring Web -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <!-- Thymeleaf for View Rendering -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-thymeleaf</artifactId>
        </dependency>
    </dependencies>
</project>

### MvcApplication.java (Main Class):
```java
package com.example.mvc;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MvcApplication {
    public static void main(String[] args) {
        SpringApplication.run(MvcApplication.class, args);
    }
}
```
### HomeController.java (Controller):
```java
package com.example.mvc;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {
        model.addAttribute("message", "Welcome to Spring Boot MVC!");
        return "index";  // refers to index.html in templates folder
    }
}
```
### index.html (View – inside src/main/resources/templates/):

<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Spring MVC</title>
</head>
<body>
    <h1 th:text="${message}">Default Message</h1>
</body>
</html>

### application.properties:
 server.port=8082

### Output:

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/b5feed12-2373-4b4b-85a2-82bebd868375" />


<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/68be863b-8ed0-4d75-b8b9-b2780a7307e6" />

### result:

Thus, the Simple Spring Boot MVC Application was successfully developed and executed using Maven and Thymeleaf. The welcome message was displayed successfully in the web browser.
