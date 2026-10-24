# บันทึกการแก้โจทย์

ไฟล์นี้ต้องเขียนโดยนักศึกษาด้วยคำพูดของตนเอง

ใช้ template นี้เฉพาะกับโจทย์ OJ ที่ถูกระบุว่าต้องส่ง learning log เท่านั้น

ห้ามให้ AI เขียนไฟล์นี้แทนคุณ AI อาจช่วยตรวจ grammar, formatting หรือความชัดเจนได้ หลังจากที่คุณเขียนเนื้อหาของตนเองแล้ว

ถ้าใช้ AI กับโจทย์ learning-log-required นี้ ต้องทำไฟล์ `ai_reflection.md` ด้วย

---

## 1. ข้อมูล OJ

หมายเลข/ชื่อโจทย์ OJ:

```text
OJ3537 / Imposter
```

OJ submission ID ถ้ามีการส่งแล้ว:

```text
697233
```

สถานะ OJ:

```text
Pass
```

เวลาที่ใช้คิดและทำโจทย์ด้วยตนเอง:

```text
0-15 mins
```

เลือกหนึ่งข้อ:

```text
0-15 minutes
15-30 minutes
30-60 minutes
1-3 hours
3-6 hours
6-24 hours
1-3 days
4-7 days
1-4 weeks
More than 4 weeks
```

วิธีนับเวลา:

- นับเฉพาะเวลาที่ตั้งใจทำโจทย์นี้ด้วยตนเองจริง ๆ
- เริ่มนับตั้งแต่ตอนที่อ่านโจทย์ครั้งแรก
- ไม่นับเวลาพัก กินข้าว เรียน นอน เวลาที่ทำโจทย์อื่น หรือเวลาที่ไม่ได้ทำโจทย์นี้
- ถ้าใช้ AI ให้นับเฉพาะเวลาที่ทำด้วยตนเองก่อน prompt แรกที่ถาม AI
- ถ้าถามเพื่อน TA หรือผู้สอน ให้นับเฉพาะเวลาที่ทำด้วยตนเองก่อนขอความช่วยเหลือครั้งแรก
- ถ้าใช้ทั้ง AI และความช่วยเหลือจากคน ให้นับเฉพาะเวลาที่ทำด้วยตนเองก่อนขอความช่วยเหลือจากภายนอกครั้งแรก ไม่ว่าจะเป็น AI หรือคน
- ถ้าไม่ได้ใช้ AI และไม่ได้ขอความช่วยเหลือจากคน ให้นับเวลาถึงก่อนเขียน `submission.md`
- ประมาณเวลาได้ แต่ต้องซื่อสัตย์

---

## 2. ความเข้าใจโจทย์ของฉัน

เขียนโจทย์ด้วยคำพูดของตนเอง

ให้อธิบาย input, output และ constraints สำคัญด้วย

ถ้ายังไม่เข้าใจโจทย์ทั้งหมด ให้เขียนสิ่งที่เข้าใจในตอนนี้ ความเข้าใจอาจยังไม่ครบหรืออาจผิดได้ แต่ต้องพยายามอธิบายอย่างจริงใจ

```text
รับข้อมูลผู้เล่นกับบทบาทเข้ามาก่อน จนกว่าเจอคำว่า "Start"
จากนั้นรับรายชื่อคนที่ตายไปทีละคน จนกว่าจะเจอคำว่า "End"
- Input: เฟสแรกเป็นรายชื่อผู้เล่นกับ role มาในรูปคล้าย dict จบด้วย Start เฟสสองเป็นชื่อผู้เล่นที่ตาย จบด้วย End
- Output: แสดงจำนวน Impostor ที่ยังรอดชีวิตอยู่ จากนั้นแสดงรายชื่อคนที่ยังรอดชีวิต (***Alive***) เรียงตามชื่อภาษาอังกฤษ A-Z และแสดงรายชื่อคนที่ตายแล้ว (***Dead***) เรียงตามชื่อภาษาอังกฤษ A-Z เช่นกัน
```

