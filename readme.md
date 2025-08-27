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

4- MongoDB ko server se kese connect kren mongoose ko use kiay bina?

Uske liay hame mongodb ko server me install krna pryga by using npm i mongodb use baad MongoClient ka ek instance banaingy or uskey andar DB ka URL pass krdengy:
import { MongoClient } from "mongodb";
const client = new MongoClient(url)
phir ek async function banake us client ko connect krdengy connect method k zaliye "client.connect()" sath me ham try catch laga lenge takay error handling ho sky asaani se.

5- Query operator kia hotin hayn mongoDB me?

Query operators special keywords hotay hayn jo ke comparison, logical operations jese greater than less than jese operations krny me help krta hay.

6- MongoDB me projection kia hoti hay:

Projection ek tareeka hay query ko specify krny ka ke mujhe is table k documents me se kon kon si fields chahiyen. project method ko use krky ham field ko choose kr skty hayn k hame wo field chahiye ya nhi? jese k users.find().project({userId: 0}) userId nhi chahiye or agar chahiye tw { userId: 1}

7- Indexes kia hayn Mongodb me ya other RDBMS me?

index ek data structure hay jo query ko fast banane k liay use hota hay. jese book me hamary pas index page hota hay ussy ham desired page pe chaly jatay hayn index me page ka number dekh k har baar page palat palat k nhi dekhty. tw blkl aise hi agar ham kisi field me index banain tw mongodb us field k liay ek sorted data structure maintain krta hay. Isse query sidha us index ka use karke data dhoondh leti hai → super fast. createIndex method se ham indexing kr skty hayn kis bhi field par jese ki:
db.users.createIndex({ email: 1 })
db.users.find({ email: "hammad@example.com" })

8- Indexing k disadvantages:

har index alag se ek data strucuture ke form me store hota hay
update delete ya insert krty wqt srf particular data ko update krny k sath sath wo index ko bhi update krta hay

9- Mongoose kia hay kia advantage mongodb k andar iska?

mongoose ek data object modeling tool hay jo mongodb me data validation. middleware support or relationship between the collections define krny k kaaam ata hay. mongooose ko use krky ham data ko insert hone se phly uska schema define krskty hayn data types define krskty hayn or multiple collections ka apas me relation bata skty hayn. ham jab ek baar schema banalen phir us collection ka model banake ham us model ko use krskty hayn CRUD operations k liay

# ===============================================

===============================================
+++++++++++++++++ MYSQL +++++++++++++++++
===============================================
===============================================
===============================================

1- SQL me triggers kia hotay hayn or kitny types k hotay hayn:

SQL me Trigger ek special type ka stored procedure hota hai jo automatically execute hota hai jab kisi table pe koi specific event (jaise INSERT, UPDATE, DELETE) perform hota hai.

2- Triggers ka use kyun hota hai?

Data ko automatically validate karne ke liye
logs k liay

3- Triggers k types:

BEFORE Trigger
Insert, update ya delete hone se pehle chal jata hai.
Mostly validations ke liye use hota hai.
AFTER Trigger
Insert, update ya delete hone ke baad chal jata hai.
Logging, notifications, aur auditing ke liye useful hota hai.

4- Views kia hotay hayn sql me?

SQL me View ek virtual table hoti hai jo kisi SQL query ke result par based hoti hai. Yani view ka apna koi data nahi hota, balki wo ek stored SELECT query hoti hai jisko table ki tarah treat kiya ja sakta hai. Jab bhi aap view ko access karte ho, wo query run hoti hai aur data return karti hai.
Agar mujhe sirf IT department ke employees dikhane hain, to mai ek view bana sakta hun:
CREATE VIEW it_employees AS
SELECT id, name, salary
FROM employees
WHERE department = 'IT';
Ab jab bhi mai likhunga:
SELECT \* FROM it_employees;
to mujhe sirf IT department ke employees ka data milega, jaise ek normal table se milta hai.

5- HAVING OR WHERE me difference?

WHERE Clause hamesha GROUP BY se pehle use hota hay jabke Having baad me. Where clause aggregate functions jese ke SUM() AVG() COUNT() ko nhi contain krta jabke HAVING krta hay.

6- DELETE, TRUNCATE and DROP me difference?

DELETE 1 ya 1 se ziada rows ko delete krta hay based on where ki condition jabke Truncate pura table delete krdeta hay magar schema delete nhi krta DROP schema table dono delete krdeta hay. iske ilawa DELETE rollback hay TRUNCATE or DROP rollback nh hayn

7- JOINTS and types of JOINTS?

