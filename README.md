# Requirement-analysis
Requirement Analysis is a critical phase in the software development lifecycle (SDLC) where the project team gathers, analyzes, and defines the requirements of the software product to be developed
# What is Requirement-Analysis?
Requirement Analysis is a crucial phase of the Software Development Life Cycle (SDLC) in which the project team identifies, examines, and defines the software requirements. The goal is to establish a clear and shared understanding among stakeholders about what the system should do and how it should function.
This stage ensures that the final product aligns with user needs, business objectives, and technical feasibility before development begins.

Importance of   Requirement Analysis
1. Ensures Clarity and Shared Understanding

It bridges the communication gap between stakeholders and the development team, minimizing confusion and ensuring that everyone agrees on the system’s goals and functionality.

2. Defines the Project Scope

By outlining what the system will and will not include, it prevents scope creep uncontrolled changes or additions during development.

3. Lays the Foundation for Design and Development

A thorough analysis provides developers and designers with a clear direction, enabling them to build solutions that align with the specified requirements.

4. Supports Accurate Cost and Time Estimation

Clear requirements help project managers estimate the necessary resources, budget, and timeline more precisely.

5. Enhances Quality Assurance

Since the requirements serve as a benchmark for testing, the development team can verify that every feature meets the defined standards  resulting in a high-quality, user-approved product.

#Why is Requirement-Analysis Important?
1. Ensures a Clear Understanding of Stakeholder Needs
Through activities like interviews, workshops, and prototyping, requirement analysis helps teams gather and clarify stakeholder expectations. This prevents misunderstandings and ensures that the software solution aligns with actual user needs and business goals.
2. Provides a Strong Foundation for Design, Development, and Testing
By documenting and modeling requirements through tools such as use cases, user stories, and data flow diagrams, the project team establishes a clear blueprint for subsequent SDLC phases. This structured approach ensures that designers, developers, and testers all work from the same reference point, leading to consistency and quality in the final product.
3. Reduces Risks and Prevents Costly Rework
Requirement validation activities—like stakeholder reviews, feasibility analysis, and traceability—help detect errors, ambiguities, or missing requirements early in the process. Identifying and resolving these issues before development starts saves time, reduces project costs, and minimizes the risk of system failure or scope creep.

##Key Activities in Requirement Analysis.
1. Requirement Gathering 🗂️

This involves collecting information from stakeholders and existing systems to understand what is needed from the new software.

Interviews: Conduct interviews with stakeholders to gather detailed insights into their needs and expectations.

Surveys/Questionnaires: Use surveys to collect input from a larger audience efficiently.

Workshops: Organize workshops to discuss, clarify, and refine requirements collaboratively.

Observation: Observe end-users in their work environment to identify real-world challenges and opportunities.

Document Analysis: Review existing documentation and systems to understand current functionalities and identify improvement areas.

2. Requirement Elicitation ✍️

Elicitation focuses on drawing out precise, actionable requirements through collaborative and creative methods.

Brainstorming: Conduct sessions to generate innovative ideas and gather diverse perspectives.

Focus Groups: Engage select stakeholders in discussions to explore detailed requirements and expectations.

Prototyping: Build early prototypes or mockups to help stakeholders visualize proposed solutions and refine their requirements.

3. Requirement Documentation 📚

This step involves recording all gathered and elicited requirements in a structured format for reference throughout the project.

Requirement Specification Document: Create a comprehensive document listing all functional and non-functional requirements.

User Stories: Write user stories that describe features from the user’s point of view.

Use Cases: Develop use case diagrams to illustrate how users will interact with the system.

4. Requirement Analysis and Modeling 📊

This activity examines, prioritizes, and models requirements to ensure they are realistic and aligned with project constraints.

Requirement Prioritization: Rank requirements based on importance, feasibility, and business value.

Feasibility Analysis: Evaluate the practicality of requirements in terms of technology, cost, and time.

Modeling: Create visual models such as data flow diagrams (DFDs) or entity-relationship diagrams (ERDs) to represent requirements clearly.

5. Requirement Validation ✅

Validation ensures that the documented requirements accurately reflect stakeholder needs and are ready for implementation.

Review and Approval: Collaborate with stakeholders to review and confirm the accuracy and completeness of requirements.

Acceptance Criteria: Define measurable acceptance standards for each requirement to verify successful implementation.

Traceability: Develop a traceability matrix to ensure all requirements are tracked and addressed during design, development, and testing.

##Types of Requirements
1. Hotel Management Service (Hotel-owner portal)

Functional Requirements:

The system shall allow hotel managers/owners to create, edit, and delete hotel listing information (name, location, photos, room types, pricing).

The system shall support hotel managers to upload availability calendar, room inventory, and special offers.

The system shall push updated hotel data to the downstream services (e.g., to search index) when hotel info changes. 
Medium

The system shall provide a portal interface for hotel managers to log in and view listings, bookings, performance metrics.

Non-Functional Requirements:

The hotel management portal shall respond to updates (create/edit) within 2 seconds under typical load.

The system shall ensure that hotel update operations are eventually consistent across data replicas (master-slave DB). 
Medium

