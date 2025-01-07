## Mongodb_task
## TASK 09
### 1. Task 1: Create a "CodingGita Students" database

Create a new MongoDB database called CodingGita. Add two collections:

students: Name, roll number, department, year, courses enrolled.
courses: Course code, name, credits, instructor.
Insert sample data into both collections.
use codinggita  

```
db.createCollection("students");

db.createCollection("courses");
```
```js
db.students.insertMany([
  { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS102"]
  },
  { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS103"]
  },
  { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  }
]);
```




### Result
```js
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677bd6a1a1f1ce2e297a008d'),
    '1': ObjectId('677bd6a1a1f1ce2e297a008e'),
    '2': ObjectId('677bd6a1a1f1ce2e297a008f')
  }
}
```
### 2.Insert sample data into the courses collection

```js
db.courses.insertMany([
  { 
    "courseCode": "CS101", 
    "courseName": "Introduction to Programming", 
    "credits": 3, 
    "instructor": "Prof. Sharma" 
  },
  { 
    "courseCode": "CS102", 
    "courseName": "Data Structures", 
    "credits": 3, 
    "instructor": "Prof. Gupta" 
  },
  { 
    "courseCode": "CS103", 
    "courseName": "Algorithms", 
    "credits": 3, 
    "instructor": "Prof. Kapoor" 
  },
  { 
    "courseCode": "EE101", 
    "courseName": "Basic Electrical Engineering", 
    "credits": 4, 
    "instructor": "Prof. Verma" 
  },
  { 
    "courseCode": "EE102", 
    "courseName": "Circuit Theory", 
    "credits": 4, 
    "instructor": "Prof. Yadav" 
  }
]);
```

### Result
```js
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677bd6e3a1f1ce2e297a0090'),
    '1': ObjectId('677bd6e3a1f1ce2e297a0091'),
    '2': ObjectId('677bd6e3a1f1ce2e297a0092'),
    '3': ObjectId('677bd6e3a1f1ce2e297a0093'),
    '4': ObjectId('677bd6e3a1f1ce2e297a0094')
  }
}
```

**do some task**

```js
db.students.find({ "department": "Computer Science" });
```
### result ###
```js
[
  {
    _id: ObjectId('677bd10ce72da967fe9ddd48'),
    name: 'Jenil',
    rollNumber: 101,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS102' ]
  },
  {
    _id: ObjectId('677bd10ce72da967fe9ddd49'),
    name: 'Mahir',
    rollNumber: 102,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS103' ]
  }
]
```


```js
db.students.find({ "year": 2 });
```
### result ###
```js
[
  {
    _id: ObjectId('677bd10ce72da967fe9ddd48'),
    name: 'Jenil',
    rollNumber: 101,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS102' ]
  },
  {
    _id: ObjectId('677bd10ce72da967fe9ddd49'),
    name: 'Mahir',
    rollNumber: 102,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS103' ]
  }
]
```

```js
db.students.find({ "coursesEnrolled": 'CS101' });
```
### result ###
```js
[
  {
    _id: ObjectId('677bd10ce72da967fe9ddd48'),
    name: 'Jenil',
    rollNumber: 101,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS102' ]
  },
  {
    _id: ObjectId('677bd10ce72da967fe9ddd49'),
    name: 'Mahir',
    rollNumber: 102,
    department: 'Computer Science',
    year: 2,
    coursesEnrolled: [ 'CS101', 'CS103' ]
  }
]
```
```js
db.courses.updateOne(
...   { "courseCode": "CS102" },
...   { $set: { "instructor": "Prof. Mehta" } }
... );

```
### result ###
```js
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```
```js
db.courses.deleteOne({ courseCode: "CS101" })
```
### result ###
```js

  { acknowledged: true, deletedCount: 1 }

```
