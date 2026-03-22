# ใบงานการทดลองที่ 2: การวัดและประเมินผลด้วย Moodle..

---

## 🎯 วัตถุประสงค์เชิงพฤติกรรม

นักศึกษาสามารถ:

1. ✅ สร้างและจัดการ **Question Bank** พร้อม Categories ที่เป็นระบบ
2. ✅ สร้างข้อสอบประเภท **Multiple Choice, True/False, Short Answer, Essay, Matching, Numerical, Calculated, Drag-and-Drop** ได้
3. ✅ ตั้งค่า **Quiz** ให้มีความปลอดภัยและยืดหยุ่นตามบริบทการใช้งาน
4. ✅ กรอกคะแนนสำหรับ **Grade Items** ที่ไม่ได้ทำใน Moodle ได้
5. ✅ ตั้งค่า **Grading** แบบเดี่ยวและแบบกลุ่มได้
6. ✅ ตั้งค่า **Grade Categories** และสูตรรวมคะแนนเพื่อตัดเกรดได้
7. ✅ ออกรายงานผลการเรียนและส่งออกไฟล์เกรดได้

---

## 🎭 สถานการณ์จำลอง (Scenario)

**บทบาท:** ครูผู้สอน **วิชาเทคโนโลยีสารสนเทศ ม.1** ต้องการจัดการวัดผลทั้งภาคเรียนในระบบ Moodle (หรือนักศึกษาสามารถใช้รายวิชาของตนเอง แต่ต้องสร้างข้อสอบเองทั้งหมด)


**โครงสร้างคะแนนของรายวิชา (คะแนนเต็ม 100):**

```
รายวิชา: เทคโนโลยีสารสนเทศ ม.1 (ภาคเรียนที่ 1)
│
├── 🧪 คะแนนระหว่างเรียน (60 คะแนน)
│   ├── แบบทดสอบย่อย (Quiz) หน่วย 1-3        → 15 คะแนน
│   ├── ใบงาน/ชิ้นงาน (Assignment)           → 15 คะแนน
│   ├── โครงงานกลุ่ม (Group Project)          → 20 คะแนน
│   └── คะแนนพฤติกรรม/จิตพิสัย (Manual)      → 10 คะแนน
│
└── 📝 คะแนนปลายภาค (40 คะแนน)
    ├── สอบปลายภาค (Final Quiz)               → 30 คะแนน
    └── สอบปฏิบัติ (Practical Exam - Manual)  → 10 คะแนน
```

**เกณฑ์ตัดเกรด:**

| เกรด | คะแนน |
|------|-------|
| 4 (A) | 80-100 |
| 3.5 (B+) | 75-79 |
| 3 (B) | 70-74 |
| 2.5 (C+) | 65-69 |
| 2 (C) | 60-64 |
| 1.5 (D+) | 55-59 |
| 1 (D) | 50-54 |
| 0 (F) | 0-49 |

---

## 📚 ส่วนที่ 1: การสร้าง Question Bank 

### **1.1 ทำความรู้จัก Question Bank**

Question Bank คือ **คลังข้อสอบกลาง** ของรายวิชา สามารถนำข้อสอบมาใช้ซ้ำ และสุ่มข้อสอบเข้า Quiz ได้

```
โครงสร้างที่แนะนำสำหรับวิชา IT ม.1:

Question Bank
├── หน่วยที่ 1: ความรู้พื้นฐานคอมพิวเตอร์
│   ├── 1.1 ฮาร์ดแวร์ (20 ข้อ)
│   ├── 1.2 ซอฟต์แวร์ (20 ข้อ)
│   └── 1.3 ระบบปฏิบัติการ (15 ข้อ)
├── หน่วยที่ 2: อินเทอร์เน็ตและการสื่อสาร
│   ├── 2.1 เครือข่ายคอมพิวเตอร์ (20 ข้อ)
│   └── 2.2 การใช้อินเทอร์เน็ตอย่างปลอดภัย (20 ข้อ)
└── หน่วยที่ 3: การเขียนโปรแกรมเบื้องต้น
    ├── 3.1 Scratch (15 ข้อ)
    └── 3.2 Python เบื้องต้น (15 ข้อ)
```

### **1.2 การสร้าง Question Categories**

**ขั้นตอน:**

1. ไปที่รายวิชา → คลิกเมนู **"More"** (แถบเมนูรายวิชา)
2. เลือก **"Question bank"** → ตรงตำแหน่งเมนูเดิม **Questions** เลือกเปลี่ยนเป็น **"Categories"**
3. ที่หัวข้อ **"Add category"** กรอก:
   - **Parent category:** `Top for [ชื่อรายวิชา]`
   - **Name:** `หน่วยที่ 1: ความรู้พื้นฐานคอมพิวเตอร์`
   - **Category info:** คำอธิบายสั้น ๆ (ไม่บังคับ)
4. คลิก **"Add category"**
5. ทำซ้ำสำหรับ Sub-category โดยเลือก **Parent category** เป็นหน่วยที่ 1

> 💡 **เคล็ดลับ:** ตั้งชื่อ Category ให้มีตัวเลขนำหน้าเสมอ เช่น "01 ฮาร์ดแวร์" เพื่อให้เรียงลำดับถูกต้อง

---

## 📝 ส่วนที่ 2: การสร้างข้อสอบแต่ละประเภท

**วิธีเข้าถึง Question Bank:**
> รายวิชา → More → Question bank → Questions → คลิก **"Create a new question ..."**

---

### **2.1 Multiple Choice (ปรนัย – เลือกตอบ)**

**เหมาะกับ:** ทดสอบความรู้ความจำ ความเข้าใจ

**ขั้นตอนการสร้าง:**

1. เลือก **"Multiple choice"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
[General]
Category:      1.1 ฮาร์ดแวร์
Question name: HW-001 (ชื่อภายในสำหรับผู้สอน ไม่แสดงให้ผู้เรียน)
Question text: อุปกรณ์ใดต่อไปนี้เป็นหน่วยประมวลผลกลาง?
General feedback: CPU (Central Processing Unit) คือหน่วยประมวลผลกลาง ทำหน้าที่คำนวณและประมวลผลข้อมูล
One or multiple answers?: One answer only
   Shuffer the choices?: check เพื่อสุ่มลำดับตัวเลือก
