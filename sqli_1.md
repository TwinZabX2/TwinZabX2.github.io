
## SQL Injection (Search/GET) ##

Members
1. Mr.Wisanu  Sameejeang
2. Mr.Tossaporn Hansing
3. Mr.Sirimongkol wongfu


ทดสอบการ Search/Get

โดยการกด Seacrch ก่อนแล้วดูการแสดงผล

<br>![pic1](/pic/sqli_1_1.jpg)<br>

ทดสอบช่องโหว่
โดยการใส่ค่า  'union select 1,2,3,4,5,6,7 -- -
<br>![pic2](/pic/sqli_1_2.jpg)<br>

ทดสอบโดยการหา version databases โดยการใส่ค่า 'union select 1,2,3,4,version(),6,7 -- -
<br>![pic3](/pic/sqli_1_3.jpg)<br>

ทดสอบหาช่องโหว่ โดย RIPS
<br>![pic4](/pic/sqli_1_rips1.jpg)<br>
วิธีแก้ที่แนะนำโดย RIPS
<br>![pic5](/pic/sqli_1_rips2.jpg)<br>

แก้ไขโดยการ แก้ไขการรับค่า $_GET["title"] ให้มีการใช้ functions : mysql_real_escape_string
<br>ก่อนแก้<br>
 $title = $_GET["title"];
<br>หลังแก้<br>
 $title = mysql_real_escape_string($_GET["title"]);
 
 
<br>
if(isset($_GET["title"])) 
{   
    $title = mysql_real_escape_string($_GET["title"]);

    $sql = "SELECT * FROM movies WHERE title LIKE '%" . sqli($title) . "%'";

    $recordset = mysql_query($sql, $link);

 <br>ทดสอบด้วยเวป RIPS หลังแก้ไขเสร็จ<br>
 <br>![pic5](/pic/sqli_1_rips3.jpg)<br>