---

## 3. แผนแรกของฉัน

เขียนแผนแรกก่อนรับความช่วยเหลือจาก AI เพื่อน TA ผู้สอน หรือก่อนสรุป code สุดท้าย

ถ้าใช้ AI ให้เขียนแผนที่มีอยู่ก่อน prompt แรกที่ถาม AI

ถ้าถามเพื่อน TA หรือผู้สอน ให้เขียนแผนที่มีอยู่ก่อนถาม

ถ้าไม่ได้ใช้ AI และไม่ได้ขอความช่วยเหลือจากคน ให้เขียนแผนที่มีอยู่ก่อนหรือระหว่างเริ่มเขียน code

แผนนี้เขียนแบบคร่าว ๆ ได้ อาจยังไม่สมบูรณ์หรืออาจต่างจากวิธีสุดท้าย

สามารถเขียนเป็น pseudocode, flowchart idea หรือขั้นตอนความคิดได้

```text
Step 1: สร้าง dictionary ชื่อ players ไว้เก็บคนที่ยังอยู่ และ dead ไว้เก็บคนที่ตาย
Step 2: วนลูปรับ input เฟสแรก คลีนข้อความโดยลบเครื่องหมาย { } " ' ออก แล้วแยกชื่อกับ role ด้วย : เก็บใส่ players หยุดรับเมื่อเจอ Start
Step 3: วนลูปรับ input เฟสสอง รับชื่อคนที่ตาย ถ้าชื่อนั้นอยู่ใน players ให้ย้ายออกจาก players ไปใส่ใน dead หยุดรับเมื่อเจอ End
Step 4: นับจำนวนคนที่มี role เป็น Impostor ใน players ที่เหลืออยู่
Step 5: พิมพ์จำนวน Impostor ที่เหลือตามฟอร์แมต
Step 6: เรียงชื่อคนใน players ตามอักษร A-Z แล้วพิมพ์ตามฟอร์แมต ***Alive***
Step 7: เรียงชื่อคนใน dead ตามอักษร A-Z แล้วพิมพ์ตามฟอร์แมต ***Dead***
```

---

## 4. วิธีสุดท้ายที่ใช้จริง

อธิบายสั้น ๆ ว่า algorithm หรือวิธีสุดท้ายที่ใช้จริงใน code ที่ส่งคืออะไร

หัวข้อนี้ต่างจาก Section 3:

- Section 3 คือแผนแรกก่อนใช้ AI ก่อนรับความช่วยเหลือจากคน หรือก่อนเขียน code สุดท้าย
- Section 4 คือวิธีสุดท้ายที่ใช้ใน solution จริง
- ถ้าวิธีสุดท้ายเหมือนกับแผนแรก ให้เขียนว่าเหมือนกัน และอธิบายสั้น ๆ ว่าทำไม

ห้ามคัดลอกคำอธิบายจาก AI

ห้ามคัดลอกคำอธิบายจากคนอื่น

```text
เหมือนกับแผนแรก เพราะใช้ dictionary ในการจัดการข้อมูล ย้ายชื่อระหว่าง alive กับ dead ได้สะดวกรวดเร็ว และใช้ฟังก์ชัน sorted() เพื่อจัดเรียงลำดับชื่อตัวอักษร A-Z ก่อนพิมพ์ผลลัพธ์
```

---

## 5. การทดสอบของฉัน

เขียน test cases อย่างน้อย 3 กรณีที่ลองเองหรือออกแบบเอง

พยายามเลือก test cases ที่แตกต่างกัน

แต่ละ test case ให้อธิบายว่าทำไมเลือกกรณีนั้น

ถ้า input หรือ output มีหลายบรรทัด ให้เขียนไว้ใน text blocks

### Test Case 1

ทำไมเลือก case นี้:

