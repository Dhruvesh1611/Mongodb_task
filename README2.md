## TASK 10 ##
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
#### **Task 5: Query subjects with multiple topics**
Query the `subjects` collection to find subjects that contain **at least 4 topics**.
```js
db.students.aggregate([
  { $match: { "topics": { $exists: true, $type: "array" } } },
  { $project: { name: 1, rollNumber: 1, 
  topicsCount: { $size: "$topics" } } },
  { $match: { topicsCount: { $gt: 4 } } }
]);

```


#### **Task 6: Update student enrollment**
Add the subject **"React Native"** to **Jenil's** subjects.
```js
db.students.updateOne({"name": "Jenil"}, {
$push: {"topics" : "React Native"}});

```

#### **Task 7: Query all students**
Query all students in the database and print out their names and enrolled subjects.

```bash
db.students.find({}, {"name": 1, "subjectsEnrolled": 1});

```
#### **Task 8: Update multiple students' year**
Update the year for all students in the **Computer Science** department to year 3.

```js
db.students.updateMany(
  {"department": "Computer Science"}, 
  {$set: {"year": 3}}
);

```

#### **Task 9: Add new topics to multiple subjects**
Add new topics to **React**, **NodeJS**, and **MongoDB** subjects. Ensure each subject gets at least **one** new topic.
```js
db.subjects.updateOne(
  { "subjectName": "React" },
  { $push: { "topics": "Introduction" } }
);

db.subjects.updateOne(
  { "subjectName": "NodeJS" },
  { $push: { "topics": "Async Programming" } }
);

db.subjects.updateOne(
  { "subjectName": "MongoDB" },
  { $push: { "topics": "Aggregation Framework" } }
);

```


#### **Task 10: Remove a topic from a subject**
Remove the topic **"Express"** from the **NodeJS** subject.
```js
db.subjects.updateOne(
  { "subjectName": "NodeJS" },  
  { $pull: { "topics": "Express" } }  
);

```

#### **Task 11: Query all students in a specific year**
Query and return all students in **year 2** or **year 3**.
```js
db.students.find({"year": { $in: [2, 3] }})
```
#### **Task 12: Delete a student by roll number**
Delete a student from the database using their **roll number**.
```js
db.students.deleteOne({"rollNumber": 103});
```
#### **Task 13: Delete all students from a department**
Delete all students who belong to the **Electrical Engineering** department.
```js
db.students.deleteMany({"department": "Electrical Engineering"});
```
#### **Task 14: Retrieve all topics for a subject**
Query the **MongoDB** subject and retrieve all topics listed for it.
```js
db.subjects.find({"subjectName":"MongoDB"}, {"topics" : 1});

```
#### **Task 15: Count the number of subjects in which a student is enrolled**
Write a query that returns the number of subjects each student is enrolled in.
```js
db.students.aggregate([
  {
    $project: {
      "name": 1,
      "coursesEnrolledCount": { $size: "$coursesEnrolled" }
    }
  }

]);
```
---