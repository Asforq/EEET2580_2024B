# HoverSprite Organic Sprayer Management System

## Project Overview
HoverSprite is a Vietnamese agricultural solutions company specializing in organic fertilizer and pesticide spraying services using a fleet of drones. The aim of this project is to digitize their current manual processes, enhancing operational efficiency and customer experience.

## Project Goals
- Streamline operations by digitizing order processing and service delivery.
- Enhance customer experience with an intuitive UI and responsive design.
- Ensure scalability and future service expansion.

## Key Functionalities
1. Customer Registration and Sign-in
2. Spray Booking and Order Management
3. Service Delivery Tracking
4. Customer Feedback and Service Quality Rating

## Requirements Breakdown

### Level 0: Initial Design
- **Data Model**: Develop an ER Model for the database.
- **System Architecture**: Create architecture diagrams using UML or C4 models.
- **User Interface**: Design UI aligned with Nielsen's heuristics for user-friendly experience.

### Level 1: Basic Functionality
- **Customer Registration and Sign-in**:
  - Implement registration, sign-in, and basic user profile.
  - Ensure password security with hashing.
- **Spray Booking and Order Management**:
  - Provide UI for booking spray orders.
  - Display available spraying sessions and calculate total cost.
- **Service Delivery**:
  - Track order status (Pending, Confirmed, Assigned, In Progress, Completed).
- **Customer Feedback**:
  - Enable feedback submission with text and rating.

### Level 2: Enhanced Usability
- **Enhanced Registration and Sign-in**:
  - Secure sign-in with JSON Web Signature.
  - Input validation for name, phone, and email.
- **Enhanced Booking and Management**:
  - DateTimePicker for flexible date-time specification.
  - Automatic suggestion for sprayer assignment.
  - Support for online payment.
- **Enhanced Service Delivery**:
  - Real-time notification box for status updates.
- **Enhanced Feedback**:
  - Additional rating criteria for sprayer team performance.

### Level 3: Advanced Features
- **Advanced Registration and Sign-in**:
  - Implement OAuth 2 for Google and Facebook authentication.
- **Advanced Booking and Management**:
  - Weekly calendar view for booking time slots.
  - Pagination or lazy loading for order management.
- **Advanced Service Delivery**:
  - Route planning for sprayers.
  - Dual confirmation of service completion with QR code scanning.
- **Advanced Feedback**:
  - Allow image uploads in feedback.
- **System Architecture**:
  - Design a modular monolith architecture using Spring Boot.

## Task Assignments
1. **Data Model Design and Database Construction**
   - Team Member 1: Develop the conceptual data model and implement the database schema.

2. **System Architecture Design and Back-end Development**
   - Team Member 2: Create UML Component Diagrams, justify architectural decisions, and implement Spring Boot components.

3. **UI/UX Design and Front-end Development**
   - Team Member 3: Align UI with Nielsen heuristics, provide examples and justifications for UI decisions, and develop the React components (if using React).

4. **Documentation and Integration**
   - Team Member 4: Contribute to a comprehensive 25-page report, ensure documentation is thorough, and oversee integration of front-end and back-end components.

## Project Management
- **GitHub Usage**:
  - Use GitHub for version control and collaboration.
  - Regular commits and documentation of contributions.
- **Milestones**:
  - Initial design completion (Level 0) – Week 1-2.
  - Basic functionality (Level 1) – Week 3-4.
  - Enhanced usability (Level 2) – Week 5-6.
  - Advanced features (Level 3) – Week 7-8.
- **Meetings**:
  - Weekly progress meetings to ensure alignment and address any challenges.

By following this structured plan, our team can effectively develop a robust, user-friendly web application for HoverSprite, meeting their operational needs and enhancing their service delivery to farmers.

## Data Model

### Entities and Attributes
1. **Farmer**
   - FarmerID (Primary Key)
   - FullName
   - PhoneNumber
   - Email
   - Address
   - Password (hashed)
   
2. **Receptionist**
   - ReceptionistID (Primary Key)
   - FullName
   - PhoneNumber
   - Email (hoversprite.com domain)
   - Expertise (Apprentice, Adept, Expert)
   - Password (hashed)
   
3. **Sprayer**
   - SprayerID (Primary Key)
   - FullName
   - PhoneNumber
   - Email (hoversprite.com domain)
   - Expertise (Apprentice, Adept, Expert)
   - Password (hashed)
   
4. **SprayOrder**
   - OrderID (Primary Key)
   - FarmerID (Foreign Key)
   - ReceptionistID (Foreign Key)
   - CropType (Fruit, Cereal, Vegetable)
   - FarmlandArea
   - DesiredDate
   - DesiredTime
   - GregorianDate
   - LunarDate
   - TotalCost
   - Status (Pending, Confirmed, Assigned, In Progress, Completed)
   
5. **Assignment**
   - AssignmentID (Primary Key)
   - OrderID (Foreign Key)
   - SprayerID (Foreign Key)
   - AssignmentDate
   - AssignmentTime
   
6. **Feedback**
   - FeedbackID (Primary Key)
   - OrderID (Foreign Key)
   - Rating (1 to 5)
   - Comments
   - AttentivenessRating (1 to 5)
   - FriendlinessRating (1 to 5)
   - ProfessionalismRating (1 to 5)
   
7. **Notification**
   - NotificationID (Primary Key)
   - UserID (Foreign Key, can be FarmerID or SprayerID)
   - Message
   - NotificationDate
   - NotificationTime
   - IsRead (Boolean)
   
8. **Payment**
   - PaymentID (Primary Key)
   - OrderID (Foreign Key)
   - Amount
   - PaymentDate
   - PaymentMethod (Cash, Visa, MasterCard)

### Relationships
- A **Farmer** can have multiple **SprayOrders**.
- A **Receptionist** can manage multiple **SprayOrders**.
- A **SprayOrder** can have multiple **Assignment
