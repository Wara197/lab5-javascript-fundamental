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

- สร้าง object student ที่มี property เช่น firstName, lastName, age, gpa, courses, isActive
- มี method getFullName() คืนชื่อเต็ม และ getInfo() คืนข้อมูลรวมชื่อ อายุ GPA
- ใช้ console.log(student) แสดงทั้ง object
- ใช้ student.courses.join(", ") รวม array เป็น string

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

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[02-functions.js - Challenge 8](./02-functions.js)

---

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

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[02-functions.js - Challenge 9](./02-functions.js)

---

# Explain: 03-control-flow.js - 5. Short-Circuit Evaluation

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `03-control-flow.js` จะได้ผลลัพธ์ดังนี้:

```javascript
console.log("\nShort-Circuit Evaluation:");
const user = { name: "John", age: 25 };
const admin = null;

const userName = admin?.name || user.name || "Anonymous";
console.log("User name:", userName);
const userProfile = user && user.profile;
console.log("User profile:", userProfile);
```

### ผลลัพธ์

```
Short-Circuit Evaluation:
User name: John
User profile: undefined
```

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[03-control-flow.js - Challenge 5](./03-control-flow.js)

---

# Explain: 03-control-flow.js - 7. Form Validation

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `03-control-flow.js` จะได้ผลลัพธ์ดังนี้:

```javascript
function validateRegistration(formData) {
  const errors = [];
  if (!formData.name || formData.name.trim() === "") {
    errors.push("Name is required");
  } else if (formData.name.length < 3) {
    errors.push("Name must be at least 3 characters");
  }
  if (!formData.email || formData.email.indexOf("@") === -1) {
    errors.push("Valid email is required");
  }
  if (!formData.age || formData.age < 18) {
    errors.push("Must be 18 or older");
  }
  if (!formData.password || formData.password.length < 6) {
    errors.push("Password must be at least 6 characters");
  }
  if (!formData.agreeToTerms) {
    errors.push("Must agree to terms");
  }
  return {
    isValid: errors.length === 0,
    errors: errors,
  };
}
console.log("\nForm Validation:");
const validUser = {
  name: "John Doe",
  email: "john@example.com",
  age: 25,
  password: "securepass123",
  agreeToTerms: true,
};
const invalidUser = {
  name: "Jo",
  email: "invalidemail",
  age: 15,
  password: "pass",
  agreeToTerms: false,
};
console.log("Valid user:", validateRegistration(validUser));
console.log("Invalid user:", validateRegistration(invalidUser));
```

### ผลลัพธ์

```
Form Validation:
Valid user: { isValid: true, errors: [] }
Invalid user: {
  isValid: false,
  errors: [
    'Name must be at least 3 characters',
    'Valid email is required',
    'Must be 18 or older',
    'Password must be at least 6 characters',
    'Must agree to terms'
  ]
}

```

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[03-control-flow.js - Challenge 7](./03-control-flow.js)

---

# Explain: 04-loops.js - 9. Chaining methods

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `04-loops.js` จะได้ผลลัพธ์ดังนี้:

```javascript
console.log("\nMethod chaining:");
const data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const evenStrings = data
  .filter((n) => n % 2 === 0)
  .map((n) => `${n}²=${n * n}`)
  .join(", ");
console.log("Even numbers squared:", evenStrings);
const numbers2 = [10, 20, 30, 40, 50];
const average = numbers2.reduce((sum, n) => sum + n, 0) / numbers2.length;
console.log("Average:", average);
```

### ผลลัพธ์

```
Method chaining:
Even numbers squared: 2²=4, 4²=16, 6²=36, 8²=64, 10²=100
Average: 30
```

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[04-loops.js - Challenge 9](./04-loops.js)

---

# Explain: 04-loops.js - 10. Challenge: Student Grades

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `04-loops.js` จะได้ผลลัพธ์ดังนี้:

```javascript
const students = [
  { name: "Alice", score: 95 },
  { name: "Bob", score: 75 },
  { name: "Charlie", score: 85 },
  { name: "Diana", score: 92 },
  { name: "Eve", score: 88 },
];
console.log("\nChallenge: Student Analysis");
console.log("Students:", students);
const names = students.map((s) => s.name);
console.log("Names:", names.join(", "));
const highScorers = students.filter((s) => s.score >= 85);
console.log(
  "High scorers:",
  highScorers.map((s) => `${s.name} (${s.score})`).join(", ")
);
const classAverage =
  students.reduce((sum, s) => sum + s.score, 0) / students.length;
console.log("Class average:", classAverage.toFixed(2));
const topScorer = students.reduce((top, s) => (s.score > top.score ? s : top));
console.log("Top scorer:", `${topScorer.name} (${topScorer.score})`);
const summary = students
  .map((s) => ({
    ...s,
    grade: s.score >= 90 ? "A" : s.score >= 80 ? "B" : "C",
  }))
  .sort((a, b) => b.score - a.score);
console.log("Summary (sorted):");
summary.forEach((s) => console.log(` ${s.name}: ${s.score} (${s.grade})`));
```

