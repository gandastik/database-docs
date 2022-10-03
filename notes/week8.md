## The Relational Data Model and Relational Database

### Concepts
- based on **Relation** (มีพื้นฐานมาจากความสัมพันธ์)
- **SQL** เป็นภาษาที่กำหนด Operation ต่อการ access / retreive ข้อมูลจาก DB
- relation -> มาจากไอเดียของ **sets**

### Definition (Informal)
- โดยรวมๆแล้วมีการมอง relation เหมือนกับ **table of values**
- relation คือจะประกอบไปด้วย **set of rows**
- ในแต่ละ แถว(rows) จะเป็นการ represent a real-world **entity** or **relationship**
- แต่ละ หลัก(column) แทนถึงข้อมูล และความหมายของข้อมูล -> **attribute**
![](https://media.discordapp.net/attachments/1014398974649708624/1021246248717668382/unknown.png)

- **Key of a Relation**
  - ในแต่ละ row จะมี value ของชุดข้อมูลที่มีความ **uniquely identifies** ในแถวๆนั้น เราจะเรียกว่า **Key**

### Definition (Formal)
- **Schema** (โครง) คำอธิบายของ Relation
  - Denoted by R(A1,A2,...An)
  - R คือชื่อของ relation
  - attributes จะอยู่ในรูป A1, A2, ..., An
- Example:
  - CUSTOMER(Cust-id, Cust-name, Address, Phone#)
    - CUSTOMER -> relation name
    - 4 attribues -> Cust-id, Cust-name, Address, Phone#
- **Tuple** คือ set of values ที่ ordered (ถ้าเกิดการสลับที่กัน = ความหมายเปลี่ยน)
  - <632985, "John Doe", "101 Main St.", "(404) 894-2000"> -> **4-tuple**
- **Domain** คือ set of atomic values
  - **Atomic** หมายความว่า ค่าที่อยู่ใน domain ที่ไม่สามารถแยกออกจากกันได้
  - มี data-type หรือ format ที่นิยามสำหรับ domain
    - USA_phone_numbers : (ddd)ddd-dddd
    - Dates: yyyy-mm-dd, dd mm, yyyy
  - แต่ละ attribute  names เป็นตัวกำหนดหน้าที่ที่จะปรากฎอยู่บน domain ใน relation
    - domain date -> สามารถใช้ได้หลากหลาย attribute และที่มีความหมายแตกต่างกันด้วย
      - "invoice-date", "payment-date"
- **State**: คือ subset ของ Cartesian product ของ domain ของ attribute ของ relation มันเอง
![Summary](https://media.discordapp.net/attachments/1014398974649708624/1021253440011243590/unknown.png)

### Characteristics of Relations
- Ordering of tuples in a relation r(R):
  - **tuple จะไม่มีการเรียงกันตามลำดับ** (row)
- Ordering of attributes in a relation schema R
  - จำเป็นต้องเรียงลำดับของ attribute
  - "self-describing": ทางเลือกของการนิยาม relation
    - t = { <name, "John">, <SSN, 123456> }

### Constraints
- **Inherent or Implicit Constraints** ห้ามมี multivalues
- **Schema-based or Explicit Constraints**
- **Application based or semantic constraints**

### Relation Integrity Constraints
- constraints คือ condition ที่จะต้องบังคับใช้กับ all valid relation states
- three main types of constraints
  - **Key**
  - **Entity integrity**
  - **Referential integrity**

### Key Constraints
- **Superkey**
  - คือ set ของ attribute "SK" of R
  - no two tuple in any valid relation state r(R) will have the same value of SK
- **Key**
  - "minimal" superkey
  - ***Key is a Superkey but not vice versa***
![Key Constraints Example](https://media.discordapp.net/attachments/1014398974649708624/1021266187734241320/unknown.png)
- ถ้า relation มี **candidate key** หลายตัว จะต้องมีตัวนึงที่ถูกเลือกให้เป็น **primary key**
  - ซึ่งจะถูก _underline_
- primary key -> **uniquely identiy**
  - provides the tuple identity
- ใช้ในการอ้างถึง tuple จากอีก tuple นึง
  - ***General rule*** : เลือก primary key ที่มีขนาดเล็กที่สุดจาก candidate keys แต่ก็ไม่เสมอไป!!

### Relations=al Database Schema
- คือ ชุดของ Relation (ตาราง) มารวมกัน

### Relation Database State
- **relational database state DB** คือ set ของ relation state ที่ r แต่ละตัวจะอยู่ในข้อบังคับ
  - โดยที่ข้อมูลของแต่ละ Relation จะต้อง valid

### Populated Databse state
- แต่ละ relation จะมีค่า tuple ที่อยู่ใน current relation state
- **relational database state** คือ union of all the individual relation states
  - INSERT, DELETE, UPDATE(MODIFY)