Joints SQL me 2 ya 2 se ziada table ko combine krny me madad deta hay.
LEFT JOIN: agar hamare pass do tables hayn A and B tw mtlb table A ka data ayega or B table ka sirf matching data ayega
RIGHT JOIN: agar hamare pass do tables hayn A and B tw mtlb table B ka data ayega or A table ka sirf matching data ayega
FULL OUTER JOIN: dono tables ka sara ka sara data ajaiyga
INNER JOIN: dono tables ka common data ajaiyega data ajaiyga

# ===============================================

===============================================
+++++++++++++++++ NODEJS +++++++++++++++++
===============================================
===============================================
===============================================

1- Event Driven architecture kia hota hay nodejs me?

Event-driven architecture ka matlab hai ke code events ke hone par react karta hai. Node.js me EventEmitter use hota hai. For example, jab user signup karta hai, ek event fire hota hai jisme email send karne aur logs save karne jese tasks handle hote hain.

2- Cron jobs?

CRON JOBS: Scheduled tasks hote hain jo fixed time pe chalne hote hain.
Example: Har raat 12 baje backup lena, ya Monday 9am par weekly email bhejna.

3- Queue jobs?

Queue JOBS: Queue jobs ka matlab hai asynchronous background tasks jo ek queue me daali jaati hain aur worker process unhe handle karta hai. ye time-based nahi hoti, balki event-based hoti hain. Jab koi kaam heavy ho (e.g. emails bhejna, PDF generate karna, image processing, SMS sending), to usay directly request ke andar run karna slow kar dega. Is liye hum usay queue me daal dete hain. Worker background me handle karta hai.

4- Streams in NODEJS?

Streams ka matlab hai data ko chhote-chhote parts (chunks) me process karna instead of pura data ek sath load karna.

5- Clusters in NODEJS?

Node.js single-threaded hota hai aur ek CPU core use karta hai. Cluster module hume multiple workers banane ki facility deta hai, jisse hum multiple cores ka faida utha sakte hain aur high traffic efficiently handle karte hain. Agar ek worker crash ho jaye to cluster usay restart bhi kar sakta hai.

6- Multer kia hay nodejs me?

Multer ek Node.js middleware hai jo multipart/form-data handle karta hai, aur file uploads ke liye use hota hai. Isme hum storage (disk ya memory), file size limit, aur type validation set kar sakte hain.

7- Express me form data ko kis tarah handle krengy?

Middleware k zariye express.urlencoded()

# ===============================================

===============================================
+++++++++++++++++ Stripe +++++++++++++++++
===============================================
===============================================
===============================================

1- Stripe kia hay or ye kese kaam krti hay backend py?

Stripe ek payment gateway hai jo online payments process karta hai. Backend pe ham Stripe ke SDK (stripe-node) use kar skty hayn
Process:
a. Frontend pe user card details enter karta hai → Stripe.js / PaymentElement se secure hota hai.
b. Backend pe tum Stripe API call kar ke PaymentIntent ya CheckoutSession create karte ho.
c. User ki payment Stripe ke servers pe securely process hoti hai.
d. Stripe tumhe webhook ke zariye status (success/failure) notify karta hai.

2- PaymentIntents kia hayn stripe me?

Stripe ne PaymentIntents API introduce kiya hai jo multiple steps handle karta hai, like 3D Secure authentication (OTP). ye ek object hay jo payment process ka lifecycle handle krta hay

3- PaymentIntent or CheckoutSessions me kia difference hay?

PaymentIntent → Custom payment flows banane ke liye use hota hai. Ham apna custom frontend bana sakte hayn (React, Next.js etc.) aur backend pe manually PaymentIntent confirm karte hayn.

Checkout Session → Stripe ka ready-made UI hai. Ham session create karte hayn aur user ko Stripe ke checkout page pe redirect kar dete hayn.

4- Stripe me webhooks kese kaam krty hayn?

Webhooks ka kaam hota hai Stripe se real-time events receive karna (like payment success/failure, refund issued, subscription canceled, etc.).

# =====================================================================================================

=====================================================================================================
++++++++++++++++++++++++++++++++++ WebSockets and Socket.io ++++++++++++++++++++++++++++++++++
=====================================================================================================
=====================================================================================================
=====================================================================================================

1- Websocket kia hay?

WebSockets ek protocol hai jo browser aur server ke darmiyan two-way (duplex) communication allow karta hai. HTTP ya HTTPS me client request krta hay or server response bhejta hay phir connection close hojaata hay lekin websocket me continuously connection barkarar rehta hay until ham usy band na kren.

2- Socket.io kia hay

Socket.IO ek library hai jo Node.js me WebSockets ke upar kaam karti hai. Ye automatically WebSocket + fallback mechanisms handle karti hai, matlab agar browser WebSocket support na kare to ye long polling ya aur methods use karti hai.
