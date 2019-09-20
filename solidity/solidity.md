# **Solidity**
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
 
