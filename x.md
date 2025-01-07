***Task 1: Add multiple students
Insert at least 5 students into the students collection with unique roll numbers, names, departments, years, and subjects enrolled***

```js
db.students.insertMany([
  {
    rollNumber: 101,
    name: "Alice Smith",
    department: "Computer Science",
    year: 1,
    subjects: ["Data Structures", "Algorithms", "Mathematics"]
  },
  {
    rollNumber: 102,
    name: "Bob Johnson",
    department: "Electrical Engineering",
    year: 2,
    subjects: ["Circuits", "Electromagnetics", "Signals & Systems"]
  },
  {
    rollNumber: 103,
    name: "Charlie Lee",
    department: "Mechanical Engineering",
    year: 3,
    subjects: ["Thermodynamics", "Fluid Mechanics", "Heat Transfer"]
  },
  {
    rollNumber: 104,
    name: "Diana Patel",
    department: "Civil Engineering",
    year: 1,
    subjects: ["Structural Analysis", "Materials Science", "Surveying"]
  },
  {
    rollNumber: 105,
    name: "Eva Wang",
    department: "Information Technology",
    year: 2,
    subjects: ["Database Systems", "Computer Networks", "Software Engineering"]
  }
])
```


**Task 2: Add multiple subjects**
Insert **4 subjects** into the `subjects` collection, each with 3 to 5 topics.

```js
db.subjects.insertMany([
  { 
    "subjectName": "React",
    "topics": [
      "JSX", 
      "Components", 
      "State", 
      "Props", 
      "Hooks"
    ]
  },
  { 
    "subjectName": "NodeJS", 
    "topics": [
      "Modules", 
      "Express", 
      "File System", 
      "Asynchronous Programming"
    ]
  },
  { 
    "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
  },
  {
  "subjectName": "JavaScript",
  "topics": [
    "Introduction to JavaScript",
    "Functions and Scope",
    "Asynchronous Programming",
    "ES6+ Features"
  ]
}
]);

#### **Task 3: Query students based on subject enrollment**
Query the `students` collection to find all students who are enrolled in **NodeJS**.

```js
db.subjects.find({
  subjectName: "NodeJS"
})
```

#### **Task 4: Add a new topic to a subject**
Add a new topic to the **NodeJS** subject.

```db.subjects.updateOne(
  { "subjectName": "NodeJS" },
  { $push: { "topics": "NPM" } }
);
```

#### **Task 5: Query subjects with multiple topics**
Query the `subjects` collection to find subjects that contain **at least 4 topics**.

```
db.subjects.find({ "topics": { $size: { $gte: 4 } } });
```