[Answers]
Choice 1: CPU         → Grade: 100%    Feedback: ถูกต้อง CPU คือหน่วยประมวลผลกลาง
Choice 2: RAM         → Grade: None    Feedback: RAM คือหน่วยความจำชั่วคราว
Choice 3: HDD         → Grade: None    Feedback: HDD คือหน่วยเก็บข้อมูล
Choice 4: Monitor     → Grade: None    Feedback: Monitor คืออุปกรณ์แสดงผล

[Multiple tries] : กำหนดคะแนนที่หักถ้าตอบผิดในแต่ละครั้ง และให้คำไบ้ โดยจะใช้ร่วมกับ Quiz แบบ Interactive mode 

```

3. คลิก **"Save changes"**

---

### **2.2 True/False (ถูก/ผิด)**

**เหมาะกับ:** ทดสอบความเข้าใจแนวคิดพื้นฐาน

**ขั้นตอนการสร้าง:**

1. เลือก **"True/False"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
Question name: TF-001
Question text: CPU ย่อมาจาก Central Processing Unit

[Correct answer] True

[Feedback for True]:  ถูกต้อง! CPU ย่อมาจาก Central Processing Unit
[Feedback for False]: ไม่ถูกต้อง CPU ย่อมาจาก Central Processing Unit
```

3. คลิก **"Save changes"**

---


### **2.3 Short Answer (เติมคำ)**

**เหมาะกับ:** ทดสอบความจำคำศัพท์ คำย่อ ชื่อเฉพาะ

**ขั้นตอนการสร้าง:**

1. เลือก **"Short answer"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
Question name: SA-001
Question text: จงเขียนชื่อเต็มของอุปกรณ์ที่ย่อว่า RAM  โดยเขียนคำศัพท์ด้วยตัวพิมพ์ใหญ่หรือพิมพ์เล็ก

[Answers - ต้องกำหนดทุก Pattern ที่รับได้]
Answer 1: Random*Access*Memory      → Grade: 100%
Answer 2: random*access*memory      → Grade: 100%  (ตัวเล็กทั้งหมด)
Answer 3: RANDOM*ACCESS*MEMORY      → Grade: 100%  (ตัวใหญ่ทั้งหมด)

```

> ⚠️ **สำคัญ:** ตั้งค่า **"Case sensitivity"** → **"No, case is unimportant"** เพื่อไม่ให้ตัวพิมพ์ใหญ่-เล็กมีผล

> 💡 **เคล็ดลับ:** ใช้ **Wildcard (*)** ได้ เช่น `Random*access*Memory` จะรับ "Random Access Memory" หรือ "Random-Access Memory" ได้

---

### **2.4 Essay (อัตนัย)**

**เหมาะกับ:** ทดสอบการคิดวิเคราะห์ การอธิบาย

**ขั้นตอนการสร้าง:**

1. เลือก **"Essay"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
Question name: ES-001
Question text: จงอธิบายความแตกต่างระหว่าง RAM และ ROM พร้อมยกตัวอย่างการใช้งานของอุปกรณ์แต่ละชนิด (อย่างน้อย 5 ประโยค)

[Response format]  HTML editor (ช่วยให้พิมพ์ได้สะดวก)
[Response required]: Require the student to enter text
[Minimum word limit]: 50
[Maximum word limit]: 300

[Response template] (ใส่หัวข้อแนะนำให้นักเรียน)
ความหมายของ RAM:
ความหมายของ ROM:
ความแตกต่างหลัก:
ตัวอย่างการใช้งาน:

[Grader information] (คำแนะนำสำหรับครูที่ตรวจ)
ให้คะแนนตามเกณฑ์:
- อธิบาย RAM ได้ถูกต้อง 2 คะแนน
- อธิบาย ROM ได้ถูกต้อง 2 คะแนน
- ยกตัวอย่างได้ 1 คะแนน (คะแนนเต็ม 5)
```

3. คลิก **"Save changes"**

> ⚠️ **สำคัญ:** ข้อสอบ Essay ไม่มีการให้คะแนนอัตโนมัติ ครูต้องตรวจและกรอกคะแนนเองใน **Quiz > Attempts > Manual grading**

---

### **2.5 Matching (จับคู่)**

**เหมาะกับ:** ทดสอบความสัมพันธ์ระหว่างคู่ข้อมูล

**ขั้นตอนการสร้าง:**

1. เลือก **"Matching"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
Question name: MA-001
Question text: จับคู่อุปกรณ์คอมพิวเตอร์กับหน้าที่หลัก

[Question 1]: CPU      [Answer]: ประมวลผลข้อมูล
[Question 2]: RAM      [Answer]: เก็บข้อมูลชั่วคราว
[Question 3]: HDD      [Answer]: เก็บข้อมูลถาวร
[Question 4]: GPU      [Answer]: ประมวลผลกราฟิก

→ เพิ่ม Distractor (ตัวเลือกหลอก ไม่มีคู่):
[Question 5]: (ว่าง)   [Answer]: แสดงผลภาพ
[Question 6]: (ว่าง)   [Answer]: แหล่งจ่ายไฟ
```

> 💡 **เคล็ดลับ:** เพิ่ม Distractor อย่างน้อย 2 รายการเพื่อเพิ่มความยากและลดการเดา

---

### **2.6 Numerical (ตัวเลข)**

**เหมาะกับ:** คำนวณ วิทยาศาสตร์ คณิตศาสตร์

**ขั้นตอนการสร้าง:**

```
Question name: NUM-001
Question text: หน่วยความจำขนาด 1 GB มีค่าเท่ากับกี่ MB?

[Answer 1]: 1024    Error: ±0    Grade: 100%
[Answer 2]: 1000    Error: ±0    Grade: 50%   (คำตอบที่ยอมรับได้บางส่วน)
[Unit handling]:
    Unit handling: Units are not used at all. Only the numerical value is graded. ไม่ใช้หน่วย
