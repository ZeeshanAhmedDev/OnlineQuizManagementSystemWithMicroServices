# OnlineQuizManagementSystemWithMicroServices

**Application Overview:**
Quiz-App-Microservices is a Java application developed using Spring Boot, Spring Cloud Eureka Server, Feign Client, Hibernate, JPA, and Maven. It's designed as a microservices-based system that facilitates student assessments during lectures. Here's how to build and deploy it.

**Building the Application:**

* **Step 1: Clone the Repository**
    - Clone the repository into your Integrated Development Environment (IDE). We recommend using IntelliJ IDEA.

* **Step 2: Cleaning and Installing**
    - In the Maven module, expand the Lifecycle and click "clean" for each of the Spring Boot microservice applications.
    - After cleaning, click "install" for each of the Spring Boot microservice applications.
    - You'll see a "BUILD SUCCESS" message in your terminal window, and relevant JAR files will be generated in the target folder of each project directory.

**Deploying the Application:**

* **Step 1: Open the Main Module**
    - Open the main Project in your project explorer.

* **Step 2: Building Microservices with Docker-Compose**
    - Open a command prompt or run cmd as an administrator.
    - Navigate to your project directory.
    - Run the command `docker-compose build`. This will build each microservice.
    - Run the command `docker-compose up`. This will build each microservice.


* **Step 3: Running Microservices**
    - After building, run the command `docker-compose up`. This will start each microservice.
    - Ensure that ports 8761, 8080, 8089, and 8088 are available, as the microservices will deploy on these ports with databases using ports 3306, 3307, and 3308.

* **Step 4: Verify All Microservices Are Running**
    - Confirm that all microservices are up and running.

* **Step 5: Accessing the Application**
    - Open your web browser and go to the URL: [http://localhost:8080/](http://localhost:8080/).
    - The application should start running.

**Application Architecture:**

The application is built using a microservices-based distributed system architecture:

* **Spring Cloud Eureka Server:**
    - This server registers each microservice as an instance, and you can access it via [http://localhost:8761/](http://localhost:8761/).

* **QuizApp-Frontend:**
    - This is the frontend layer developed using Thymeleaf. It acts as a client for the Eureka Server and communicates with other microservices through the Feign client.

* **Questions-Microservice and Result-Microservice:**
    - These microservices contain the core business logic of the application. They handle decision-making, calculations, evaluations, and data processing.
    - These microservices also interact with databases to save and retrieve application data.
    - Both are clients of the Eureka Server for service discovery.

This architecture allows for a scalable and efficient application for student assessments during lectures.
