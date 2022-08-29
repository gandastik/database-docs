## Database Concept and Architecture
> week 3 no class, week 4 I didn't attend
- **!! next week quiz !!**

### Data Models
- กลุ่มของ concept ที่ไว้อธิบาย **Structures(โครงสร้าง)** ของ db
- **operations** of manipulating these structures
- certains **constraints** that the database should obey
- provides a **framework** for data to be used within **information systems**
- **Constructs**
  - ***elements***
  - groups of elements (e.g. ***entity, record, table***)
  - ***relationship*** among such groups
- **Constraints** specify some restrictions on valid data and **must enforced at all times**
- **Operations**
  - ***Retrievals***
  - ***Updates***

### Categories of Data Models
- **Conceptual (high-level, semantic) data models** e.g. Relational model, Concept-oriented model, Object-Role model
- **Implementation (represational) data modelS**
  - aka. ***logical schema*** ("โครง")
  - logical schema and conceptual schema are sometimes implemented as one and the same
- **Physical (low-level, internal) data models**
  - provide a concept that describe details of how data is stored in the computer

### Schemas (คำอธิบายว่า db ประกอบด้วยอะไรบ้าง)
> reminder : database = collection of related data
- ***Database Schema*** is **the description of the database**
- A displayed schema is called a **schema diagram**

### Database State
- the actual data stored in a database at a **paritcular moment** in time
- also called **database instance** (or **occurrence** or **snapshot**)

### terminology
- ***Database state*** : refers to the content of a database at a moment in time
  - database state คือ ข้อมูลที่อยู่บน database ณ เวลาใดเวลานึง (ตราบใดที่ข้อมูลยังไม่เปลี่ยนก็ยังคงเป็น state เดิมอยู่)
- ***Initial Database State*** : the database state when it is initially loaded into the system
- ***Valid State*** : A state that satisfies the structure and constraints of the database
  - คือ state ที่อยู๋ภายใต้โครงสร้างและข้อกำหนดของ database
- the distincion between
   - database ***schema*** : changes very infrequently
   - database ***state*** : changes every tiem the database is updated
- **Schema** is also called **intension**
- **State** is also called **extension**

### The Three-Schema Architecture
![Three-Schema Architecture](https://cdn.discordapp.com/attachments/287239433517006848/1013647320073654292/unknown.png)
- **External Level**
  - A number of external schemas or user views
- **Conceptual Level** <- the topics that we are goning to learn
  - describe the structure of the whole database for a community of users
- **Interal Level**

### Data Independence
- **Logical Data Independence** : the capacity to change the conceptual schema without
  having to change the external schemas and their associated application programs
    - ความสามารถในการเปลี่ยนแปลง external level โดยที่ไม่ส่งผลกระทบต่อ conceptual level
- **Physical Data Independence** : the capacity to change the internal schema without having to change the conceptual schema
    - ความสามารถในการเปลี่ยนแปลง internal level โดยที่ไม่ส่งผลกระทบต่อ conceptual level

### User-Friendly DBMS Interfaces
- Menu-based
- Forms-based
- Graphics-based
- Natural Language
- and others e.g. speech, web browser with keyword search, parametic interfaces, interfaces for the DBA

### A Physical Centralized Architecture
![Physical Centralized architecture](https://cdn.discordapp.com/attachments/287239433517006848/1013650941720920064/unknown.png)

### Two-Tier Client-Server Model
![Client-Server](https://cdn.discordapp.com/attachments/287239433517006848/1013651609487687771/unknown.png)

### Three-Tier Client-Server
![Three-Tier](https://media.discordapp.net/attachments/287239433517006848/1013652659191939102/unknown.png)
![Three-Tier Architecture](https://media.discordapp.net/attachments/287239433517006848/1013652906777509950/unknown.png)
- common for web application
- can enhance security
  - database server only accessible via middle tier
  - client cannot directly access database server

### Classification of DBMSs
- Based on the data model used
  - Legacy
    - Network, Hiearchical
  - Currently Used
    - Relational, Object-oriented, Object-relation
  - Recent Technologies
    - NOSQL, Native XML DBMS
- Other classification
  - Single-user vs Mutli-user
  - Centralized vs Distributed
- examples of free relational DBMS: MySQL, PostgreSQL, others
