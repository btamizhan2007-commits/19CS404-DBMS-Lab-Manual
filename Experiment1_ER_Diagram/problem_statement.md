# ER Diagram Workshop – Submission Template

## NAME: TAMIZHAN B
## REF NO: 212225230283

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:


<img width="793" height="734" alt="Screenshot 2026-08-20 204737" src="https://github.com/user-attachments/assets/bf48bf21-8d3a-4c9a-90d4-16a2f3ed076f" />


### Entities and Attributes

<img width="902" height="425" alt="image" src="https://github.com/user-attachments/assets/21cc0725-8038-4ed2-94d8-901375c8f7b8" />

### Relationships and Constraints

<img width="887" height="345" alt="image" src="https://github.com/user-attachments/assets/4060104e-551b-4f00-b88f-892bb347098c" />

Assumptions
   •	All entity IDs are surrogate primary keys and are unique and system-generated.
   •	Every M:N relationship (Member–Program, Trainer–Program) is resolved with a dedicated junction table.
   •	Attendance is modelled as a Status attribute on Session (e.g., Attended, No-show, Cancelled) rather than a separate entity.
   •	A payment can relate to either a membership fee or a training session; PaymentType distinguishes the two.
   •	A member can have at most one active membership at a time.


---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
<img width="841" height="485" alt="image" src="https://github.com/user-attachments/assets/ff9c2d60-6c30-47d2-ade9-d5652f61269a" />

### Entities and Attributes

<img width="905" height="263" alt="image" src="https://github.com/user-attachments/assets/a5bc3e57-ca73-410c-b592-1e9cbad4ce42" />
<img width="913" height="263" alt="image" src="https://github.com/user-attachments/assets/ef0562f2-bb27-4879-9336-0e97ffcf7de8" />

### Relationships and Constraints

<img width="886" height="361" alt="image" src="https://github.com/user-attachments/assets/7823375d-23c6-4380-8a82-f4207ce3a1c1" />

### Assumptions

   •	Each physical book copy is uniquely identified by BookID; multiple copies of the same title are modelled as separate Book rows.
   •	A fine is generated only for a late return, so the Loan–Fine relationship is optional (0..1) on the Fine side.
   •	Room bookings for private/individual study are out of scope for this diagram; only event-related room usage (EventRoom) is modelled explicitly.
   •	All M:N relationships (Member–Event, Event–Speaker, Event–Room) are resolved using junction tables.
   •	All entity IDs are unique, system-generated primary keys.

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:

<img width="829" height="404" alt="image" src="https://github.com/user-attachments/assets/29a79a99-9a2d-4951-bfbf-7b77257c612e" />

### Entities and Attributes

<img width="904" height="357" alt="image" src="https://github.com/user-attachments/assets/eaa53ce8-1613-435e-bf49-d08d0d5a2888" />
<img width="912" height="142" alt="image" src="https://github.com/user-attachments/assets/74d77c09-6fc8-4e2c-aa26-a7226b88fbf6" />

### Relationships and Constraints

<img width="887" height="468" alt="image" src="https://github.com/user-attachments/assets/3ecf898e-a70f-4c9b-ba9f-43242221bb15" />

### Assumptions
     •	Walk-in customers are still recorded as a Customer row (with minimal details) so every reservation has a valid Customer_ID.
     •	Table availability is tracked via a Status attribute on Table (Available, Reserved, Occupied).
     •	The Order–Dish M:N relationship is resolved via Order Line, which also stores Quantity and Subtotal.
     •	A reservation may be served by more than one waiter (e.g., shift handover), modelled via the Reservation Waiter junction table.
     •	Billing (service charge, taxes) is calculated once per reservation, after all orders under it are placed.

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
