irBnB Clone Project

##  Overview

The **AirBnB Clone** is a full-stack web development project designed to mimic the core functionalities of the real AirBnB platform. It is part of the ALX Advanced Backend track and aims to help developers build a comprehensive understanding of web application architecture, API development, database modeling, and more.

This project will be developed incrementally, starting from a basic console application and evolving into a fully functioning web platform.

##  Project Goals

- Recreate the core features of the AirBnB website
- Build a custom backend system including data storage, RESTful APIs, and user management
- Learn best practices for backend architecture, security, and deployment
- Gain hands-on experience with Git, GitHub collaboration, and CI/CD workflows

##  Tech Stack

- **Programming Language:** Python 3
- **Framework:** Flask (for web app/API)
- **Storage:** MySQL (database), File Storage (initially)
- **ORM:** SQLAlchemy
- **Web Server:** Gunicorn (for production deployment)
- **Frontend:** HTML/CSS (basic templates)
- **Version Control:** Git & GitHub
- **Testing:** Unittest (Python's built-in test framework)

## Features to Implement

- Custom command-line interpreter
- Class models for users, places, states, cities, reviews, and amenities
- File and DB storage engines
- RESTful API endpoints
- Dynamic web pages with Flask
- Authentication and security measures
- Frontend integration

##  Repository Structure (To Be Updated)

airbnb-clone-project/
├── README.md
├── models/
├── tests/
├── web_static/
├── api/
├── console.py
└── ...

bash
Copy code

##  Getting Started

To run the project locally:

```bash
git clone https://github.com/haron-murumba/airbnb-clone-project.git
cd airbnb-clone-project
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python3 console.py
 Contributing
This project is developed as part of the ALX Software Engineering Program. Contributions are welcome from peers within the program.

## team roles

Team Roles

Below is a list of team roles and their responsibilities within the project:

Backend Developer
Responsible for building and maintaining the server-side logic of the application. They develop APIs, integrate with databases, ensure data flow, and implement business logic. Their work ensures that the application performs efficiently and securely behind the scenes.

 Frontend Developer
Focuses on the client-side of the application. They implement user interfaces based on design mockups, handle user interactions, and ensure responsiveness across devices and browsers using technologies like HTML, CSS, and JavaScript frameworks.
 Database Administrator (DBA)

Designs, implements, and manages the project's database systems. They ensure data integrity, security, backup, and performance tuning. The DBA works closely with backend developers to optimize queries and data structures.
 QA Engineer (Quality Assurance)

Responsible for testing the application to find bugs and ensure functionality meets requirements. They create test cases, perform manual and automated testing, and collaborate with developers to resolve issues and maintain quality standards.
Project Manager (PM)

Oversees the project from planning to delivery. The PM ensures the team follows timelines, meets deliverables, manages resources, and communicates with stakeholders. They also facilitate meetings and remove roadblocks.

 Business Analyst (BA)

Acts as a bridge between stakeholders and the technical team. They gather and document requirements, analyze business processes, and help ensure the final product aligns with business goals.

 UI/UX Designer

Designs the user interface and experience. They create wireframes, prototypes, and high-fidelity mockups, ensuring that the application is intuitive, accessible, and user-friendly.

Technology Stack

This project leverages a modern and scalable technology stack to ensure efficient development, performance, and maintainability.
Django
Purpose: A high-level Python web framework used to build secure and scalable web applications. In this project, Django is used to develop the backend and RESTful or GraphQL APIs.
PostgreSQL
Purpose: A powerful open-source relational database system. It is used for storing and managing structured data, such as user accounts, application content, and transactional records.
GraphQL

Purpose: A query language for APIs and a runtime for executing those queries. It allows clients to request exactly the data they need, reducing over-fetching and improving performance.
 Django REST Framework (DRF)
Purpose: A toolkit for building Web APIs in Django. It provides serialization, authentication, and view logic to expose backend functionality through RESTful endpoints.
JWT (JSON Web Tokens)
Purpose: Used for secure authentication. It ensures that users can log in and receive a token that allows them to access protected resources.
Pytest

Purpose: A testing framework used to write and run automated tests for the backend. It ensures the code works as expected and prevents bugs from being introduced.
Docker
Purpose: Used to containerize the application and its dependencies, making it easier to develop, test, and deploy consistently across environments.


Database Design

The database schema is designed to support core functionality like user management, property listings, bookings, reviews, and payments. Below are the key entities and their relationships.

Users

Represents all users in the system — guests, hosts, or admins.
Key Fields:

id: Primary key
name: Full name of the user
email: Unique email address
password_hash: Encrypted password
role: Defines whether the user is a guest, host, or admin
Relationships:
A user can own multiple properties
A user can make multiple bookings
A user can leave multiple reviews

 Properties

Represents properties listed by hosts for booking.
Key Fields:
id: Primary key
title: Name/title of the property
description: Detailed property info
location: Address or area
price_per_night: Cost of booking per night
owner_id: Foreign key referencing the user (host)

Relationships:

A property is owned by one user (host)
A property can have many bookings
A property can have many reviews

Bookings

Stores information about user reservations.
Key Fields:

id: Primary key
user_id: Foreign key referencing the user (guest)
property_id: Foreign key referencing the property
start_date: Check-in date
end_date: Check-out date
total_price: Total cost of the booking

Relationships:

A booking is made by one user
A booking is for one property
 Reviews
Captures feedback left by users about properties.

Key Fields:
id: Primary key
user_id: Foreign key referencing the reviewer
property_id: Foreign key referencing the property reviewed
rating: Numeric rating (e.g., 1–5)
comment: Optional textual feedback

Relationships:
A review is written by one user
A review belongs to one property

Payments

Handles payment information related to bookings.
Key Fields:

id: Primary key
booking_id: Foreign key referencing the booking

amount: Amount paid
payment_date: Date of payment
status: Payment status (e.g., paid, pending, failed)
Relationships:

A payment is linked to one booking

 Entity Relationships Summary

A User can:
Own multiple Properties
Make multiple Bookings
Write multiple Reviews
A Property can:

Be booked multiple times (Bookings)
Have multiple Reviews
A Booking:
Belongs to one User (guest)
Belongs to one Property
Has one Payment
A Review:
Belongs to one User
Belongs to one Property

A Payment:
Belongs to one Booking
