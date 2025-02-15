# Shuttle Management System

A smart campus transit solution that streamlines shuttle operations and provides students with a seamless way to book rides, check wallet balances, view trip history, and receive optimal route suggestions based on their travel patterns.

---

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Project Structure](#project-structure)
- [API Endpoints and Sample JSON](#api-endpoints-and-sample-json)
- [Database Seeding](#database-seeding)
- [Getting Started](#getting-started)
- [Demo](#demo)
- [License](#license)

---

## Features

- **User Registration & Login:**  
  - Students register using their university email (ending with `@lpu.in`).  
  - Every new student is given a default wallet balance of 100 rupees.
- **Wallet Management:**  
  - Students can view their wallet balance.  
  - Only an admin can recharge a student's wallet.
- **Shuttle Booking:**  
  - **Get Available Shuttle Options:** The system calculates and displays the top 4 shuttle options based on the student's current location and destination.
  - **Confirm Booking:** Upon selection, the system deducts the corresponding fare from the student's wallet and confirms the booking.
- **Trip History & Route Suggestions:**  
  - Students can view their past trip history, including ride date, start and end stops, fare, and points deducted.
  - The system analyzes past travel patterns to suggest optimal routes.

---

## Technologies

- **Backend:** Java, Spring Boot, Spring Data JPA, Hibernate
- **Database:** PostgreSQL
- **Frontend:** HTML, Bootstrap 4, jQuery
- **Build Tool:** Maven

---

## Project Structure

```plaintext
ShuttleManagementSystem/
├── src/
│   ├── main/
│   │   ├── java/com/shuttle/SMS/
│   │   │   ├── config/                  # Configuration (e.g., security)
│   │   │   ├── controller/              # REST controllers (UserController, BookingController, WalletController, etc.)
│   │   │   ├── dto/                     # Data Transfer Objects (UserRegistrationDTO, LoginDTO, UserWalletResponseDTO, etc.)
│   │   │   ├── model/                   # JPA Entities (User, Booking, Route, Shuttle, Stop, etc.)
│   │   │   ├── repository/              # Spring Data JPA repositories
│   │   │   ├── service/                 # Business logic services (UserService, BookingService, RouteOptimizationService, etc.)
│   │   │   └── ShuttleManagementSystemApplication.java  # Main Spring Boot Application
│   ├── resources/
│   │   ├── application.properties       # Application configuration (DB connection, etc.)
│   │   ├── data.sql                     # SQL script for database seeding (sample data for stops, shuttles, routes, bookings, etc.)
│   │   └── static/
│   │       ├── index.html               # Frontend landing page and UI
│   │       └── index.js                 # Custom JavaScript for the UI
├── pom.xml                              # Maven configuration and dependencies
└── README.md                            # This file
