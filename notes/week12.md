## Basic of Functional Dependencies and Normalization for Relational Database

### Informal Design Guidelines for Relational Database
- relational database design -> grouping of attributes to form "good" relation schemas
- goals of the designs
  - **information preservation**: เก็บให้ข้อมูลมีความถูกต้องเสมอ
  - **minimum redundancy**:
- **normal forms**
  - 1NF (First)
  - 2NF (Second)
  - 3NF (Third)
  - BCNF (Boyce-Codd Normal Form)
- **1: Semantics**
  - each tuple in a relation should represent one entity or relationship instance
    - ให้แต่ละ row สามารถแสดงข้อมูลต่อหนึ่ง entity เท่านั้น
    - only ***foreign keys*** should used to refer to other entities
    - entity and relationship attributes should be kept apart as much as possible
      - ในช่วงการ mapping ระหว่าง ER -> Relational ให้สร้าง table ใหม่ทุกๆครั้งสำหรับแต่ละ Relationship
    - ***bottom line***: the semantics of attributes should be easy to interpret
- **2: Redundant Information in Tuples and Update Anomalies**
  - การเก็บข้อมูลที่ซ้ำซ้อน -> waste storage, cause problems with update anomalies
    - Insertion anomalies: ![](https://media.discordapp.net/attachments/1014398974649708624/1031399773728686180/unknown.png?width=1440&height=440)
    - Deletion anomalies: ![](https://media.discordapp.net/attachments/1014398974649708624/1031400493043437588/unknown.png?width=1440&height=504)
    - Modification(Update) anomalies: ![](https://media.discordapp.net/attachments/1014398974649708624/1031399443267846245/unknown.png?width=1440&height=437)
      - ทำให้เกิดการ propogate update to too many entity
  - design a schema that does not suffer from the insertion, deletion and update anomalies
  - ถ้าเกิดมี anomalies -> ให้ทาง application เป็นตัวจัดการแก้ปัญหาแทน
- **3: Null Values in Tuples**
  - relations should be designed -> ***have as few NULL values as possible***
  - ถ้า attributes ที่มี NULL บ่อย -> สร้าง relation ใหม่ที่มี pk ของตัวเอง
- **4: Generation of Spurious Tuples - avoid at any cost**
  - การที่ออกแบบไม่ดีจะทำให้เกิดปัญหาในการ JOIN ระหว่าง relation
  - **Result of Spurious Tuples**: ![](https://media.discordapp.net/attachments/1014398974649708624/1031403817826267206/unknown.png?width=932&height=685)
  - ***lossless join*** คือคุณสมบัติที่การันตีว่าจะเกิดผลลัพธ์ที่มีความหมายจากการทำ JOIN operation
  - relations should be **designed to satisfy the lossless join condition**
- **Spurious Tuples**
  - Non-additive or losslessness of the corresponding join
  - Preservation of the functional dependencies

### Functional Dependencies
- used to specify formal measures
- keys are used to define **normal forms** for relations
- are constraints that are derived from the meaning and interrelationships of the data attributes
- a set of attributes X ***funtionally determines** a set of attributes Y if **the value of X determines a unique value for Y**
  - ชุดของ attribute X ที่สามารถ determines ชุด attribute Y ว่า ค่าของ X สามารถบอกได้ว่า Y มีความ Unique
- notation: **X -> Y holds** (Y depends on X)
- examples:
  - SSN -> ENAME (Social Security Number determines Employee name)
  - PNUMBER -> {PNAME, PLOCATION}
- **If K is a key of R**
  - then ***K functionall determines _all_ attributes in R***
- **Definining FDs from instances**
  - การที่จะนิยาม FDs, จำเป็นต้อง **เข้าใจถึงความหมายของ attributes ที่เกี่ยวข้อง** และ **relationship** ระหว่างพวกมัน
  - FD ก็คือ คุณสมบัติของ attribute ที่อยู่ใน schema R
  - all we can conclude is that an FD **may exists** between certain attributes

### Normalization of Relations
- **Normalization**: คือกระบวนการ decomposing "bad" relation โดยการแยก attributes ของพวกมันให้กลายเป็น relations ที่ย่อยลงมา
- **Normal Form**: condition using keys and FDs of relation to ceritfy whether a relation schema is in a particular normal form
  - คุณสมบัติของการใช้ keys และ FDs ของ relation ในการตรวจสอบว่าโครงสร้างของ relation อยู่ในรูปแบบ normal ใดๆหรือป่าว
- **2NF, 3NF, BCNF**: based on keys and FDs of a relation schema
- **4NF**: based on keys, multi-valued dependencies: (MVDs)
- **5NF**: based on keys, join dependencies: (JDs)
- **Normalization**: จะเกิดขึ้นในการนำมาใช้เพื่อที่จะให้ ผลลัพธ์ของ designs มีคุณภาพสูงและ meet the desirable properties
  - practical utility of these normal forms becomes questionable when the constraints on which they are based on are ***hard to understand*** or ***to detect***
  - ไม่จำเป็นที่จะต้อง normalized ไปอยู่ในระดับที่สูงที่สุด (usually 3NF, BCNF)
- **Denormalization**: คือกระบวนการในการจัดเก็บการ join ของ higher normal form relations as a base relation
  - เป็นกระบวนการย้อนกลับของ Normalization ไว้ใช้สำหรับการ check คือ table เล็ก join กลับมาต้องเหมือนกัน table ใหญ่แบบเดิม
- **superkey** คือ set of attributes S subset-of R with the property that no two tuples in any legal relation state will have the same attribute(superkey)
- **key** is a superkey with the additional property that removal of any attribute from will cause K not to be a superkey anymore
- **prime attribute** must be a member of some candidate key
  - คือ attribute ใดๆก็ตามที่ประกอบแล้วเป็น candidate key
- **non-prime attribute** is not a member of any candidate keys

### First Normal Form
- **Disallow**
  - composite attributes
  - multivalued attributes
  - **nested relations** (table ซ้อน table)
- considered to be part of the definition of relation

### Second Normal Form
- uses the concepts of FDs, primary key
- Definitions:
  - **Prime attribute**: that is a member of the primary key K
  - **Full functional dependency**: คือ FDs ที่ไม่สามารถถอด attribute ไปได้อีกแล้ว
- Examples:
  - {SSN, PNUMBER} -> HOURS
  - {SSN, PNUMBER} -> ENAME (is not a full FD)(partial dependency)
- จะเป็น 2NF ได้เก็ต่อเมื่อ non-prime attribute A จะ fully dependent on the primary key
  - KEY ก็สามารถ determines attribute ทุกตัวได้

### Third Normal Form
- **Transitive functional dependency**
  - a FD X->Z that can be derived from two FDs X -> Y and Y -> Z
  - DMSGSSN is transitive FD Since SSN -> DNUMBES and DNUMBER -> DMSGSSN
  - ENAME is non transitive
- relation schema ใน 3NF จำเป็นต้องอยู่ใน 2NF และ no non-prime attribute A in R is transitively dependent on the primary key
  - primary key need to determines non primary attribute directly
![](https://media.discordapp.net/attachments/1014398974649708624/1031423045816025158/unknown.png)
- จาก 2NF (primary attribute fully determines all non primary attributes)
- แต่ SSN ไม่เข้าข่าย 3NF เพราะว่าไม่สามารถ determines Dmgr_ssn ได้จึงต้องมีการ decompose into two relations

### Progressive Normalization
![](https://media.discordapp.net/attachments/1014398974649708624/1031424080345313330/unknown.png?width=1440&height=673)
- Candidate Key ที่มีการ Transitive ไม่จำเป็นต้องแยกออกมา

### Normal Forms Defined Informally
- **1st normal form**
  - All attribute depend on **the key**
- **2nd normal form**
  - All attribute depend on **the whole key**
- **3rd normal form**
  - All attribute depend on **nothing but the key**

### Next week Quiz to p.45