The system shall keep data secure: only authorized hotel managers can modify their own hotel listings (access control).

The system shall be scalable to support thousands of hotels, and database replication must maintain performance under high update load.

2. Customer Service (Search + Booking)

Functional Requirements:

The system shall allow customers to search for hotels by location, date range, number of guests, price, filters (amenities). 
Medium

The system shall allow customers to book a hotel (select room type, enter guest info, payment integration). 
Medium

The system shall integrate with a third-party payment service to process customer payment during booking. 
Medium

The system shall use caching (e.g., Redis) to accelerate booking/cart operations. 
Medium

Non-Functional Requirements:

The search API shall return results in under 500 ms for 95 % of requests (assuming caching and search index usage).

The booking service shall guarantee atomicity of the booking transaction (either full success or rollback) and consistency in the booking database.

The system shall tolerate high traffic – e.g., thousands of searches per second – by using load balancers and replication. 
Medium

The system shall log booking and payment events for auditing and analytics.

3. View Booking Service (for both customers & managers)

Functional Requirements:

The system shall allow a user (customer or manager) to view current and past bookings, with their statuses (confirmed, cancelled, etc.). 
Medium

The system shall fetch recent booking data from cache (Redis) and older data from archive storage (Cassandra). 
Medium

The system shall send notifications (e.g., via message queue) when a booking is made or changed, to the relevant customer or hotel manager. 
Medium

Non-Functional Requirements:

The booking-view interface shall load recent bookings in under 300 ms for users.

The archival storage system shall enable queries on bookings older than 1 year without causing performance degradation to recent-data queries.

The system shall provide data durability and availability (e.g., via Cassandra’s replication) to support high-volume booking history.

The system shall ensure timely delivery of notifications (< 5 seconds) after booking status changes.

## Use Case Diagrams

### What are Use Case Diagrams?
Use Case Diagrams are a type of **behavioral UML diagram** used during **requirement analysis** to identify and visualize the functional requirements of a system. They show how different users (actors) interact with the system and what operations (use cases) they can perform.

### Benefits of Use Case Diagrams
- **Clarify functional requirements:** They help stakeholders and developers understand what the system should do.
- **Identify actors and interactions:** Clearly defines roles like customers, admins, or external services.
- **Improve communication:** Serves as a visual tool for discussions between technical and non-technical team members.
- **Guide design and testing:** Provides a foundation for designing features and creating test cases.

---

### Booking System Use Case Diagram

The diagram below illustrates the interactions between different users and the booking system.

**Actors:**
- **Customer:** Books, views, or cancels a reservation.
- **Admin:** Manages bookings and user accounts.
- **Payment Service:** Processes payments.

**Use Cases:**
- Search for available rooms  
- Make a booking  
- Cancel booking  
- Make payment  
- Manage users  
- Manage bookings  

![Booking System Use Case Diagram](alx-booking-uc.png)
##Describe what Use Case Diagrams are and their benefits.
Diagram elements to include:

Actors:

Customer

Admin

Payment Service

Use Cases:

Search Rooms

Book Room

Cancel Booking

Make Payment

Manage Users

Manage Bookings

Relationships:

Customer → Search Rooms, Book Room, Cancel Booking, Make Payment

Admin → Manage Users, Manage Bookings

Book Room → includes → Make Payment

Payment Service → handles → Make Payment
![Booking System Use Case Diagram](alx-booking-uc.png)
## Acceptance Criteria

### Importance of Acceptance Criteria in Requirement Analysis

Acceptance Criteria are **specific conditions that a software feature must meet to be accepted by stakeholders**. They serve as a bridge between requirement analysis and testing by clearly defining what success looks like for each feature.  

**Key benefits of Acceptance Criteria:**
- ✅ **Clarifies expectations:** Ensures everyone (developers, testers, and clients) share the same understanding of feature goals.  
- ✅ **Guides development:** Provides developers with measurable targets to build toward.  
- ✅ **Supports validation and testing:** Helps QA teams create test cases that confirm a feature works as intended.  
- ✅ **Reduces ambiguity:** Minimizes misunderstandings or scope creep during implementation.  
- ✅ **Facilitates stakeholder approval:** Clearly outlines the conditions for project sign-off.  


### Example: Acceptance Criteria for the Checkout Feature

**Feature:** Checkout (Booking Management System)

**User Story:**  
_As a customer, I want to complete my booking and payment online so that I can confirm my stay quickly and securely._

**Acceptance Criteria:**
1. The system must allow the user to review selected property details and booking dates before payment.  
2. The total price, including taxes and service fees, must be displayed clearly.  
3. The user must be able to select a preferred payment method (credit/debit card, PayPal, etc.).  
4. The system must securely process payments and provide a confirmation message once payment is successful.  
5. The user must receive a booking confirmation email within one minute of successful payment.  
6. If payment fails, the system must display an error message and prompt the user to retry or use a different method.  
7. All data must be encrypted during the transaction process.  


### Summary

Acceptance Criteria ensure that features meet the **business objectives** and **user needs** established during requirement analysis. By setting measurable and testable conditions for success, teams can deliver high-quality software that satisfies stakeholders and enhances user trust.