```

---

### **2.7 Calculated (คำนวณจากตัวแปร)**

**เหมาะกับ:** โจทย์คณิตศาสตร์ที่เปลี่ยนตัวเลขได้ทุกครั้ง

**ขั้นตอนการสร้าง:**
1. กำหนดรายละเอียดข้อสอบ
```
Question name: CALC-001
Question text: ถ้าฮาร์ดดิสก์มีขนาด {size} GB และมีข้อมูลอยู่แล้ว {used} GB จะเหลือพื้นที่ว่างอีกกี่ GB?

[Answers]
   Formula: {size} - {used}
   Grade: 100%
   Tolerance: 0.01
   Type: Relative ยอมรับค่าความคลาดเคลื่อน + หรือ - จากค่าคำตอบ ใช้สูตร tolerance X ค่าคำตอบ แล้วนำไป + หรือ - จากคำตอบ
         Nominal  ยอมรับค่าความคลาดเคลื่อนแบบคงที่ เช่น + หรือ - 0.01 เสมอ ไม่ว่าคำตอบจะเป็นเท่าไร คำนำตอบ มา + หรือ - ด้วย 0.01


```
2. Save changes จะปรากฎหน้าต่าง สำหรับกำหนดค่า Wild card
3. กำหนดตัวเลือกค Wild card
 [Mandatory wild cards present in answers]
   Wild card {size}: will use the same existing private dataset as befor
   Wild card {used}: will use the same existing private dataset as befor
 [Synchronise the data from shared datasets with other questions in a quiz]: Do not synchonise
 4. กด Next page
 5. กำหนดค่า Wild card  
 [Item to add]
    Wild card {size}    ค่าตัวอย่าง: ??
    Range of Values:  Minimum [10.1] — Maximum [20.0]
    Decimal places:   [1]
    Distribution:     [Uniform ▾]

    Wild card {used}    ค่าตัวอย่าง: ??
    Range of Values:  Minimum [1.0] — Maximum [10.0]
    Decimal places:   [1]
→ กรณีโจทย์ข้อนี้ จะต้องแน่ใจว่า กำหนด size > used เพื่อไม่ให้มีค่าติดลบ
6. กด Update the datasets parameters เพื่อให้ค่าที่กำหนดใหม่มีผล
7. กดปุ่ม Get new 'Item to Add' now  เพื่อให้ระบบทำการสุ่มค่าตัวอย่างใหม่
8. Add item: กำหนด Add item: 10 เพื่อให้สร้างข้อมูลสุ่มมา 10 ข้อมูล แล้วทำการกดปุ่ม "Add"
9. กดปุ่ม "Save changes"
---

### **2.8 Drag and Drop onto Image (ลาก-วางบนภาพ)**

**เหมาะกับ:** ระบุตำแหน่งบนแผนผัง แผนที่ ไดอะแกรม

**ขั้นตอนการสร้าง:**

1. กำหนดรายละเอียดข้อสอบ
  Question name: DDI-001
  Question text: จากภาพเครื่องคอมพิวเตอร์ตั้งโต๊ะด้านล่าง ให้ลากชื่ออุปกรณ์ไปวางในตำแหน่งที่ถูกต้อง
3. อัพโหลดภาพพื้นหลัง (เช่น ภาพส่วนประกอบคอมพิวเตอร์)
4. กำหนด **Drop zones** (พื้นที่เป้าหมายบนภาพ):

```
[Background image]: computer_parts.jpg

[Draggable items]:
Item 1: 
    Type: Dragable text 
    Group: A 
    Text: CPU
Item 2: 
    Type: Dragable text 
    Group: A 
    Text: RAM       
Item 3: 
    Type: Dragable text 
    Group: A 
    Text: Hard Disk
Item 4: 
    Type: Dragable text 
    Group: A 
    Text: Power Supply

[Drop zones - ระบุพิกัด Left,Top บนภาพ]: (ระบุไปคร่าว ๆ ก่อน จะสามารถเลื่อนข้อความไปยังตำแหน่งที่แม่นยำได้หลังจากบันทึกข้อมูลแล้ว)
Zone 1: CPU          Left=180, Top=120   → Item 1
Zone 2: RAM          Left=270, Top=140   → Item 2
Zone 3: Hard Disk    Left=420, Top=272   → Item 3
Zone 4: Power Supply Left=120, Top=328   → Item 4
```
5. กด Save changes and continue edition 
6. กลับไปเลื่อนตำแหน่งข้อความให้ตรงกับรูปภาพ
7. กด Save changes
   
> ⚠️ **สำคัญ:** ต้องใช้ภาพที่มีพื้นที่ชัดเจนสำหรับแต่ละ Zone ขนาดแนะนำ 600x450 px

---

### **2.9 All-or-Nothing Multiple Choice (ปรนัยแบบได้คะแนนเต็มหรือศูนย์)**

**เหมาะกับ:** ทดสอบว่านักเรียน "รู้จริงครบถ้วน" ไม่ใช่แค่เดาถูกบางส่วน เช่น องค์ประกอบของระบบ, ลักษณะของสิ่งที่มีหลายคุณสมบัติ

> **ต่างจาก Multiple Choice ธรรมดา:** MC ปกติให้คะแนนบางส่วนได้ (Partial Credit) แต่ All-or-Nothing ต้องเลือกถูกครบทุกตัวจึงได้คะแนน ผิดแม้ตัวเดียว = 0 ทันที

**ขั้นตอนการสร้าง:**

1. Question Bank → Add → เลือก **"All-or-Nothing Multiple Choice"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
[General]
Category:      1.1 ฮาร์ดแวร์
Question name: HW-AON-001
Question text: ข้อใดต่อไปนี้เป็นส่วนประกอบของ CPU?
               (เลือกทุกข้อที่ถูกต้อง)
Default mark:  3
General Feedback:
    CPU ประกอบด้วย 3 ส่วนหลัก ได้แก่
    • ALU (Arithmetic Logic Unit) – คำนวณและเปรียบเทียบ
    • Control Unit – ควบคุมลำดับการทำงานของคำสั่ง
    • Registers – หน่วยความจำความเร็วสูงภายใน CPU
    ส่วน Hard Disk Cache และ RAM Slot ไม่ใช่ส่วนประกอบของ CPU

[Answers]
Choice 1: ALU (Arithmetic Logic Unit)  ✓ Correct
Choice 2: Control Unit                 ✓ Correct
Choice 3: Registers                    ✓ Correct
Choice 4: Hard Disk Cache              
Choice 5: RAM Slot                     

[Combined feedback]
  Options ✓ Show the number of correct responses → แสดงให้นักเรียนรู้ว่าต้องเลือกกี่ตัว


```

