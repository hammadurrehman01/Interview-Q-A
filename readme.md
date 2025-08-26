1- MongoDB kis type ka database hay:

MongoDB ek document based database jay jo ke BSON format me jo ke JSON like format hay save krta hay. BSON ek binary-encoded JSON like data format hay jo ke JSON ko extend krta hay kuch additional data types k sath jese ke Date and BinData and ObjectId. MongoDB data ko internally JSON se BSON me convert krky store krta hay but humans k liay JSON hi read krwata hay.


2- ObjectId in MongoDB:

ObjectId mongodb me ek unique identifier hota hay jo 24 characters hexadecimal string me dikhaya jata hay.
ye 12 bytes kuch is taraha bante hayn:
4 bytes - Timestamp: Document banne ka time
5 bytes - random value: machine aur process id ensure krny k liay takay alag alag servers par bhi unique ho
3 bytes - Counter: Ek auto-increment counter hota hay jo har Objectid me badhta rehta hay


3- RDBMS kabuse kren or NOSQL kab use kren:

RDBMS suitable hota hay banking, finance, or e-commerce jesi application k liay kion kay ye ek structured database hay hay jisme ham data ko pre defined schema k sath store krty hayn
Dusri taraf NoSQL database large volumes of data k liay hota hay high speed k sath read and write kar sakta hay isy ham social media ya gaming jese platform k liay use kr skty hayn


MongoDB ko server se kese connect kren mongoose ko use kiay bina?

Uske liay hame mongodb ko server me install krna pryga by using npm i mongodb use baad MongoClient ka ek instance banaingy or uskey andar DB ka URL pass krdengy:
import { MongoClient } from "mongodb";
const client = new MongoClient(url)
phir ek async function banake us client ko connect krdengy connect method k zaliye "client.connect()" sath me ham try catch laga lenge takay error handling ho sky asaani se.





Query operator kia hotin hayn mongoDB me?

Query operators special keywords hotay hayn jo ke comparison, logical operations jese greater than less than jese operations krny me help krta hay.






MongoDB me projection kia hoti hay:

Projection ek tareeka hay query ko specify krny ka ke mujhe is table k documents me se kon kon si fields chahiyen. project method ko use krky ham field ko choose kr skty hayn k hame wo field chahiye ya nhi? jese k users.find().project({userId: 0}) userId nhi chahiye or agar chahiye tw { userId: 1}






Indexes kia hayn Mongodb me ya other RDBMS me?

index ek data structure hay jo query ko fast banane k liay use hota hay. jese book me hamary pas index page hota hay ussy ham desired page pe chaly jatay hayn index me page ka number dekh k har baar page palat palat k nhi dekhty. tw blkl aise hi agar ham kisi field me index banain tw mongodb us field k liay ek sorted data structure maintain krta hay. Isse query sidha us index ka use karke data dhoondh leti hai → super fast. createIndex method se ham indexing kr skty hayn kis bhi field par jese ki:
db.users.createIndex({ email: 1 })
db.users.find({ email: "hammad@example.com" })





Indexing k disadvantages:

har index alag se ek data strucuture ke form me store hota hay
update delete ya insert krty wqt srf particular data ko update krny k sath sath wo index ko bhi update krta hay






Mongoose kia hay kia advantage mongodb k andar iska?

mongoose ek data object modeling tool hay jo mongodb me data validation. middleware support or relationship between the collections define krny k kaaam ata hay. mongooose ko use krky ham data ko insert hone se phly uska schema define krskty hayn data types define krskty hayn or multiple collections ka apas me relation bata skty hayn. ham jab ek baar schema banalen phir us collection ka model banake ham us model ko use krskty hayn CRUD operations k liay







MySQL:

SQL me triggers kia hotay hayn or kitny types k hotay hayn:

SQL me Trigger ek special type ka stored procedure hota hai jo automatically execute hota hai jab kisi table pe koi specific event (jaise INSERT, UPDATE, DELETE) perform hota hai.






Triggers ka use kyun hota hai?

Data ko automatically validate karne ke liye
logs k liay




Triggers k types:

BEFORE Trigger
Insert, update ya delete hone se pehle chal jata hai.
Mostly validations ke liye use hota hai.
AFTER Trigger
Insert, update ya delete hone ke baad chal jata hai.
Logging, notifications, aur auditing ke liye useful hota hai.






Views kia hotay hayn sql me?

SQL me View ek virtual table hoti hai jo kisi SQL query ke result par based hoti hai. Yani view ka apna koi data nahi hota, balki wo ek stored SELECT query hoti hai jisko table ki tarah treat kiya ja sakta hai. Jab bhi aap view ko access karte ho, wo query run hoti hai aur data return karti hai.
Agar mujhe sirf IT department ke employees dikhane hain, to mai ek view bana sakta hun:
CREATE VIEW it_employees AS
SELECT id, name, salary
FROM employees
WHERE department = 'IT';
Ab jab bhi mai likhunga:
SELECT * FROM it_employees;
to mujhe sirf IT department ke employees ka data milega, jaise ek normal table se milta hai.






HAVING OR WHERE me difference?

WHERE Clause hamesha GROUP BY se pehle use hota hay jabke Having baad me. Where clause aggregate functions jese ke SUM() AVG() COUNT() ko nhi contain krta jabke HAVING krta hay.




DELETE, TRUNCATE and DELETE me difference?

DELETE 1 ya 1 se ziada rows ko delete krta hay based on where ki condition jabke Truncate pura table delete krdeta hay magar schema delete nhi krta DROP schema table dono delete krdeta hay. iske ilawa DELETE rollback hay TRUNCATE or DROP rollback nh hayn



JOINTS and types of JOINTS?

Joints SQL me 2 ya 2 se ziada table ko combine krny me madad deta hay.
LEFT JOIN: agar hamare pass do tables hayn A and B tw mtlb table A ka data ayega or B table ka sirf matching data ayega
RIGHT JOIN: agar hamare pass do tables hayn A and B tw mtlb table B ka data ayega or A table ka sirf matching data ayega
FULL OUTER JOIN: dono tables ka sara ka sara data ajaiyga
INNER JOIN: dono tables ka common data ajaiyega data ajaiyga