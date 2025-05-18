# Airbnb Clone Project

## Overview
The **Airbnb Clone Project** is a comprehensive, real-world application designed to simulate the development of a robust booking platform similar to Airbnb. This repository will guide you through building a scalable, secure, and maintainable web application, focusing on backend architecture, database design, API development, and CI/CD.

## Project Goals
- **Repository Management:** Establish a clean, well-documented GitHub repository following industry best practices.
- **Backend Architecture:** Design and implement a modular Django-based backend with REST and GraphQL APIs.
- **Database Design:** Model a relational database schema in MySQL that captures users, listings, bookings, reviews, and payments.
- **API Security:** Apply authentication, authorization, and data validation to safeguard endpoints and user data.
- **CI/CD Integration:** Configure automated pipelines using GitHub Actions (or equivalent) for testing, linting, and deployment.
- **Team Collaboration:** Document roles, workflows, and code conventions to enable seamless collaboration in a team environment.

## Team Roles
- **Project Manager:** Oversees project timeline, coordinates between stakeholders, and ensures milestones are met.
- **Backend Developer:** Implements server-side logic using Django, develops REST and GraphQL APIs, and handles business logic.
- **Database Administrator:** Designs and maintains the MySQL database schema, ensures data integrity, manages migrations, and optimizes queries.
- **Frontend Developer:** (When applicable) Integrates with API endpoints, implements UI components, and ensures responsive design.
- **DevOps Engineer:** Configures Docker containers, sets up CI/CD pipelines with GitHub Actions, and manages deployment processes.
- **Security Engineer:** Implements authentication and authorization mechanisms, audits code for vulnerabilities, and enforces best security practices.
- **QA Engineer:** Writes and executes test cases, performs automated and manual testing, and ensures application quality.

## Technology Stack Overview
| Technology               | Purpose in Project                                                      |
|--------------------------|-------------------------------------------------------------------------|
| **Django**               | A Python web framework used to build the application’s backend APIs.    |
| **Django REST Framework**| Extension of Django for building robust RESTful APIs with serializers and viewsets. |
| **Graphene-Django**      | Integrates GraphQL support into Django for flexible query and mutation capabilities. |
| **MySQL**                | Relational database for storing application data like users, listings, and bookings. |
| **Docker & Docker Compose** | Containerization tools to package and orchestrate application services consistently. |
| **Git & GitHub**         | Version control and repository hosting for collaborative development and code reviews. |
| **GitHub Actions**       | CI/CD platform for automating testing, linting, and deployment workflows. |
| **JSON Web Tokens (JWT)**| Authentication mechanism for securing API endpoints and managing user sessions. |

## Database Design
Below are the key entities and their primary fields, along with relationships between them:

### Users
- **id** (PK)
- **username**
- **email**
- **password**
- **role**

*A user can own multiple properties, create multiple bookings, write reviews, and make payments.*

### Properties
- **id** (PK)
- **title**
- **description**
- **owner_id** (FK ? Users.id)
- **location**

*A property belongs to a user and can have many bookings and reviews.*

### Bookings
- **id** (PK)
- **user_id** (FK ? Users.id)
- **property_id** (FK ? Properties.id)
- **start_date**
- **end_date**

*A booking belongs to a user and a property, and is associated with one payment record.*

### Reviews
- **id** (PK)
- **user_id** (FK ? Users.id)
- **property_id** (FK ? Properties.id)
- **rating**
- **comment**

*A review is created by a user for a specific property.*

### Payments
- **id** (PK)
- **booking_id** (FK ? Bookings.id)
- **amount**
- **payment_date**
- **status**

*A payment is tied to a booking and tracks transaction details.*

---
*Initialized on May 18, 2025.*  