3. เปิด **"Shuffle the choices?"** → **Yes**
4. คลิก **"Save changes"**

> 💡 **เคล็ดลับ:** เปิด "Show number of correct choices" เสมอ เพราะถ้าไม่บอกนักเรียนจะไม่รู้ว่าต้องเลือกกี่ตัว


---

### **2.10 Drag and Drop into Text (ลากคำเติมในช่องว่าง)**

**เหมาะกับ:** ฝึกคำศัพท์เทคนิคในบริบทประโยคจริง, เติมคำสั่งโปรแกรม, เติมชื่ออุปกรณ์

> **ต่างจาก Select Missing Words:** ใช้การ**ลากวาง**แทน Dropdown เหมาะกับคอมพิวเตอร์มากกว่ามือถือ

**ขั้นตอนการสร้าง:**

1. Question Bank → Add → เลือก **"Drag and drop into text"** → คลิก **"Add"**
2. กรอกข้อมูล โดยใช้ `[[หมายเลข]]` ในตำแหน่งช่องว่าง:

```
[General]
Category:      01.1 ฮาร์ดแวร์
Question name: HW-DDT-001
Question text: อุปกรณ์คอมพิวเตอร์แต่ละชนิดมีหน้าที่แตกต่างกัน
               [[1]] ทำหน้าที่ประมวลผลและคำนวณข้อมูลทั้งหมด
               [[2]] ทำหน้าที่เก็บข้อมูลชั่วคราวขณะใช้งาน
               [[3]] ทำหน้าที่แสดงผลข้อมูลให้ผู้ใช้เห็น
               [[4]] ทำหน้าที่รับข้อมูลจากผู้ใช้เข้าสู่ระบบ
Default mark:  4
General Feedback:
• [[1]] CPU – Central Processing Unit ทำหน้าที่ประมวลผล
• [[2]] RAM – Random Access Memory เก็บข้อมูลชั่วคราว
• [[3]] Monitor – จอภาพแสดงผลข้อมูล
• [[4]] Keyboard – แป้นพิมพ์รับข้อมูลจากผู้ใช้
```

3. กำหนด **Choices** :

```
Item 1: CPU       Group: A   Infinite: No  ← คำตอบ [[1]]
Item 2: RAM       Group: A   Infinite: No  ← คำตอบ [[2]]
Item 3: Monitor   Group: A   Infinite: No  ← คำตอบ [[3]]
Item 4: Keyboard  Group: A   Infinite: No  ← คำตอบ [[4]]
Item 5: GPU       Group: A   Infinite: No  ← Distractor
Item 6: HDD       Group: A   Infinite: No  ← Distractor
```
> 💡 **Group:** ช่องที่ใช้ Group เดียวกันจะดึง Drag items จากชุดเดียวกัน ถ้าต้องการแยกกลุ่มคำให้ใช้ Group ต่างกัน  
> 💡 **Unlimited** = ใช้คำเดิมซ้ำในหลายช่องได้ เหมาะกับโจทย์ที่คำตอบซ้ำกัน

4. คลิก **"Save changes"**


---

### **2.11 Drag and Drop Markers (ลากหมุดปักบนภาพ)**

**เหมาะกับ:** ระบุตำแหน่งส่วนประกอบบนภาพจริง เช่น ชิ้นส่วนฮาร์ดแวร์, ตำแหน่งบนแผนผังเครือข่าย

> **ต่างจาก Drag and Drop onto Image:** ใช้ **Marker (ป้ายชื่อ)** ที่ลากไปปักบนจุด แทนการลาก Item ไปวางในกรอบ Drop zone

**ขั้นตอนการสร้าง:**

1. Question Bank → Add → เลือก **"Drag and drop markers"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
[General]
Category:      1.1 ฮาร์ดแวร์
Question name: HW-DDM-001
Question text: จากภาพ Motherboard ด้านล่าง
               ให้ลากชื่อส่วนประกอบไปปักในตำแหน่งที่ถูกต้อง
Default mark:  4
General Feedback:
• CPU Socket – ช่องเสียบ CPU อยู่กลางบอร์ด มีลักษณะเป็นช่องสี่เหลี่ยมขนาดใหญ่
• RAM Slot   – ช่องเสียบ RAM อยู่ข้างๆ CPU มักเป็นร่องยาวสีดำหรือสีต่างๆ
• PCIe Slot  – ช่องเสียบการ์ดจอ/การ์ดต่างๆ อยู่ส่วนล่างของบอร์ด
• SATA       – ขั้วต่อสายฮาร์ดดิสก์/SSD มีขนาดเล็กอยู่มุมบอร์ด

 คลิ๊กเลือก Highlight drop zones which have not had the correct marker dropped on them ให้เน้นสีตรงพื้นที่วาง (Drop Zones) ที่ยังไม่มีคำตอบที่ถูกต้องมาวาง
```

3. อัพโหลด **Background image** — ภาพ Motherboard ที่ไม่มี Label กำกับ ขนาดแนะนำ 600×400 px

4. กำหนด **Markers** (ป้ายชื่อที่ให้ลาก):

```
[Markers]

Shuffle drag items each time question is attempted
Marker 1: CPU Socket        Number: 1
Marker 2: RAM Slot          Number: 1
Marker 3: PCIe Slot         Number: 1
Marker 4: SATA Connector    Number: 1
```

5. กำหนด **Drop zones** โดยคลิกบนภาพเพื่อระบุตำแหน่ง:

```
[Drop zones]
Zone 1: ตำแหน่ง CPU Socket บนภาพ
        Shape: Circle   Marker: CPU Socket  Coordinates: (ตามค่า default)

