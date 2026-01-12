# Week 5: JavaScript Fundamental

ไฟล์นี้จะทำการอธิบาย การทำงานของโค้ดที่ทำกำหนด + แสดงผลลัพธ์ สำหรับทุกหัวข้อที่กำหนดทั้งหมด สามารถคลิกเปิดดูใน Github ได้เลย

---

# Explain: 01-variables.js - Challenge 6 (Create a Person Object)

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `01-variables.js` จะได้ผลลัพธ์ดังนี้:

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

### ผลลัพธ์

```
Full name: Alice Smith
Info: Alice Smith, Age: 20, GPA: 3.8
Courses: HTML, CSS, JavaScript
```

### อธิบายการทำงานของโค้ด

---

## สรุป

โค้ดนี้สาธิตการสร้าง **Object ใน JavaScript** ที่มีทั้ง property และ method เพื่อเก็บข้อมูลนักเรียนและสามารถเรียกใช้งานได้ เช่น การแสดงชื่อเต็ม, ข้อมูลสรุป และรายวิชา โดยใช้ `console.log` เพื่อแสดงผลลัพธ์ออกมาทีละขั้นตอน

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[01-variables.js - Challenge 6](./01-variables.js)

---

# Explain: 02-functions.js - Challenge 8: Returning Objects

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `02-functions.js` จะได้ผลลัพธ์ดังนี้:

```javascript
function createUser(firstName, lastName, age) {
  return {
    firstName,
    lastName,
    age,
    email: `${firstName.toLowerCase()}.${lastName.toLowerCase()}@example.com`,
    getFullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    getAge() {
      return this.age;
    },
  };
}

console.log("\nReturning Objects:");
const newUser = createUser("John", "Doe", 30);
console.log(newUser);
console.log("Email:", newUser.email);
console.log("Full name:", newUser.getFullName());
```

### ผลลัพธ์

```
Email: john.doe@example.com
Full name: John Doe

```

# Explain: 02-functions.js - Challenge 9: Function as Parameter (Callback)

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `02-functions.js` จะได้ผลลัพธ์ดังนี้:

```javascript
function processArray(arr, callback) {
  const result = [];
  for (const item of arr) {
    result.push(callback(item));
  }
  return result;
}

const numbers = [1, 2, 3, 4, 5];
const doubled = processArray(numbers, (x) => x * 2);
const squared = processArray(numbers, (x) => x * x);

console.log("\nCallback Function:");
console.log("Original:", numbers);
console.log("Doubled:", doubled);
console.log("Squared:", squared);
```

### ผลลัพธ์

```
Callback Function:
Original: [ 1, 2, 3, 4, 5 ]
Doubled: [ 2, 4, 6, 8, 10 ]
Squared: [ 1, 4, 9, 16, 25 ]

```
