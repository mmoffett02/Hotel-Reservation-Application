# Hotel Reservation Application

## Overview

The Hotel Reservation Application is a comprehensive project designed to manage hotel reservations with enhanced features such as localization, internationalization, multithreading, and Docker containerization. This application is developed using Java with the Spring Framework for the backend, and Angular for the frontend, ensuring a robust and scalable architecture.

## Project Description

This application was developed as part of a software development course to meet new requirements under new management for the Landon Hotel scheduling application. The project includes various functionalities such as displaying welcome messages in multiple languages, showing prices in different currencies, and displaying times for events in various time zones. The project is containerized using Docker for easy deployment and scalability.

### Key Features

1. **Multithreaded Localization and Internationalization**:
   - The application displays a welcome message in both English and French using resource bundles.
   - Each language's welcome message is displayed using a different thread to demonstrate multithreading.

2. **Currency Display**:
   - The front end displays the price for a reservation in U.S. dollars ($), Canadian dollars (C$), and euros (€) on different lines.

3. **Time Zone Conversion**:
   - A Java method converts times between Eastern Time (ET), Mountain Time (MT), and Coordinated Universal Time (UTC).
   - The application displays a message showing the time for an online live presentation in all three time zones.

4. **Docker Containerization**:
   - The application is containerized using Docker.
   - A Dockerfile is provided to create a single image that includes all code and modifications.
   - Instructions and a screenshot for running the Docker image in a container are provided.

### Technologies Used

- **Spring Framework**: For building the Java backend.
- **Angular**: For the front-end interface.
- **Spring Data JPA**: For interacting with the relational database.
- **MySQL**: As the database to store reservation data.
- **JUnit**: For unit testing the application.
- **Lombok**: To reduce boilerplate code in Java.
- **Docker**: For containerizing the application.

### How to Run the Application

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/mmoffett02/Hotel-Reservation-Application.git
   cd Hotel-Reservation-Application