Zone 2: ตำแหน่ง RAM Slot บนภาพ
        Shape: Circle   Marker: RAM Slot    Coordinates: (ตามค่า default)

Zone 3: ตำแหน่ง PCIe Slot บนภาพ
        Shape: Rectangle   Marker: PCIe Slot    Coordinates: (ตามค่า default)

Zone 4: ตำแหน่ง SATA Connector บนภาพ
        Shape: Circle   Marker: SATA Connector  Coordinates: (ตามค่า default)
```

6. คลิก **"Save changes and continue editing"**
7. กลับไปในส่วนของรูปภาพ จะมีตำแหน่ง Markers อยู่มุมบนซ้าย ให้คลิกเมาส์ตรงกลางแต่ละ Markers แล้ว Drag มาบริเวณคำตอบที่ถูกต้อง และทำการปรับขนาดให้ครอบคลุมพื้นที่ของบริเวณคำตอบ
8. ทดสอบ Preview เพื่อดูผลการทำงาน
9. คลิก **"Save changes"** 
> ⚠️ **สำคัญ:** ต้องใช้ภาพที่ **ไม่มี Label** กำกับส่วนประกอบ มิฉะนั้นเท่ากับเฉลยให้นักเรียนทันที  
> แนะนำทดสอบบนหน้าจอขนาดต่างกันก่อน เพราะตำแหน่ง Zone อาจเลื่อนบน Mobile
> 

---

### **2.12 Ordering (เรียงลำดับ)**

**เหมาะกับ:** ขั้นตอนการทำงาน, ลำดับเหตุการณ์, ลำดับจากน้อยไปมาก

**ขั้นตอนการสร้าง:**

1. Question Bank → Add → เลือก **"Ordering"** → คลิก **"Add"**
2. กรอกข้อมูล:

```
[General]
Category:      1.1 ฮาร์ดแวร์
Question name: HW-ORD-001
Question text: จงเรียงลำดับขั้นตอนการ Boot คอมพิวเตอร์ จากขั้นตอนแรกไปยังขั้นตอนสุดท้าย
Default mark:  3

General Feedback:
ลำดับการ Boot ที่ถูกต้อง:
1. Power ON → 2. POST → 3. BIOS/UEFI → 4. Bootloader → 5. OS Load → 6. Login
แต่ละขั้นตอนต้องสำเร็จก่อนจึงจะไปขั้นถัดไปได้

[Draggable Items - พิมพ์ตามลำดับที่ถูกต้อง Moodle จะสุ่มให้นักเรียนอัตโนมัติ]
Item 1: กดปุ่ม Power เปิดเครื่อง
Item 2: POST (Power-On Self Test) ตรวจสอบฮาร์ดแวร์
Item 3: BIOS/UEFI โหลดและค้นหา Boot Device
Item 4: Bootloader โหลด Operating System
Item 5: OS เริ่มต้นทำงานและแสดงหน้า Login
Item 6: ผู้ใช้ Login เข้าสู่ระบบ

Grading type:
  ○ Absolute position  → คิดสัดส่วนตำแหน่งที่ถูก ★ แนะนำ
  ● All or nothing  → ถูกครบทุกตำแหน่ง = ได้คะแนน ผิดแม้ตัวเดียว = 0


```

3. คลิก **"Save changes"**


---

### **2.13 Select Missing Words (เลือกคำเติมช่องว่างจาก Dropdown)**

**เหมาะกับ:** เติมคำศัพท์ในบริบทประโยค, เลือกคำสั่งโปรแกรม — เหมาะกับ Mobile มากกว่า Drag and Drop

> **ต่างจาก Drag and Drop into Text:** ใช้ **Dropdown เลือก** แทนการลากวาง ทำบนมือถือได้สะดวกกว่า

**ขั้นตอนการสร้าง:**

1. Question Bank → Add → เลือก **"Select missing words"** → คลิก **"Add"**
2. กรอกข้อมูล โดยใช้ `[[หมายเลข]]` ในตำแหน่งช่องว่าง:

```
[General]
Category:      02.1 เครือข่ายคอมพิวเตอร์
Question name: NET-SMW-001
Question text: อินเทอร์เน็ตทำงานโดยอาศัยระบบ [[1]] ในการแปลง
               ชื่อเว็บไซต์ เช่น www.google.com ให้เป็นหมายเลข [[2]]
               การส่งข้อมูลที่ปลอดภัยใช้โปรโตคอล [[3]]
               ซึ่งเข้ารหัสด้วย [[4]]
Default mark:  4
```

3. กำหนด **Choice Groups** ในส่วนด้านล่างของฟอร์ม:

```
ใส่ตัวเลือกที่ถูกต้องไว้เป็นตัวเลือกแรกของกลุ่ม

[Group A] – ใช้กับ [[1]]         [Group B] – ใช้กับ [[2]]
  ● DNS          ← ถูกต้อง         ● IP Address   ← ถูกต้อง
  ○ DHCP                            ○ MAC Address
  ○ FTP                             ○ URL
  ○ HTTP                            ○ Domain Name

[Group C] – ใช้กับ [[3]]         [Group D] – ใช้กับ [[4]]
  ● HTTPS        ← ถูกต้อง         ● SSL/TLS      ← ถูกต้อง
  ○ HTTP                            ○ WPA2
  ○ FTP                             ○ VPN
  ○ SMTP                            ○ Firewall