```text
ทดสอบกรณีทั่วไปที่มีทั้ง Crewmate และ Impostor หลายคน มีคนตายบางส่วน และทดสอบการจัดเรียงชื่อ A-Z ทั้งฝั่งคนเป็นและคนตาย
```

Input:

```text
{"Yellow": "Crewmate"}
{"Purple": "Impostor"}
{"Black": "Crewmate"}
{"Brown": "Impostor"}
Start
Yellow
End
```

Expected output:

```text
2 Impostor Remains
***Alive***
Black : Crewmate
Brown : Impostor
Purple : Impostor
***Dead***
Yellow : Crewmate
```

Actual output:

```text
2 Impostor Remains
***Alive***
Black : Crewmate
Brown : Impostor
Purple : Impostor
***Dead***
Yellow : Crewmate
```

Result:

```text
Pass
```

### Test Case 2

ทำไมเลือก case นี้:

```text
ทดสอบกรณี Impostor ตายทั้งหมดในเกม
```

Input:

```text
{"Red": "Impostor"}
{"Blue": "Crewmate"}
Start
Red
End
```

Expected output:

```text
0 Impostor Remains
***Alive***
Blue : Crewmate
***Dead***
Red : Impostor
```

Actual output:

```text
0 Impostor Remains
***Alive***
Blue : Crewmate
***Dead***
Red : Impostor
```

Result:
```text
Pass
```

### Test Case 3

ทำไมเลือก case นี้:

```text
ทดสอบกรณีไม่มีใครตายเลยในเกม
```

Input:

```text
{"Red": "Impostor"}
{"Blue": "Crewmate"}
Start
End
```

Expected output:

```text
1 Impostor Remains
***Alive***
Blue : Crewmate
Red : Impostor
***Dead***
```

Actual output:

```text
1 Impostor Remains
***Alive***
Blue : Crewmate
Red : Impostor
***Dead***
```

Result:

```text
Pass
```

---

## 6. การใช้ AI

ใช้ AI กับโจทย์นี้หรือไม่

```text
No
```

ถ้าใช้ AI ต้องทำไฟล์นี้ด้วย:

```text
ai_reflection.md
```

ถ้าถามเฉพาะเพื่อน TA หรือผู้สอน และไม่ได้ใช้ AI ไม่ต้องทำ `ai_reflection.md`

---

## 7. ความช่วยเหลือจากคน / การร่วมมือ

ได้ถามเพื่อน TA ผู้สอน หรือบุคคลอื่นเพื่อขอความช่วยเหลือในโจทย์นี้หรือไม่

```text
No
```

ถ้าใช่ ให้อธิบายสั้น ๆ ว่าได้รับความช่วยเหลือแบบใด

ตัวอย่างที่อนุญาต:

- อธิบายความหมายของโจทย์
- อธิบาย concept การเขียนโปรแกรม
- ให้ hint เกี่ยวกับแนวทาง
- คุยเรื่อง debugging
- คุยเรื่อง test cases
- ช่วยอธิบาย error message

สิ่งที่ไม่อนุญาต:

- คัดลอก code ของผู้อื่น
- ส่ง solution ของผู้อื่น
- ขอให้ผู้อื่นเขียน solution ให้
- ใช้ OJ submission ของผู้อื่น
- ขอให้ผู้อื่นส่ง OJ แทน

ใครช่วยคุณ

```text

```

เขาช่วยอะไร

```text

```

คุณยังทำอะไรด้วยตนเอง

```text

```

คุณคัดลอก code จากคนอื่นหรือไม่

```text
No
```

---

## 8. คำรับรองของนักศึกษา

เขียน `Yes` ในแต่ละ statement

| Statement | Yes/No |
|---|---|
| I wrote this submission in my own words. | Yes |
| I understand my final code. |Yes|
| I recorded the real OJ status. |Yes|
| I did not copy AI-generated text directly into this file. |Yes|
| I did not copy code from another person. |Yes|
| If I received human help, I disclosed it in this file. |Yes|
| I submitted the final code to the OJ by myself. |Yes|
