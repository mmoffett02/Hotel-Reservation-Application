# D387 Advanced Java

## Project Information
**Student ID:** 012029134

## Part B1: Localization and Internationalization
### Description
Modified the Landon Hotel scheduling application to display a welcome message in both English and French by creating resource bundles and applying them using different threads for each language.

### Endpoints
- `/welcome?lang=en`: Displays welcome message in English
- `/welcome?lang=fr`: Displays welcome message in French

## Part B2: Display Prices in Different Currencies
### Description
Modified the front end to display the price for a reservation in U.S. dollars (USD), Canadian dollars (CAD), and euros (EUR) on different lines.

## Part B3: Time Zone Conversion for Presentation
### Description
Added functionality to display the time for an online live presentation held at the Landon Hotel in Eastern Time (ET), Mountain Time (MT), and Coordinated Universal Time (UTC).

### Endpoints
- `/presentation`: Displays a message stating the presentation time in ET, MT, and UTC.

### Part C1: Dockerfile Creation and Docker Image Build
For part C1, we created a Dockerfile to containerize the application and built a Docker image.

#### Dockerfile
```dockerfile
FROM openjdk:11
COPY ./target/D387_sample_code-0.0.2-SNAPSHOT.jar /usr/src/D387_sample_code-0.0.2-SNAPSHOT.jar
WORKDIR /usr/src
EXPOSE 8080
CMD ["java", "-jar", "D387_sample_code-0.0.2-SNAPSHOT.jar"]