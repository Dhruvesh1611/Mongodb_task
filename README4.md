#### **Task 1: Add more students to the `students` collection**  
- Add at least 5 new students to the `students` collection with unique names, roll numbers, and course enrollments.

```js
db.students.insertMany([
  { 
    name: "dhruvesh", 
    rollNumber: 104, 
    department: "computer science Engineering", 
    year: 1, 
    coursesEnrolled: ["ME101", "ME102"]
  },
  { 
    name: "krish", 
    rollNumber: 105, 
    department: "computer science Engineering", 
    year: 2, 
    coursesEnrolled: ["EE101", "EE104"]
  },
  { 
    name: "priyasha", 
    rollNumber: 106, 
    department: "computer science Engineering", 
    year: 3, 
    coursesEnrolled: ["CE101", "CE103"]
  },
  { 
    name: "Vanshika", 
    rollNumber: 107, 
    department: "Computer Science", 
    year: 1, 
    coursesEnrolled: ["CS101", "CS105"]
  },
  { 
    name: "arjun", 
    rollNumber: 108, 
    department: "Information Technology", 
    year: 2, 
    coursesEnrolled: ["IT101", "IT102"]
  }
])

```
#### **Task 2: Insert a new course into the `courses` collection**  
Add a new course with the following details:  
  - Course Code: `CS202`  
  - Name: `Data Structures`  
  - Credits: 3  
  - Instructor: `Prof. Krishna`

```js
  db.courses.insertOne({
  "courseCode": "CS202",
  "name": "Data Structures",
  "credits": 3,
  "instructor": "Prof. Krishna"
});
```