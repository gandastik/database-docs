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
