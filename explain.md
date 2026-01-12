# Week 5: JavaScript Fundamental

ไฟล์นี้จะทำการอธิบาย การทำงานของโค้ดที่ทำกำหนด + แสดงผลลัพธ์ สำหรับทุกหัวข้อที่กำหนดทั้งหมด สามารถคลิกเปิดดูใน Github ได้เลย

---

# Explain: 01-variables.js - Challenge 6 (Create a Person Object)

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `01-variables.js` ส่วน Challenge 6 จะได้ผลลัพธ์ดังนี้:

```javascript
console.log("\n=== Challenge: Person Object ===");
const student = {
  firstName: "Alice",
  lastName: "Smith",
  age: 20,
  gpa: 3.8,
  courses: ["HTML", "CSS", "JavaScript"],
  isActive: true,

  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
  getInfo: function () {
    return `${this.getFullName()}, Age: ${this.age}, GPA: ${this.gpa}`;
  },
};
console.log("Student object:");
console.log(student);
console.log("Full name:", student.getFullName());
console.log("Info:", student.getInfo());
console.log("Courses:", student.courses.join(", "));
```

---

### ผลลัพธ์ที่ได้จากรัน

```
{ firstName: 'Alice', lastName: 'Smith', age: 20, gpa: 3.8, ... }
Full name: Alice Smith
Info: Alice Smith, Age: 20, GPA: 3.8
Courses: HTML, CSS, JavaScript
```

### อธิบายการทำงานของโค้ด

1. **สร้าง Object `student`**

   - มี property เช่น `firstName`, `lastName`, `age`, `gpa`, `courses`, และ `isActive`
   - มี method (function ภายใน object) คือ:
     - `getFullName()` → คืนค่าเป็นชื่อเต็ม โดยใช้ `this.firstName` และ `this.lastName`
     - `getInfo()` → คืนค่าเป็นข้อความรวมชื่อเต็ม, อายุ และ GPA

2. **คำสั่ง `console.log("\n=== Challenge: Person Object ===");`**

   - แสดงหัวข้อเพื่อบอกว่ากำลังเข้าสู่ Challenge 6

3. **คำสั่ง `console.log("Student object:"); console.log(student);`**

   - แสดงข้อความ "Student object:"
   - ตามด้วยการพิมพ์ทั้ง object `student` ออกมา ทำให้เห็นทั้ง property และ method

4. **คำสั่ง `console.log("Full name:", student.getFullName());`**

   - เรียกใช้ method `getFullName()` → คืนค่า `"Alice Smith"`

5. **คำสั่ง `console.log("Info:", student.getInfo());`**

   - เรียกใช้ method `getInfo()` → คืนค่า `"Alice Smith, Age: 20, GPA: 3.8"`

6. **คำสั่ง `console.log("Courses:", student.courses.join(", "));`**
   - ใช้ `.join(", ")` รวม array `["HTML", "CSS", "JavaScript"]` เป็น string `"HTML, CSS, JavaScript"`

---

## สรุป

โค้ดนี้สาธิตการสร้าง **Object ใน JavaScript** ที่มีทั้ง property และ method เพื่อเก็บข้อมูลนักเรียนและสามารถเรียกใช้งานได้ เช่น การแสดงชื่อเต็ม, ข้อมูลสรุป และรายวิชา โดยใช้ `console.log` เพื่อแสดงผลลัพธ์ออกมาทีละขั้นตอน

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[01-variables.js - Challenge 6](./01-variables.js)