### ผลลัพธ์

```
Challenge: Student Analysis
Students: [ { name: 'Alice', score: 95 }, { name: 'Bob', score: 75 }, ... ]
Names: Alice, Bob, Charlie, Diana, Eve
High scorers: Alice (95), Charlie (85), Diana (92), Eve (88)
Class average: 87.00
Top scorer: Alice (95)
Summary (sorted):
Alice: 95 (A)
Diana: 92 (A)
Eve: 88 (B)
Charlie: 85 (B)
Bob: 75 (C)
```

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[04-loops.js - Challenge 10](./04-loops.js)

---

# Explain: 05-integration.js - Activity 5: Integration - Quiz Application

## ผลลัพธ์ที่ได้จากการรันโค้ด

เมื่อรันไฟล์ `05-integration.js` จะได้ผลลัพธ์ดังนี้:

```javascript
console.log("🎯🎯 === QUIZ APPLICATION === 🎯🎯\n");
const quizzes = [
  {
    question: "What is 5 + 3?",
    options: ["8", "7", "6", "9"],
    correctAnswer: 0,
  },
  {
    question: "What is the capital of Thailand?",
    options: ["Phuket", "Bangkok", "Chiang Mai", "Pattaya"],
    correctAnswer: 1,
  },
  {
    question: "What is the largest planet?",
    options: ["Mars", "Saturn", "Jupiter", "Neptune"],
    correctAnswer: 2,
  },
  {
    question: "What is 2^8?",
    options: ["128", "256", "64", "512"],
    correctAnswer: 1,
  },
  {
    question: "Which is NOT a JavaScript data type?",
    options: ["string", "class", "symbol", "boolean"],
    correctAnswer: 1,
  },
];
let results = [];
quizzes.forEach((quiz, index) => {
  const userAnswer = Math.floor(Math.random() * 4);
  const isCorrect = userAnswer === quiz.correctAnswer;
  results.push({
    questionNum: index + 1,
    question: quiz.question,
    userAnswer: quiz.options[userAnswer],
    correctAnswer: quiz.options[quiz.correctAnswer],
    isCorrect: isCorrect,
  });
});
console.log("QUIZ RESULTS:");
console.log("─".repeat(60));
results.forEach((result) => {
  const status = result.isCorrect ? "CORRECT" : " WRONG";
  console.log(`Q${result.questionNum}: ${result.question}`);
  console.log(` Your answer: ${result.userAnswer}`);
  if (!result.isCorrect) {
    console.log(` Correct answer: ${result.correctAnswer}`);
  }
  console.log(` ${status}`);
  console.log();
});
const correctCount = results.filter((r) => r.isCorrect).length;
const score = (correctCount / results.length) * 100;
console.log("─".repeat(60));
console.log(
  `FINAL SCORE: ${correctCount}/${results.length} (${score.toFixed(1)}%)`
);
let grade;
if (score >= 90) {
  grade = "A";
} else if (score >= 80) {
  grade = "B";
} else if (score >= 70) {
  grade = "C";
} else if (score >= 60) {
  grade = "D";
} else {
  grade = "F";
}
console.log(`GRADE: ${grade}`);
console.log("\nFEEDBACK:");
if (score === 100) {
  console.log("🌟🌟 Perfect score! Excellent work!");
} else if (score >= 80) {
  console.log("👍👍 Great job! Keep practicing.");
} else if (score >= 60) {
  console.log("📚📚 Good effort. Review the material and try again.");
} else {
  console.log("💪💪 Keep practicing. You'll improve!");
}
console.log("\n📊📊 STATISTICS:");
console.log(`Total questions: ${results.length}`);
console.log(`Correct: ${correctCount}`);
console.log(`Incorrect: ${results.length - correctCount}`);
console.log(`Success rate: ${score.toFixed(1)}%`);
const byCorrectness = results.reduce(
  (acc, r) => {
    acc[r.isCorrect ? "correct" : "incorrect"]++;
    return acc;
  },
  { correct: 0, incorrect: 0 }
);
console.log("\nAnswer breakdown:");
console.log(` ✅ Correct: ${byCorrectness.correct}`);
console.log(` ❌ Incorrect: ${byCorrectness.incorrect}`);
console.log("\n✅ All activities completed!");
console.log("━".repeat(60));
```

### ผลลัพธ์

```
=== QUIZ APPLICATION ===

QUIZ RESULTS:
Q1: What is 5 + 3?
Your answer: 7
Correct answer: 8
WRONG

Q2: What is the capital of Thailand?
Your answer: Bangkok
CORRECT

FINAL SCORE: 1/2 (50.0%)s
```

### อธิบายการทำงานของโค้ด

---

## ลิงก์ไปยังไฟล์บน GitHub

คุณสามารถคลิกเพื่อดูไฟล์ต้นฉบับได้ที่นี่:
[05-integration.js - Activity 5 ](./05-integration.js)

---
