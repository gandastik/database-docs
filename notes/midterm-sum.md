## Terminology
1. **Data**: known facts that can be recorded and have an implicit meaning
2. **Database**: a collection of **related** data
3. **Mini-world**: some part of the real world about which data stored in a database
4. **Database Management System (DBMS)**: a software package/system to faciliate the creation and maintenance of a database
5. **Database system**: DBMS software together with the data itself
6. **Meta-data**: The database definition (complete description of database) eg. storage format, datatype, constraints
7. **Data Model**: collection of concepts use to describe the structure of the database
8. **Entities**: represent real world object or concepts
9. **Attributes**: properties that describe entity
10. **Relationships**: association among 2 or more entities
11. **Database schema**: description of a database (โครงสร้าง พิมพ์เขียว หรือแปลนของ db)
12. **Schema Diagram**: displayed schema
13. **Schema Construct**: Each object within the schema
14. **Database State (instance, snapshot)**: the data in the database at a particular moment
15. **Data Independence**: ความสามารถที่สามารถที่จะเปลี่ยนแปลง schema ใน level นึงโดยไม่ส่งผลกระทบต่อ next higher level
  - **Logical Data Independence**: Conceptual schema <-> External schema
  - **Physical Data Independence**: Physical schema <-> Conceptual schema
16. **Centralized DBMS Architecture**: processing -> performed remotely on the computer system
  - display information sent to the termi1nal via networks
17. **Basic Client Server Architecture**: have specialized servers with specific functionalities
  - **Client** can access specific server by an appropriate interface
  - **Server** provide services to client machines
18. **Two-tier Client/Server Architecture**:
  - client: user interfaces, application programs
  - server: query & transaction functionality (query/transaction server)
  - **Open Database Connectivity (ODBC)**: provide API -> allow programs (client-side) to call DBMS
19. **Three-tier Client/Server Architecture**: common in web application
  - additional intermediate layer: Application server or Web server
    - stores rules used to access data
    - process the request
    - sends commands to database server
    - **conduits**
20. **Concurrency**: ความพร้อมๆกัน
21. **Atomicity**: properties that dbms must ensure that transaction must **executed completely** or **none at all**
22. **Composite Attributes**: can be divided into further parts
23. **Multivalued Attributes**: attribute that can have **set of values** of particular entity
24. **Derived Attributes**: attribute that can be derived from other attribute eg. age -> date_of_birth
25. **Stored Attributes**: from which the value of other attribute derived
26. **NULL values**: Not applicable, unknown
27. **Entity Type**: a collection of entity that have the same attributes
28. **Entity Set**: collection of entities of a particular entity type at a point in time
29. **Key Attribute**: the attribute that can use to **identify each entity uniquely**
30. **Weak Entity Types**: entity type that **do not have key attribute** of their own
  - id themself by relating to another entity
  - relationship between weak entity and the owner is called "identifying relationship"
  - double rectangle
31. **Degree of Relationship**: number of entity types that participate in that relationship
32. **Cardinality Ratio**: maximum number of relationship instances that an entity can participate in
  - 1:1, 1:N, N:1, M:N
33. **Participation Constraints**: specified whether existence of an entity depends on its being related to another entity
  - **Total Participation** -> double line  (all of that entity must participate in that relation)
  - **Partial Participation** -> single line (not all of that entity instance)
34. **Recursive Relationships**: same entity type participate more than onces in the relationship type in different roles

### Data Model
**Categories**
- **High-level or Conceptual Data Model**
  - แนวคิดที่ใกล้เคียงกับสิ่งที่ user มองเห็นข้อมูล
  - ตัวอย่างแนวคิดที่ใช้ -> entities, attributes, relationships
- **Low-level or Physical Data Model**
  - อธิบายถึงว่า **how data is stored** ในคอมพิวเตอร์
- **Representational (or Implementaion) Data Model**
  - represent data using **record structures**
-

### Alternative Notations for ER Diagrams
- (min, max)

Example
![](https://media.discordapp.net/attachments/1014398974649708624/1023625549115052163/unknown.png)
