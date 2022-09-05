## Data Modeling Using the Entity-Relationship (ER) Model

### Overview of Database Design Process
![Database Design Process](https://media.discordapp.net/attachments/287239433517006848/1016170332723355739/unknown.png?width=666&height=640)

- **Functional Requirement**
  - user defined **operation** (or **transactions**) including **retrieval** and **updates**
- **Data Requirement**
  - Detailed description
    - Entity Types
    - Relationshiop
    - Constraints

### ER Model
- **Entities**
- **Attributes**
- **Relationships**

### Entities and Attributes
- **Entitiy** is a basic concept for the ER model
  - eg. EMPLOYEE john Smith, the research DEPARTMENT, the ProductX PROJECT
- **Attributes** are properties used to descrbibe an entity
  - eg. EMPLOYEE entity may have the atributes NAME,

### Types of Attributes
- **Simple**: each entity has a single atomic value
- **Composite**: may be composed of serverla components
  - คุณสมบัติที่ประกอบไปด้วย components ย่อยๆ
  - eg. Address(Apt#, House#, City, State, Zipcode, ..), Name, Compositio
- **Multi-valued**: entity may have multiple values for that attribute
  - คุณสมบัติที่อาจจะมีค่ามากกว่าหนึ่งค่า
  - eg. Colors of a car, previous degrees
  - {Color} {PreviousDegrees}
- composite and mutli-valued attributes maybe nested
  - {PreviousDegrees(College, Year, Degree, Field)}
- **Stored vs. Derived Attributed**
  - Two or more attribute values are related
    - eg. **Birth_date** vs. **Age** -> **Age** attribute is derived from **Birth_date**
  - Some attribute values can be derived from related entities
    - eg. **Number_of_employees** of a DEPARTMENT -> count the number in the department
- **NULL value**
  - not applicable นำไปใช้ไม่ได้ ไม่มีค่า

### Entity Types
- Entities with the same basic attributes are grouped or typed into an entity type
### Entity Sets
- Each entity type will have a collection of entites stored in the database
  - Called the **entity set** or sometimes **entity collection**
- Entity set is **the current state of the entities of that type** that are stored in the database

### Key Attribute
- An attribute of an entity type for which **each entity must have a unique value**
- แต่ละ entity จะต้องมีเพื่อที่จะสามารถเอาไว้ id ได้ โดยจะต้องมีค่าทีเป็น unique กัน
  - eg. SSN, ISBN, UID etc.
- A key attribute may be composite
  - eg. VehicleTagNumber -> (Number,State)
- An entity type may have more than one key
- **Each key is _underline_** *note this is difference from the relational schema where only one "primary key" is underlined
- Example :
![Car Key Attribute Example](https://media.discordapp.net/attachments/287239433517006848/1016184597756780625/unknown.png?width=1159&height=640)
![Car Key Attribute Description](https://media.discordapp.net/attachments/1014398974649708624/1016184682716614817/unknown.png?width=1226&height=640)

### Notation for ER Diagram
![Summary of the notion for ER diagrams](https://media.discordapp.net/attachments/1014398974649708624/1016185812745986148/unknown.png?width=481&height=640)

### Initial Conceptual Design
- Requirements -> Diagram
- Define which attribute is multi-valued, key attribute
