## Mongodb_task
## TASK 09
### 1. Create the Database 
use codinggita  

### 2. Create the students/courses collection

db.createCollection("students");

db.createCollection("courses");

### 2. Insert sample data into the students collection

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

### Result
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677bd6a1a1f1ce2e297a008d'),
    '1': ObjectId('677bd6a1a1f1ce2e297a008e'),
    '2': ObjectId('677bd6a1a1f1ce2e297a008f')
  }
}

### 2.Insert sample data into the courses collection

db.createCollection("courses");
{ ok: 1 }
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
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('677bd6a1a1f1ce2e297a008d'),
    '1': ObjectId('677bd6a1a1f1ce2e297a008e'),
    '2': ObjectId('677bd6a1a1f1ce2e297a008f')
  }
}
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

### Result
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