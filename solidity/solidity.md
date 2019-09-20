# **Solidity**  
 * Cedits by (https://medium.com/@thanwa/solidity-blockchain-solidity-101-barcampsk-837d9f271a4a)
 * Cedits by (https://medium.com/20scoops-cnx/มารู้จักกับ-solidity-ขั้นพื้นฐานกัน-6f713b3fb64)
<br>
## **ความเป็นมา (History)**
solidity เป็นภาษาสำหรับการสร้าง Smart Contract เป็นภาษาที่ได้รับอิทธิพลมาจาก C ++, Python และ JavaScript 
ที่สำคัญเลยก็คือเป็นภาษาชนิดที่ statically typed และเป็นภาษาแบบ Object Oriented (OO) เพราะว่ามีคุณสมบัติของการสืบทอดและการทำ
 struct เป็นต้น
## **ชนิดของตัวแปร (Value Types)** 
  * **Booleans :** bool (true and false)
  * **Integers :** int/uint อันนี้เราสามารถกำหนดขนาดที่เราจะใช้ได้โดยมีขนาดตั้งแต่ 8-256 bits เช่น int8 และ uint16 และถ้าหากเราไม่ได้ได้ระบุขนาดของ bits ก็จะมีขนาด 256 โดยอัตโนมัติ เช่น int หรือ uint นั้นหมายความว่ามีค่าเท่ากับ int256 หรือ uint256
  * **Bytes :** bytes มีขนาดตั้งแต่ 1–32 bytes เช่น bytes8 หรือ bytes32แต่ถ้าเราไม่กำหนดขนาดก็จะเป็น array dynamic size
  * **Strings :** string อันนี้ไม่มีให้กำหนดขนาดของ bytes หมายความว่าจะมองเป็น array dynamic size ซึ่งมีความแตกต่างจากการใช้ bytes ที่มีการกำหนดขนาดตรงที่จำนวนของ gas ที่ใช้ strings จะใช้ gas มากว่านิคหน่อย
  * **Address :** address มีค่าอยู่ที่ 20 byte ตามขนาดของ Ethereum address
 
## **Smart contract คือ account ที่ถูกควบคุมโดย code
ซึ่งจะประกอบด้วย 3 ส่วนสำคัญคือ**
 *  **balance** คือ จำนวนของ ether ที่อยู่ใน account นี้
 *  **storage** คือ ข้อมูลที่อยู่ใน smart contract ซึ่งสามารถเก็บข้อมูลได้หลายชนิด เช่น uint, string, array เป็นต้น
 *  **code** คือ machine code สำหรับ account นี้ (ไม่สามารถอ่านแล้วเข้าใจได้โดยง่าย)

## **Solidity Programming Language**
 * เขียนอยู่ในรูปของไฟล์ .sol
 * คล้ายกับ JavaScript
 * แต่เป็นภาษาแบบ Strongly typed
 <br>
![](https://twinzabx2.github.io/solidity/solidity.bmp)
<br>
จากรูปแสดงให้เห็นว่าภาษา Solidity เมื่อถูก compile จะได้ output ออกมาเป็น 2 ส่วนซึ่งก็คือ byte code (ส่วนที่เป็น machine code ที่กล่าวถึงก่อนหน้านี้) และ ABI ซึ่งก็คือ interface สำหรับติดต่อกับ Ethereum blockchain ซึ่งใช้ในฝั่งของ client
<br>
![](https://twinzabx2.github.io/solidity/solidity_2.bmp)
<br>
จากโค้ดด้านบน เรามี contract ที่ชื่อว่า Inbox เก็บตัวแปรชื่อว่า message ซึ่งเป็นตัวแปรของ contract มีฟังก์ชัน 2 ฟังก์ชันคือ getMessage และ setMessage ซึ่งทั้ง 2 ฟังก์ชันนี้สามารถเรียกใช้จากภายนอก contract ได้ (เป็นฟังก์ชันแบบ public)
<br>
![](https://twinzabx2.github.io/solidity/solidity_3.bmp)
<br>
### นิยาม Function จะเป็นดังรูปตามตารางข้างล่างนี้
<br>
![](https://twinzabx2.github.io/solidity/solidity_4.bmp)
<br>
 * public สามารถเรียกใช้งานจากนอก contract ได้
 * private เฉพาะ contract เท่านั้นที่สามารถเรียกได้
 * view และ constant เรียกใช้งานแล้วไม่มีการแก้ไขตัวแปรใน contract
 * pure ไม่แก้ไขและไม่อ่านตัวแปรของ contract
 * payable ผู้เรียกสามารถส่งเงินเป็น ether ขณะเรียกฟังก์ชันนั้นๆ ได้
 <br>
![](https://twinzabx2.github.io/solidity/solidity_5.bmp)
<br>
<br>
![](https://twinzabx2.github.io/solidity/solidity_6.bmp)
<br>
 ในการ demo เราจะให้ Remix ซึ่งเป็น online editor ทำการ deploy ลงบน JavaScript VM ซึ่งอยู่ใน browser ซึ่งตัว Remix มีความสามารถในการ compile solidity file ให้เป็น byte code และ ABI อยู่แล้ว ซึ่งอำนวยความสะดวกให้นักพัฒนาได้เป็นอย่างดี<br><br>
เราจะสังเกตว่า smart contract เมื่อกี้ที่ deploy ไปแล้วจะมีฟังก์ชัน getMessage และ message ออกมา ซึ่งหากลิงคลิกดูแล้วปรากฎว่าให้ผลลัพธ์เดียวกันคือ return ค่าของ message ออกมา ซึ่งหมายความว่าตัวแปรใน contract ทุกตัวที่ประกาศออกมาเป็น public ตัว solidity จะทำการ auto generate ฟังก์ชัน get มาให้เราโดยอัตโนมัติ
<br>
<br>
![](https://twinzabx2.github.io/solidity/solidity_7.bmp)
<br>
การสร้าง smart contract จำเป็นต้องมี external account เป็นคนสร้าง (contract owner) ซึ่งไม่ต้องระบุฟิลด์ to โดย ethereum จะเข้าใจว่ามันคือการ deploy smart contract ใหม่ขึ้นไปบน ethereum blockchain
<br>
![](https://twinzabx2.github.io/solidity/solidity_8.bmp)
<br>
 เราสามารถที่จะ deploy ไปยังหลายๆ ethereum network ได้ ซึ่งแต่ละ network ก็จะแยกออกจากกันโดยเด็ดขาด smart contract ไม่สามารถคุยกันข้าม network ได้ แม้กระทั้งการ deploy ไปยัง network เดียวกัน ก็นับว่าเป็นคนละ instance กันสำหรับ contract นั้นๆ (ไม่มีความเกี่ยวข้องกัน)
 <br>
![](https://twinzabx2.github.io/solidity/solidity_9.bmp)
<br>
มื่อเราจะติดต่อกับ smart contract ที่อยู่บน ethereum blockchain หากมีการกระทำที่มีการแก้ไขค่าของตัวแปร จะมีค่าใช้จ่ายเกิดขึ้น เพราะจะมีกระบวนการ PoW ในการ verify ข้อมูลใหม่เกิดขึ้น และจะต้องรอ block time ประมาณ 10–15 วินาที (กรณีที่ใช้งานบน public network)
<br>
## **การเรียกใช้ฟังก์ชันนั้นมีอยู่สองแบบคือการ call ฟังก์ชันและการ send transaction**
 * **call function:** ใช้สำหรับขอข้อมูลโดยไม่มีการแก้ไขข้อมูลใน ethereum blockchain โดยการเรียกฟังก์ชันประเภทนี้จะไม่มีค่าใช้จ่าย
 * **send transaction:** ใช้เมื่อต้องการแก้ไขข้อมูลใน ethereum blockchain ซึ่งต้องสร้างเป็น transaction และส่งออกไปยัง miner โดยจะใช้เวลาในการ execute (รอ PoW) โดยฟังก์ชันประเภทนี้จะ return transaction hash กลับมา นี่เป็นเหตุผลว่าทำไมเราถึงไม่สามารถ set ค่าตัวแปรพร้อมกับสั่งให้ return ค่ากลับมาได้พร้อมๆ กัน และเมื่อมันเป็นการส่ง transaction มันย่อมจะมีค่าใช้จ่าย
 <br>
![](https://twinzabx2.github.io/solidity/solidity_10.bmp)
<br>
ในการเขียน smart contract หน่วยเงินที่เล็กที่สุดของโลก ethereun คือหน่วย wei (ผมออกเสียงว่าเวย์) โดยภาษานี้จะไม่มีเลขทศนิยม ซึ่งขนาดของตัวแปร uint ที่ใหญ่ที่สุดคือ 256 bit หรือ 32 bytes ซึ่งใหญ่มากเมื่อเทียบกับภาษาอื่นๆ
<br>
![](https://twinzabx2.github.io/solidity/solidity_11.bmp)
<br>
## **Gas price และ Gas limit คืออะไร?**
ในการส่ง transaction (deploy ก็ถือว่าเป็นการส่ง transction) จะมีค่าธรรมเนียมที่ต้องจ่าย หรือที่เราเรียกกันว่า gas
<br>
![](https://twinzabx2.github.io/solidity/solidity_12.bmp)
<br>
gasPrice คือราคา gas ต่อ 1 unit ซึ่งผู้ส่ง transaction จะเป็นคนจ่ายให้ miner เพื่อให้ miner ทำการ process transaction นั้นๆ โดยราคาของ gas จะแตกต่างกันออกไปตามช่วงเวลาซึ่งขึ้นอยู่กับความหนาแน่นของ ethereum network ในขณะนั้น สามารถตรวจสอบราคา gas ในปัจจุบันได้ที่ https://ethgasstation.info/
<br>
สำหรับ gasLimit คือ จำนวนของ gas ที่ลิมิตไว้ในการส่ง transaction เพื่อไม่ให้จำนวน gas ที่ใช้งานมีจำนวนสูงเกินไป ซึ่งอาจทำให้ผู้ส่ง transaction ต้องเสียเงินมากกว่าที่ควรจะเป็น
<br>
เราสามารถที่จะคำนวณและประมาณจำนวน gas ที่ใช้งานในการส่ง transaction ได้ โดยสามารถดูได้จากลิงก์ด้านล่างนี้
<br>
https://docs.google.com/spreadsheets/d/1n6mRqkBz3iWcOlRem_mO09GtSKEKrAsfO7Frgx18pNU/edit#gid=0
<br>
<br>
![](https://twinzabx2.github.io/solidity/solidity_14.bmp)
<br>
ยกตัวอย่างเช่น ฟังก์ชัน doMath มีการ บวก ลบ คูณ และเช็คว่าค่าทั้งสองมีค่าเท่ากันหรือไม่ หากดูจากตารางจะพบว่า operation ADD ใช้ 3 gas, SUBTRACT ใช้ 3 gas, MULTIPLY ใช้ 5 gas และ EQ ใช้ 3 gas รวมทั้งหมดเป็น 14 gas
<br>
![](https://twinzabx2.github.io/solidity/solidity_13.bmp)
<br>
เมื่อเราได้จำนวน gas ทั้งหมดที่ใช้งาน เราสามารถที่จะนำราคา gas ต่อ 1 unit คูณกับจำนวน gas ก็จะได้ราคา gas ที่ต้องจ่ายในการส่ง transaction นั้น (หากการเรียกฟังก์ชันมีการส่ง ether ด้วยจะต้องนำค่า gas มารวมด้วย) ซึ่งในการพัฒนา smart contract ต้องคำนึงถึงค่า gas ที่ user ต้องจ่ายด้วย ทั้งนี้เราสามารถใช้ web3 ในการ estimate ค่า gas ได้โดยไม่ต้องมาคำนวณเอง



