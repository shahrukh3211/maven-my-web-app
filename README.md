# maven-my-web-app
# My Web App

My Web App is a simple Java web application built with Maven and deployed on Tomcat. This project demonstrates how to build a Java web application using Maven, package it as a WAR file, and deploy it using Docker.

## Prerequisites

- Docker
- Docker Compose
- Maven

## Project Structure

my-web-app/
├── Dockerfile
├── docker-compose.yml
├── pom.xml
└── src/
├── main/
│ ├── java/
│ ├── resources/
│ └── webapp/
│ ├── WEB-INF/
│ │ └── web.xml
│ └── index.jsp
└── test/
└── java/


## Getting Started

### Clone the Repository

```bash
git clone https://github.com/shahrukh3211/maven-my-web-app/
cd my-web-app

Build and Run the Application with Docker Compose
Build the Docker images and start the containers:
docker-compose up --build

Access the web application:

Open your web browser and navigate to http://localhost:8080/my-web-app.

Project Details
pom.xml: Maven configuration file.
src/main/webapp/index.jsp: The main JSP file displaying "Hello World!".
src/main/webapp/WEB-INF/web.xml: Deployment descriptor for the web application.
Dockerfile: Defines the build steps for the Docker image.
docker-compose.yml: Docker Compose configuration file.
Volumes
The docker-compose.yml file includes a volume mapping:
services:
  my-web-app:
    build: .
    ports:
      - "8080:8080"
    volumes:
      - ./data:/usr/local/tomcat/webapps  # Persisting webapps directory

This configuration ensures that the Tomcat webapps directory is persisted to the ./data directory on your host machine.

Building the WAR file with Maven
If you prefer to build the WAR file manually without Docker:
mvn clean package

The WAR file will be generated in the target directory.

Testing
This project includes a sample dependency for JUnit:
<dependency>
  <groupId>junit</groupId>
  <artifactId>junit</artifactId>
  <version>3.8.1</version>
  <scope>test</scope>
</dependency>

Run tests using Maven:
mvn test

Contributing
Contributions are welcome! Please open an issue or submit a pull request for any changes.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
Maven
Tomcat
Docker
