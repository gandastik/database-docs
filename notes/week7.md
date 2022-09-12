## ER Model

### Entity Relationship 3 main concepts
1. **Entities**
2. **Attributes**
3. **Relationship**

### Relationship and Relationship Types
- **relationship** relates two or more distinct entities with a specific meaning
- relationship of the same type are grouped or typed into a **relationship type**
- degree of a relationship type is the number of participating entity type
  - degree ของ relationship type คือจำนวนของ entity ที่มีส่วนเกี่ยวพันด้วย

### Example of **Binary** relationship
![Binary Relationship Types](https://media.discordapp.net/attachments/1014398974649708624/1018713806320435210/unknown.png)

### Recursive Relationship Type
- relationship between the same participating entity type in **distinct type**
- aka. **self-referencing** relationship type
- eg. SUPERVISION relationship between employee (in the role of supervisor) and another employee (in the role of supervisee)

![Recursive Relationship Type](https://media.discordapp.net/attachments/1014398974649708624/1018715952352866304/unknown.png)

### ER Diagram for the company
![ER Diagram](https://media.discordapp.net/attachments/1014398974649708624/1018717220500668446/unknown.png)
- **Rectangle** : Entity
  - Double Border : **Weak Entity** (depend on parent entity)
- **Diamond** : Relationship
  - Double Line : **Total Participation** (ทุก instance ใน entity จำเป็นต้องมี relationship นี้)
  - Single Line : **Partial Participation** (บาง instance เท่านั้นที่จะมี relationship)
- **Number** : บ่งบอกถึงลักษณะของความสัมพันธ์ว่าเป็น one-to-one, one-to-many, many-to-many

### Contraints on Relationship
- aka. ratio constriants
- **One-to-One (1:1)**
- **One-to-Many (1:N) or Many-to-One (M:1)**
- **Many-to-Many (M:N)**

### Weak Entity Types
- **does not have a key attribute**

### Notation for Contraints on Relationship
- **Cardinality Ratio** : 1:1, 1:N, N:1, M:N
- **Participation contraintst** total = double line, partial = single line

### (min, max) notation for relationship structural contraints
![](https://media.discordapp.net/attachments/1014398974649708624/1018723565182386176/unknown.png)

### UML Class Diagram
![UML class Diagram fro Company db](https://media.discordapp.net/attachments/1014398974649708624/1018725356217323530/unknown.png)

