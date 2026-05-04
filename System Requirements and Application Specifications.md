# System Requirements and Application Specifications

---

## Chosen Development Model

### Model: Agile (Scrum)

### Justification:
Agile was selected because it allows flexibility and continuous improvement. The system can evolve based on user feedback, and Agile supports iterative development, fast feature delivery, and easy adaptation to changes.

---

## Stakeholders:

### Consumers:
Consumers are individuals who use the platform to search for and request surplus food. They can browse available food listings, view details such as location, ingredients, and quantity, and place requests based on their needs.

### Food Providers (Restaurants, Stores, Households):
Food providers create and publish surplus food listings by specifying food type, quantity, location, ingredients, and availability time in order to distribute excess food efficiently.

### Charities and Organizations:
Charities monitor available listings and receive notifications in order to collect and redistribute food to people in need.

### Development Team:
The development team designs, implements, tests, and maintains the system to ensure proper functionality.

### Admin:
The admin monitors platform activity, manages accounts and content, and ensures system security and proper operation.

---

## User Stories

- As a consumer, I want to create an account and log in using my credentials so that I can securely access the platform.
- As a food provider, I want to create and publish surplus food listings with details such as type, quantity, location, and ingredients so that the food can be distributed instead of wasted.
- As a consumer, I want to browse and search listings using keywords, location, or category so that I can find suitable food near me.
- As a charity organization, I want to receive notifications when new food listings are added so that I can act quickly.
- As an admin, I want to manage accounts and listings so that the system remains secure and organized.
- As a consumer, I want to receive real-time updates so that I do not miss available food.
- As a consumer, I want to reset my password through a secure process so that I can regain access to my account.
- As a consumer, I want to save listings so that I can access them later.
- As a consumer, I want to report inappropriate listings so that the platform remains safe.

---

## Functional Requirements

- The system shall allow consumers to register and log in using email and password.
- The system shall allow consumers to manage their profiles.
- The system shall allow food providers to create and manage food listings.
- The system shall allow consumers to browse, search, and filter listings.
- The system shall display detailed listing information, including ingredients and allergens.
- The system shall send notifications to consumers and charities.
- The system shall allow admins to manage accounts and content.
- The system shall allow consumers to reset passwords securely.
- The system shall provide real-time updates of listings.

---

## Non-Functional Requirements

### Performance:
The system shall load pages within 2 seconds and complete actions within 3–5 seconds.

### Usability:
The system shall provide a clear and intuitive interface with consistent navigation.

### Reliability:
The system shall maintain at least 99% uptime and operate without critical failures.

### Security:
The system shall protect data through authentication, authorization, and encryption.

### Scalability:
The system shall support increasing users without performance degradation.

---

## Architecture

The system follows a three-tier architecture:

- Frontend (Presentation Layer): Handles user interaction
- Backend (Application Layer): Processes logic and requests
- Database (Data Layer): Stores system data

The frontend communicates with the backend through APIs, and the backend interacts with the database.

---

## Database Model

### Users:
Stores account information (ID, name, email, password, role)

### Food Listings:
Stores food data (ID, title, quantity, location, ingredients)

### Notifications:
Stores alerts

### Relationships:
Listings are linked to providers, and notifications are linked to users.

### Constraints:
Emails must be unique, and listings must belong to valid users.

---

## Technologies Used

- Frontend: HTML, CSS, JavaScript
- Backend: Node.js (Express)
- Database: MySQL
- Version Control: GitHub

### Justification:
These technologies were selected because they are widely used, easy to implement, and suitable for building scalable and responsive web applications.

---

## User Interface Design

- Login/Register Page: Authentication interface
- Home Page: Displays food listings
- Post Listing Page: Allows providers to add food
- Notification Panel: Shows updates

The design focuses on simplicity and responsiveness.

---

## Security Measures

- The system shall implement secure authentication mechanisms.
- The system shall enforce role-based access control.
- The system shall validate user input.
- The system shall use HTTPS for secure communication.
