## The Relational Data Model and Relational Database

### Entity Integrity
- **primary key attributes PK** ของแต่ละ Schema Relation **cannot have** ***null values***
  - pk จะใช้เป็นตัว identify individual tuples

### Referential Integrity
- a constraint involving **two** relations (ตัวเชื่อมระหว่างสอง table)
- ตัว **referencing relation** R1 มี **Foreign Key (FK)** ที่ reference ไปยัง PK ของ **referenced relation** R2
- ใช้ ลูกศร ในการอ้างอิง
- **Foreign Key** คือตัวที่ใช้ในการเชื่อมโยงระหว่าง 2 Relation เข้าด้วยกันโดยใช้ primary key ของอีก relation นึงมาเป็นตัว อ้างอิง

### Example of Referential Integrity Constraints for COMPANY DB
![](https://media.discordapp.net/attachments/1014398974649708624/1026339262041423963/unknown.png)

### Update Operations on Relations
- **Updates** may ***propagate*** จะไปส่งผลกระทบต่อ table อื่นที่นำตัวนั้นๆไป reference
- incase of integrity violation:
   - RESTRICT, REJECT
   - CASCADE (ตามไปแก้ตัวที่โยงมาทั้งหมด),  SET_NULL
   - user-specified

### Possible Violations for each operation
- **INSERT**
  - Domain constraints: ใส่ attribute เกินจากที่ระบุไว้ใน relation
  - Key constrainst: key attribute ซ้ำกับตัวอื่นใน tuple
  - Referential integrity: ถ้า fk ไม่มีอยู่ใน pk ของ referenced relation
  - Entity integrity: pk is null in the new tuple
- **DELETE**
  - ถ้า pk ถูกลบ -> RESTRICT, CASCADE, SET NULL
- **UPDATE**
  - domain constraint, **NOT NULL** constraints
  - updating the pk -> คล้ายๆกับกรณีของ DELETE
  - updating the fk ->
  - updaing an ordinary attribute

## Mapping ER to Relational

### GOALs
- preserve all information
- maintain the constraint
- minimize null values

![Mapping](https://media.discordapp.net/attachments/1014398974649708624/1026343460032233502/unknown.png?width=1440&height=574)

### Step 1: Mapping of Regular Entity Types
- symbols -> rectangle (strong entity)
- ให้สร้าง Relation (table) ขึ้นมาตามจำนวนของ entity
- นำ key attributes of E มาเป็น PK ของ R (ถ้ามี key attr. หลายตัว (candidate key) ให้เลือกมาตัวหนึ่งเพื่อเป็น primary key)

![](https://media.discordapp.net/attachments/1014398974649708624/1026344088703881246/unknown.png?width=1378&height=640)

### Step 2: Mapping of Weak Entity Types
- สำหรับ weak entity ให้สร้าง relation R
- สร้าง fk โดยใช้ pk จาก owner of the relation
- จะมี pk ของ ตัว weak R เป็น composite มาจาก (pk of owner, partial key)

![](https://media.discordapp.net/attachments/1014398974649708624/1026344984431046716/unknown.png?width=1189&height=640)

### Step 3: Mapping of Binary 1:1 Relation Types
- three approaches:
  1. **Foreign Key (2 relations) approach**: มี total ข้างหนึ่ง
    - เลือก relationship ที่มี total participation นำตัว partial key ของอีก relation มาแปะในข้างที่เป็น total
  2. **Merged relation (1 relation) opetion**: มี total สองข้าง
    - merging the two entity types and the relationship into a single relation. when both participations are total.
  3. **Cross-reference or relationship relation (3 relations) option**:
    - สร้าง relation (table) สำหรับของ relationship มาใช้ในการ cross-referencing

![](https://media.discordapp.net/attachments/1014398974649708624/1028664649547268117/unknown.png?width=1440&height=442)

### Step 4: Mapping of Binary 1:N Relationship Types
- ระบุให้แต่ละ relationship type R, ให้เป็น relation (table) S ที่ represent participating entity type at the **N-side**
- นำ foreign key ของ relation T ที่เป็น relation ของด้าน 1-side มาใส่เป็น attr. เพิ่ม

![](https://media.discordapp.net/attachments/1014398974649708624/1026347896922181692/unknown.png?width=1440&height=567)

### Step 5: Mapping of Binary M:N Relationship Types
- **create new relation S to represent R (relationship)**

### Step 6: Mapping of Multivalued attributes
- สำหรับแต่ละ multivalues A ให้สร้าง relation R เพิ่มขึ้นมา

### Step 7: Mapping of N-ary Relationship Types
- for each **n-ary relationship types** R, where n > 2 -> **create a new relationship S to represent R**

### A Correspondence between ER and Relational Model
![](https://media.discordapp.net/attachments/1014398974649708624/1028665228751294595/unknown.png)