```

4. กรอก **General Feedback:**

```
[General Feedback]:
• [[1]] DNS – แปลง Domain name → IP Address
• [[2]] IP Address – หมายเลขที่ระบุตัวตนของเครื่องในเครือข่าย
• [[3]] HTTPS – โปรโตคอลเว็บที่มีการเข้ารหัส (S = Secure)
• [[4]] SSL/TLS – มาตรฐานการเข้ารหัสข้อมูลบนอินเทอร์เน็ต
```

5. คลิก **"Save changes"**

> 💡 **Group:** แต่ละ `[[หมายเลข]]` ผูกกับ Group หนึ่ง — ถ้าช่องสองช่องใช้ Group เดียวกัน Dropdown จะมีตัวเลือกชุดเดียวกัน ใช้ Group ต่างกันเมื่อต้องการตัวเลือกต่างกันในแต่ละช่อง
> 💡 **แนะนำ:** ถ้านักเรียนทำบนโทรศัพท์มือถือเป็นหลัก ให้เลือกใช้ **All-or-Nothing MC, Random SA Matching** และ **Select Missing Words** ที่ใช้การคลิกแทนการลากวาง

---




## 📥 ส่วนที่ 2: การ Import ข้อคำถามจากแหล่งภายนอก

> **เหมาะสำหรับ:** ครูที่มีข้อสอบสำเร็จรูปอยู่แล้วใน Excel, Word, หรือรับมาจากเพื่อนครู  
> **ประหยัดเวลา:** สร้างข้อสอบ 30 ข้อใน Excel ได้ภายใน 15 นาที แทนที่จะใช้ 1-2 ชั่วโมงในระบบ Moodle

---

### **ภาพรวม Format ที่ Moodle รองรับสำหรับ Import**

| Format | เหมาะกับ | ความยาก | รองรับประเภทข้อสอบ |
|--------|---------|---------|-------------------|
| **GIFT** | ครูทั่วไป | ⭐⭐ ง่าย | MC, T/F, Short Answer, Essay, Numerical, Matching |
| **Moodle XML** | ครูเทคนิค | ⭐⭐⭐ กลาง | ทุกประเภท รวม Drag & Drop, Calculated |
| **Aiken** | MC อย่างเดียว | ⭐ ง่ายที่สุด | Multiple Choice เท่านั้น |
| **CSV** | ผ่าน Plugin | ⭐⭐ ง่าย | ขึ้นกับ Plugin ที่ติดตั้ง |

> 💡 **แนะนำ: ใช้ GIFT สำหรับข้อสอบทั่วไป** และ **Moodle XML สำหรับข้อสอบที่ซับซ้อน**

---

### **ทำความเข้าใจไวยากรณ์ GIFT Format**

GIFT ใช้สัญลักษณ์พิเศษเพื่อระบุโครงสร้างข้อสอบ:

```
// นี่คือ Comment (Moodle จะข้าม)

$CATEGORY: ชื่อหมวดหมู่/Sub-category  ← กำหนด Category ก่อนกลุ่มข้อ

::ชื่อข้อสอบ::คำถาม {
    =คำตอบที่ถูก        ← = หมายถึง ถูกต้อง (Grade 100%)
    ~คำตอบผิด 1         ← ~ หมายถึง ผิด (Grade 0%)
    ~%50%คำตอบผิดบางส่วน ← %50% หมายถึง ได้ 50% ของคะแนน
    ####Feedback รวม    ← #### คือ General Feedback
}
```

**ตารางสัญลักษณ์ GIFT:**

| สัญลักษณ์ | ความหมาย | ตัวอย่าง |
|----------|---------|---------|
| `=` | คำตอบถูกต้อง | `=CPU` |
| `~` | คำตอบผิด | `~RAM` |
| `%n%` | คะแนนบางส่วน n% | `%50%คำตอบใกล้เคียง` |
| `####` | General Feedback | `####คำอธิบายเฉลย` |
| `#` | Feedback เฉพาะตัวเลือก | `=CPU#ถูกต้อง!` |
| `::` | ขอบเขตชื่อข้อสอบ | `::HW-001::` |
| `//` | Comment | `// หมายเหตุ` |
| `{TRUE}` | True/False = True | `{TRUE#fb_true~fb_false}` |
| `{#}` | Numerical | `{#1024:0}` |
| `->` | Matching pair | `=CPU -> ประมวลผล` |

---

### **ตัวอย่าง GIFT แต่ละประเภท (พร้อม Copy)**

**Multiple Choice (ปรนัย):**
```
$CATEGORY: หน่วยที่ 1/ฮาร์ดแวร์

::HW-MC-001::อุปกรณ์ใดเป็นหน่วยประมวลผลกลาง? {
    =CPU
    ~RAM
    ~HDD
    ~Monitor
    ####CPU = Central Processing Unit
}
```

**True/False (ถูก-ผิด):**
```
::HW-TF-001::RAM เป็นหน่วยความจำชั่วคราว {
    TRUE#ถูกต้อง! RAM สูญหายเมื่อปิดเครื่อง
    ~FALSE#ไม่ถูกต้อง RAM เป็นหน่วยความจำชั่วคราว
}
```

**Short Answer (เติมคำ – รับหลาย Pattern):**
```
::HW-SA-001::SSD ย่อมาจากอะไร? {
    =Solid State Drive
    =solid state drive
    =SOLID STATE DRIVE
    ####SSD = Solid State Drive
}
```

**Matching (จับคู่):**
```
::HW-MAT-001::จับคู่อุปกรณ์กับหน้าที่ {
    =CPU -> ประมวลผลข้อมูล
    =RAM -> เก็บข้อมูลชั่วคราว
    =HDD -> เก็บข้อมูลถาวร
    = -> แสดงผลภาพ
}
```
> ⚠️ บรรทัดสุดท้าย `= ->` คือ Distractor (ตัวหลอก ไม่มีคู่ซ้าย)

**Numerical (ตัวเลข):**
```
::HW-NUM-001::1 GB เท่ากับกี่ MB? {
    #1024:0
    ####1 GB = 1024 MB
}
// รูปแบบ: #คำตอบ:ค่าคลาดเคลื่อน
// เช่น #9.8:0.2 รับ 9.6 ถึง 10.0
```

**Essay (อัตนัย):**
```
::ES-001::จงอธิบายความแตกต่างระหว่างฮาร์ดแวร์และซอฟต์แวร์ {}
// ข้อ Essay ใช้ {} ว่างเปล่า ครูต้องตรวจเองใน Manual Grading
```

---

### **2.1 การ Import เข้า Moodle (Step-by-Step)**

**ขั้นตอน:**

1. รายวิชา → คลิก **"More"** → **"Question bank"** → **"Import"**

2. ตั้งค่า Import:

```
[File format]:          ★ GIFT format  (หรือ Moodle XML)
[General]:
  Import category:      ✓ From file  (ใช้ $CATEGORY จากไฟล์)
  Match grades:         Error if grade not listed
  Stop on error:        Yes  (หยุดถ้าพบ error)
```

