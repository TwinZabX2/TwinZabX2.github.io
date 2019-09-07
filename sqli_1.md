
## SQL Injection (Search/GET) ##

รายชื่อกลุ่ม 
1. Mr.Wisanu  Sameejeang
2. Mr.Tossaporn Hansing
3. Mr.Sirimongkol wongfu


ทดสอบการ Search/Get)

โดยการกด Seacrch ก่อนแล้วดูการแสดงผล

<br>![pic1](/pic/sqli_1_1.jpg)<br>

ทดสอบช่องโหว่
โดยการใส่ค่า  'union select 1,2,3,4,5,6,7 -- -
<br>![pic2](/pic/sqli_1_2.jpg)<br>

ทดสอบโดยการหา version databases โดยการใส่ค่า 'union select 1,2,3,4,version(),6,7 -- -
<br>![pic3](/pic/sqli_1_3.jpg)<br>

แก้ไขโดยการ แก้ไขการรับค่า mysql_real_escape_string
ก่อนแก้
 $title = $_GET["title"];
หลังแก้
 $title = mysql_real_escape_string($_GET["title"]);
 
 
 
if(isset($_GET["title"])) 
{   

    $title = mysql_real_escape_string($_GET["title"]);

    $sql = "SELECT * FROM movies WHERE title LIKE '%" . sqli($title) . "%'";

    $recordset = mysql_query($sql, $link);

    if(!$recordset)
    {

