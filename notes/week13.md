## FD and Normalization (Cont.)

### General Normal Form (for multiple keys)
- consider the primary key only
- สนใจแต่กับ relation ที่มี **multiple candidate keys**
- **prime attribute** -> attribute ที่เป็นส่วนหนึ่งของ candidate key
- **non-prime attribute** -> attribute ที่ไม่ได้เป็นส่วนหนึ่งของ candidate key

### 2NF (General Definitions)
- 2NF คือ **every non-prime** attribute A in R is fully functionally dependent on **every key** of R

![](https://media.discordapp.net/attachments/1014398974649708624/1036471042601910312/unknown.png?width=1389&height=685)
- Tax_rate ถูก determine โดย Conty_name อย่างเดียว ซึ่งไม่ใช่ Key จึงไม่ได้อยู่ภายใต้นิยามของ 2NF -> ถูก decompose มาเป็น LOTS2 ซึ่งก็จะทำให้อยู่ภายใต้ 2NF

### 3NF (General Definitions)
- **Superkey** ของ relation schema "R" คือ เซตของ attribute "S" ของ "R" ที่ประกอบไปด้วย key ของ  "R"
- if whenever a FD X -> A
	- (a). X คือ superkey ของ R
	- (b). A เป็น prime attribute ของ R

![](https://media.discordapp.net/attachments/1014398974649708624/1036472414244184144/unknown.png?width=1440&height=627)
- จะเห็นได้ว่า Price ถูก determine โดย Area แต่ **Area ไม่ได้เป็น Superkey** ทำให้ไม่ได้เป็น 3NF
- จาก ข้อ a). จะสามารถตีความได้ว่า ถ้า **prime attribute functionally determines a non-prime attribute** จะไปถูก 2NF violations เนื่องจาก **non-full functional dependencies** 
- และ ถ้า **a non-prime attribute functionally determines a non-prime attribute** จะไปถูก 3NF violations จาก **a transitive dependency**
- หรือจะสามารถนิยาม 3NF ใหม่ได้ประมาณนี้
	- relation in schema R is in 3NF ถ้า every non-prime attribute ใน R อยู่ภายใต้เงื่อนไขพวกนี้
		- **It is fully functionally dependent on every key of R**
		- **It is non-transitively dependent on every key of R**

### BCNF (Boyce-Codd Normal Form)
- a relation schema R จะอยู่ในรูปของ BCNF ได้ก็ต่อเมื่อ **Nontrivial functional dependency
X->A holds in R, เมื่อ X is a superkey of R**
- **trivial dependency** คือ เซตของ attribute ที่เรียกว่า trivial ถ้า **เซตของ attribute นั้นเป็น subset ของ attribute นั้นด้วย**
	- **X->Y** is a trivial functional dependency **if Y is a subset of X**
- **nontrivial dependency** เกิดขึ้นเมื่อ **A->B holds true when B is not a subset of A**
- **สรุปได้ว่า**
	- Every 2NF realtion is in 1NF
	- Every 3NF realtion is in 2NF
	- Every BCNF realtion is in 3NF
- BCNF is considered a **Stronger form of 3NF**
- the goal is to have each realtion in BCNF (or 3NF)

![](https://media.discordapp.net/attachments/1014398974649708624/1036475726116945990/unknown.png?width=1440&height=586)
- Area ไม่ได้เป็น superkey ทำให้ violates BCNF

### Example

![](https://media.discordapp.net/attachments/1014398974649708624/1036477930794131497/unknown.png?width=1348&height=685)

![](https://media.discordapp.net/attachments/1014398974649708624/1036478083756212236/unknown.png?width=1340&height=685)

### Test for checking non-additivity of Binary Relation Decomposition
- F+ -> **Closure of F**
- **Binary Decomposition** คือ การแบ่ง relation จาก 1 ให้กลายเป็น 2 raltion
- **Propery NJB (non-additive join test for binary decomposition)** การทำ decomposition D = {R1, R2} of R มี **loseless join propery** (การ join แล้วไม่มีข้อมูลซ้ำ? เพิ่ม?)
	- f.d. (R1 intersect R2) -> (R1 - R2) อยู่ใน F+ or
	- f.d. (R1 intersect R2) -> (R2 - R1) อยู่ใน F+

![](https://media.discordapp.net/attachments/1014398974649708624/1036480444121751612/unknown.png?width=1312&height=685)

### Multivalued Dependencies and Fourth Normal Form

![](https://media.discordapp.net/attachments/1014398974649708624/1036482241917886544/unknown.png?width=1423&height=684)
- realtion EMP คือ **all-key relation** คือ attribute ทุกตัวเป็น key หมดเลย ทำให้ไม่มี f.d.'s เลย
- ทำให้เกิด redundancy ขึ้นมาใน relation จึงทำให้เกิด **Multivalued Dependency (MVD)** ขึ้นมา
- **MVD** คือ X ->-> Y ใน relation R เมื่อ X  และ Y คือ subset ของ R
![](https://media.discordapp.net/attachments/1014398974649708624/1036483386665091112/unknown.png)
- X ->-> Y อ่านว่า X **multidetermines** Y
- relation schema R จะอยู่ใน **4NF** ได้ สำหรับ **every nontrivial multivalued dependency 
 X ->-> Y in F+, X is a superkey for R**

![](https://media.discordapp.net/attachments/1014398974649708624/1036484758441570356/unknown.png?width=1440&height=646)
- Ename ->-> Pname, Ename ->-> Dname แต่มันไม่ได้อยู่ในนิยามของ 4NF ก็คือ Ename ไม่ได้เป็น superkey ของ R

### Join Dependencies and Fifth Normal Form
![](https://media.discordapp.net/attachments/1014398974649708624/1036487376282849341/unknown.png?width=1423&height=685) 
- เมื่อแตก R ออกแล้ว รวม R กลับมาต้องเป็นไม่มี Spurious Tuple จะต้องกลับมาได้เหมือนเดิม
- 5NF (or project-join normal form (PJNF)) for every nontrivial join dependency JD(R1, R2, ..., Rn) in F+, **every Ri is a superkey of R**

![](https://media.discordapp.net/attachments/1014398974649708624/1036489049986302042/unknown.png?width=1383&height=685)

![](https://media.discordapp.net/attachments/1014398974649708624/1036489437841993768/unknown.png)