3. อัพโหลดไฟล์:
   - คลิก **"Choose a file"** → อัพโหลด `.txt` (GIFT) หรือ `.xml` (Moodle XML)
   - ตรวจสอบ **Encoding: UTF-8** (สำคัญมากสำหรับภาษาไทย)

4. คลิก **"Import"**

5. ระบบแสดงรายการข้อสอบที่จะนำเข้า → ตรวจสอบ → คลิก **"Continue"**

6. ตรวจสอบผลใน **Question bank** → ควรเห็นข้อสอบใหม่ใน Category ที่กำหนด

> ⚠️ **ถ้าเห็น Error:** ตรวจสอบสัญลักษณ์ `{ } ~ = #` ในคำถาม  
> ถ้ามีสัญลักษณ์เหล่านี้ในคำถาม ต้อง Escape ด้วย `\` เช่น `\{` หรือ `\~`

---

### **การ Import จาก Moodle XML (ข้อสอบซับซ้อน)** 

**เหมาะกับ:** ข้อสอบที่มี HTML, ภาพประกอบ, Drag & Drop, Calculated

**ขั้นตอน Import เหมือน GIFT แต่เลือก Format:**
```
[File format]: Moodle XML format
[Import file]: questions_moodle_xml.xml
```

**ข้อดีของ Moodle XML:**
- รองรับ HTML ในคำถาม (ตัวหนา, ตาราง, สี)
- ฝังรูปภาพใน Base64 ได้
- รองรับ Tags, Hints, Penalties
- Export/Import ข้ามรายวิชาหรือข้าม Server

**วิธี Export XML จากรายวิชาอื่น (แบ่งปันข้อสอบ):**
1. รายวิชาต้นทาง → Question Bank → เลือกข้อสอบที่ต้องการ
2. คลิก **"With selected"** → **"Export"**
3. เลือก **Moodle XML format** → Download
4. นำไฟล์ไป Import ในรายวิชาปลายทาง


---

## 🧪 ส่วนที่ 3: การสร้างและตั้งค่า Quiz

### **3.1 การสร้าง Quiz**

**ขั้นตอน:**

1. รายวิชา → เปิด **Editing mode**
2. คลิก **"Add an activity or resource"** → เลือก **"Quiz"**
3. กรอกข้อมูลพื้นฐาน:

```
[General]
Name:         แบบทดสอบย่อยหน่วยที่ 1: ความรู้พื้นฐาน
Description:  ทดสอบความรู้ฮาร์ดแวร์และซอฟต์แวร์ จำนวน 20 ข้อ 20 คะแนน
              เวลา 30 นาที ทำได้ 1 ครั้ง

[Timing]
Open the quiz:    วันที่เปิดสอบ   เวลา 08:00
Close the quiz:   วันที่ปิดสอบ   เวลา 23:59
Time limit:       30 minutes
When time expires: Open attempts are submitted automatically → บังคับส่งเมื่อหมดเวลา

[Grade]
Grade category:  แบบทดสอบย่อย  (ต้องสร้าง Category ใน Gradebook ก่อน)
Grade to pass:   12  (60% ถือว่าผ่าน → แสดงสีเขียวในรายงาน)
Attempts allowed: 1 (ให้ทำข้อสอบได้ 1 ครั้ง)
Grading method:  Highest grade (ถ้าให้ทำได้หลายครั้ง)

[Layout]
New page:        Every 5 questions (แต่ละหน้าให้แสดงข้อสอบ 5 ข้อ)
Navigation method: Sequential (ไม่ให้ย้อนกลับ – เพิ่มความเป็นธรรม)

[Question behaviour]
Shuffle within questions: Yes
How questions behave:     Deferred feedback (เห็น feedback หลังส่ง)

[Review options]  ← ตั้งค่าว่านักเรียนจะเห็นอะไรบ้าง
During attempt:       ✗ (ไม่เห็นอะไรระหว่างทำ) เอาตัวเลือกที่สามารถเลือกได้ออกทั้งหมด
Immediately after:    ✓ The attempt / ✓ Marks / ✓ Specific feedback
Later, while the quiz is still open:    ✓ The attempt / ✓ Marks / ✗ Right answer
After the quiz closes: ✓ The attempt / ✓ Marks / ✓ Right answer / ✓ General feedback
```

> 💡 **แนะนำ:** ตั้ง **"After the quiz closes"** ให้เห็นเฉลยได้ทุกอย่าง เพื่อให้นักเรียนเรียนรู้หลังสอบ
4. คลิก **"Save changes"** 
---

### **3.2 การเพิ่มข้อสอบเข้า Quiz**

**วิธีที่ 1: เพิ่มจาก Question Bank โดยตรง**

1. ในหน้าแก้ไข Quiz คลิก **"Add question"**
2. คลิกที่ **Add** ที่อยู่มุมด้านขวาล่าง แล้วเลือก **"from question bank"**
3. กรองตาม Category → คลิก **Apply filters** เพื่อแสดงข้อสอบใน Category ที่เลือก
4. เลือกข้อสอบที่ต้องการ → คลิก **"Add selected questions"**

**วิธีที่ 2: สุ่มข้อสอบจาก Category (แนะนำสำหรับการสอบจริง)**

1. คลิก **"Add"** → **"a random question"**
2. เลือก Category: `1.1 ฮาร์ดแวร์`
3. กำหนด **Number of random questions:** `10`
4. ทำซ้ำสำหรับ `1.2 ซอฟต์แวร์` อีก `10` ข้อ
**หน้าแสดงข้อคำถาม จะแสดงให้เห็นว่าเป็นข้อสอบที่ได้จากการสุ่ม**


```
ผลลัพธ์: นักเรียนแต่ละคนได้ข้อสอบคนละชุด
→ ลดการลอกคำตอบ
→ ยุติธรรมมากขึ้น
→ ประหยัดเวลาสร้างข้อสอบหลายชุด
```

**การจัดลำดับและน้ำหนักคะแนน:**

```
ตัวอย่าง Quiz 20 คะแนน 20 ข้อ:
- ข้อ 1-15  Multiple Choice   (1 คะแนน/ข้อ)  = 15 คะแนน
- ข้อ 16-18 Matching          (1 คะแนน/ข้อ)  =  3 คะแนน
- ข้อ 19-20 Short Answer      (1 คะแนน/ข้อ)  =  2 คะแนน
                                     รวม      = 20 คะแนน

→ ปรับน้ำหนักที่ [Maximum mark] ของแต่ละข้อใน Edit quiz
```


---

## ✍️ ส่วนที่ 4: การกรอกคะแนนแบบเดี่ยวและแบบกลุ่ม

### **4.1 การกรอกคะแนนแบบเดี่ยว (Individual Grading)**
ทดสอบกรอกคะแนนรายบุคคลตามขั้นตอนดังนี้ โดยเลือกวิธีที่ 1 หรือวิธีที่ 2
**วิธีที่ 1: กรอกทีละคนใน Grader Report**
1. รายวิชา → **Grades** → ตรวจสอบว่าอยู่ใน **"Grader report"**
2. คลิก **ไอคอนดินสอ ✏️** ที่หัวข้อ Grade Item ที่ต้องการกรอก
3. ระบบเข้าสู่โหมด Edit → กรอกคะแนนในช่องของนักเรียนแต่ละคน
4. คลิก **"Save changes"**

**วิธีที่ 2: Single View (แนะนำสำหรับกรอกทีละ Grade Item)**
ทดสอบกรอกคะแนนรายบุคคลตามขั้นตอนดังนี้
1. Grades → dropdown → **"Single view"**
2. เลือก **"Grade item"** → เลือก `คะแนนพฤติกรรม`
3. ระบบแสดงรายชื่อนักเรียนทั้งหมดในคอลัมน์เดียว
4. กรอกคะแนนทีละคน → คลิก **"Save"**

```
✏️ Single View สะดวกกว่า Grader Report เมื่อต้องกรอก
   Grade Item เดียวสำหรับนักเรียนหลายคน
```

**วิธีที่ 3: นำเข้าจาก CSV (แนะนำเมื่อมีข้อมูลจาก Excel)** 
**ไม่ต้องทดลองส่วนนี้**
1. เตรียมไฟล์ CSV:

```csv
"username","คะแนนพฤติกรรม/จิตพิสัย"
"std001",8
"std002",9
"std003",7
"std004",10
"std005",6
```

2. Grades → dropdown → **"Import"** → **"CSV file"**
3. อัพโหลดไฟล์ → ตรวจสอบ Column mapping:
   - `username` → Map to: **User field: username**
   - `คะแนนพฤติกรรม/จิตพิสัย` → Map to: **Grade item: คะแนนพฤติกรรม**
4. Preview → คลิก **"Upload grades"**

---

### **4.2 การกรอกคะแนนแบบกลุ่ม (Group Grading)**

**สถานการณ์:** โครงงานกลุ่ม ทุกคนในกลุ่มได้คะแนนเท่ากัน

**วิธีที่ 1: ใช้ Assignment พร้อม Group submission**
ทดสอบกรอกคะแนนแบบกลุ่ม โดยเลือกวิธีที่ 1 หรือวิธีที่ 2

> *(สร้าง Assignment → ตั้ง Submission settings → "Students submit in groups: Yes")*

เมื่อตรวจ:
1. Assignment → คลิก **"View all submissions"**
2. กรอง **"Group"** → เลือกกลุ่มที่ต้องการตรวจ
3. ตรวจและให้คะแนน → เลือก **"Apply grades and feedback to entire group"** ✓
4. คลิก **"Save feedback"**

**วิธีที่ 2: กรอกใน Grader Report ทีละกลุ่ม**

1. Grades → Grader Report → คลิก **"Separate groups"** dropdown → เลือกกลุ่ม
2. ระบบกรองแสดงเฉพาะสมาชิกในกลุ่มนั้น
3. เปิด Edit mode → กรอกคะแนนเดียวกันให้ทุกคนในกลุ่ม
4. คลิก **"Save changes"**

---

## 🏆 ส่วนที่ 5: การรวมคะแนนและตัดเกรด
### **5.1 การตั้งค่า Grade Letters (เกณฑ์ตัดเกรด)**

1. Grades → dropdown → **"Grade letters"**
2. คลิก **"Edit grade letters"** → เปิดใช้ **"Override site defaults"**
3. กำหนดเกรดตามเกณฑ์สถานศึกษา:

```
Grade letter   Highest %   Lowest %
A              100.00       80.00
B+             79.99        75.00
B              74.99        70.00
C+             69.99        65.00
C              64.99        60.00
D+             59.99        55.00
D              54.99        50.00
F              49.99         0.00
```

4. คลิก **"Save changes"**

> ⚠️ **สำคัญ:** Grade Letters ใน Moodle คิดจาก **เปอร์เซ็นต์** (% ของ Maximum grade) ไม่ใช่คะแนนดิบ

### **5.2 การดู Grader Report และส่งออกเกรด**

**การดูภาพรวมคะแนนทั้งชั้น:**

1. Grades → **"Grader report"**
2. ระบบแสดงตารางคะแนนทุก Grade Item ของทุกคน
3. เลือก **Course grade settings** 
4. กำหนด [Grade item settings] Grade display type : Letter เพื่อแสดงเป็นเกรด หรือ Letter(real) เพื่อแสดง เกรด(คะแนน)
5. กด Save changes
6. กลับมาหน้า Grader report ทดสอบกรอกคะแนนนักเรียน 1 คน ให้ครบทุก Grade items 
7. กด Save changes
8. ปิด Edit mode เพื่อดูเกรดที่คอลัมน์ Course total ที่อยู่คอลัมน์สุดท้าย

**การส่งออกเกรด:**

1. Grades → **"Export"**
2.  [Export] Export as : Excel spreadsheet
3. เลือก Grade Items ที่ต้องการส่งออก
4. ตั้งค่า [Export format options]:
   - **Grade export display type:** Letter (เป็นตัวอักษร A-F) หรือ Real (คะแนนจริง)
   - **Grade export decimal points:** 2
5. คลิก **"Download"**

---

