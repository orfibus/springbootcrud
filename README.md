# Documentation

## Description

```springbootcrud``` is a sample project of a spring boot + vue.js web application. The application consists of a vue.js front-end web client and a spring-boot served back-end server application. The server application features some basic REST API implementation that handles crud operations for 2 data entities (Persons and Suppliers). The front-end provides a user-friendly interface that supports all crud operations and search over the data.

## Build instructions

To build the project you need to install the following dependencies:

- OpenJDK 1.8
- Maven 3.x
- Git 2.x
- MySQL 5.x or newer
- Node.js 6.x

After you have successfully installed the dependencies you need to:

1. Clone or download this git repository
```git clone https://github.com/orfibus/springbootcrud.git```
2. Import the project in an IDE i.e. VsCode or IntellijIDEA
3. Reload the master pom.xml located in the `springbootcrud` folder in order for Maven to download all necessary dependencies.

After the project has been imported it is time to configure and run the server application:

1. Create an empty database with name: springbootcrud
2. Open the file: `springbootcrud-webapp/src/main/resources/application.properties` and
modify the following properties, depending on your MySQL installation:
    - `spring.datasource.username=root`
    - `spring.datasource.password=root`
3. Open the file: `springbootcrud-domain/src/main/resources/liquibase.properties`and
modify the following properties, depending on your MySQL installation exactly as the previous step:
    - `username=root`
    - `password=root`
4. Open `springbootcrud-domain` folder in terminal and run `mvn liquibase:update` to create the data tables in the database with Liquibase.
5. Then run the `Application.class` to start the server application (back-end).

Finally, you have to build and run the client application (front-end)

1. Be sure that you are in the `springbootcrud-client` folder and execute the following
command: `npm install`
2. When the installation will be finished you can run the Client with: `npm run dev`
3. Then you can visit http://localhost:9000

## Thoughts and Observations
 1. Sample project needs update on Liquibase version if used with newer MySQL versions. Liquibase version 4.4.3 was tested and works. Also, MySQL connector needs update to a version over 8.0.0 since important JDBC API changes were introduced, version 8.0.20 was tested and works. The reason I updated MySQL connector and Liquibase, was that I already maintain some databases in the computer I used to develop the project, and I did not wish to install an older MySQL version.
