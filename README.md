# student management -sql-project
# Student-Management-System
🎓 Student Management System  The Student Management System is a software application designed to efficiently manage student records and academic information. This system helps educational institutions store, organize, and retrieve student data in a structured and secure manner.
It provides a structured way to store, retrieve, and manage data related to students, teachers, courses, departments, enrollments, and grades.

This project demonstrates database design concepts such as:

Primary and Foreign Keys

One-to-Many Relationships

Many-to-Many Relationships

CRUD Operations (Create, Read, Update, Delete)

✨ Features

Add new student records

Update student information

Delete student records

Search students by ID or name

Manage departments and courses

Enroll students in courses

Record and manage grades

Maintain relational database integrity

🗂️ Database Tables

The system includes the following tables:

Students

Teachers

Departments

Courses

Enrollments

Grades

Users (optional – for authentication)

🔗 Entity Relationships

One Department → Many Teachers

One Department → Many Courses

One Teacher → Many Courses

Many Students ↔ Many Courses (via Enrollments table)

Grades linked to Students and Courses
✅ Advantages
1️⃣ Centralized Data Management

All student information is stored in one database, making it easy to manage and access.

2️⃣ Improved Data Accuracy

Reduces manual errors compared to paper-based systems.

3️⃣ Easy Data Retrieval

Quick search and retrieval of student records using SQL queries.

4️⃣ Better Organization

Structured tables (Students, Courses, Enrollments, etc.) keep data well organized.

5️⃣ Time Saving

Automates record management, saving administrative time.

6️⃣ Data Security

User authentication and database permissions improve security.

7️⃣ Scalability

MySQL databases can handle large numbers of student records efficiently.

8️⃣ Relationship Management

Supports One-to-Many and Many-to-Many relationships using foreign keys.

❌ Disadvantages
1️⃣ Initial Setup Complexity

Requires proper database design and configuration.

2️⃣ Maintenance Required

Needs regular database backups and maintenance.

3️⃣ Technical Knowledge Needed

Users must understand SQL and database management.

4️⃣ Security Risks

If not configured properly, the database may be vulnerable to attacks.

5️⃣ Cost (Optional)

Advanced hosting or server setups may involve additional costs.

6️⃣ System Dependency

If the system crashes or the server fails, access to data may be temporarily lost.

--step 1:create database

    Create databases students _records;
--step 2: use database

    use students _records;
--step 3:create Tables students 

    create table students (
    student _id int primary key,
    name varchar (50),
    email varchar (50),
    phone_ number varchar (50),
    enrollment _date date); 
  --step 4: create Tables teachers
  
    create table teachers(
    teacher_id int primary key,
    name varchar(50),
    phone_number varchar(50),
    hire_date date);
  --step 5: create Tables course
  
         Create table course (
    course_ id INT PRIMARY KEY,
    course_ name VARCHAR (255) NOT NULL,
    teacher_ id INT,
    foreign key (teacher_ id) references teachers (teacher_ id));
--step 6: create Tables enrollment 

    CREATE TABLE enrollment (
       enrollment_id INT PRIMARY KEY,
      student_id INT,
       course_id INT,
     enrollment_date DATE,
     FOREIGN KEY (student_id) REFERENCES students(student_id),
       FOREIGN KEY (course_id) REFERENCES course(course_id)
     );
-- step 7: insert values into students Table

           insert into students (student _ id, name, email, phone _number, enrollment _date) values
      (10, 'John Doe', 'john33@gmail.com', '5556612734', '2025-01-01'),
     (11, 'Rahul ram', 'rahul12@gmail.com', '55530002', '2025-01-02'),
     (12, 'Krishna ', 'krishna34@gmail.com', '55530003', '2025-01-03'),
     (42, 'Shankar', 'shankar23@gmail.com', '55520004', '2025-01-04'),
     (52, 'Prashant', 'prashant45@gmail.com', '55503005', '2025-01-05'),
     (62, ' nursing ', 'narsing13@gmail.com', '5550006', '2025-01-06'),
     (72, 'Santosh', 'santosh40@gmail.com', '5550007', '2025-01-07'),
     (82, 'Deepak t', 'deepak00@example.com', '55567777', '2025-01-08'),
     (92, 'Avinash', 'avinash98@example.com', '124567892', '2025-01-09'),
    (102, 'Maja', 'maja17@gmail.com', '1234567892', '2025-01-10'),
     (103, 'Anant', 'bhandare43@gmail.com', '9080405020', '2025-01-10'); 
--step 8: insert values into teachers Table

      insert into teachers (teacher_ id, name, phone _number, hire_ date) values
     (101, 'Abdul kalam','9080405020', '2024-12-10'),
     (109,'vikas divyankirti','902003000','2024-12-20'),
     (108,'sunil kumar','123456780','2024-12-01'),
     (106,'swami vivekananda','1090807030','2023-12-28'),
    (105,'madan Mohan malviy','000001010','2024-12-27'),
    (104,'dr a p j Abdul kalam','0123454673','2023-02-26'),
     (112,'rajinder singh','9844802326','2023-01-27'),
    (113,'anand kumar','90987623','2023-01-25'),
    (114,'anju dahiya','093457791','2024-12-23'),
    (115,'himachal pradesh','123564456','2024-12-24');
--step 9: insert values into course Table

    Insert into course (course_id, course_name, teacher_id) values
    (1001, 'Mathematics', 101),
    (1002, 'computer science', 101),
    (1003, 'software enginerring', 104),
     (1004, 'digital marketing', 104),
       (1005, 'English ', 105),
     (1006, 'Computer Science', 106),
     (1007, 'cloud computing', 109),
    (1008, 'data science', 113),
    (1009, 'devops', 112),
    (1010, 'cyber security', 115);
--step 10: insert values into enrollment Table

    Insert into enrollment (enrollment_id, student_id, course_id, enrollment_date) values
     (201, 10, 1001, '2024-01-10'),
    (202, 11, 1001, '2024-01-12'),
    (203, 12, 1003, '2024-01-15'),
    (204, 12, 1004, '2024-01-18'),
    (205, 42, 1005, '2024-01-20'),
    (206, 52, 1006, '2024-02-01'),
    (207, 62, 1007, '2024-02-05'),
    (208, 72, 1008, '2024-02-08'),
    (209, 103, 1009, '2024-02-11'),
    (2010, 102, 1010, '2024-02-15');
step 13: Queries and outputs
1.List all students with their details. 

    SELECT * FROM Students;
2.List all teachers with their details

    SELECT * FROM Teachers;
3.List all courses along with the teacher’s name. 

    SELECT 
    c.course_id,
    c.course_name,
    c.course_code,
    c.credits,
    CONCAT(t.first_name, ' ', t.last_name) AS teacher_name,
    d.department_name
    FROM Courses c
    JOIN Teachers t ON c.teacher_id = t.teacher_id
    JOIN Departments d ON c.department_id = d.department_id;
4.Find students enrolled after January 5, 2025

    SELECT * 
    FROM Students
    WHERE enrollment_date > '2025-01-05';
5.Find teachers hired before January 10, 2024

    SELECT * FROM Teachers WHERE hire_date < '2024-01-10';
6.Find all courses taught by teacher named 'Abdul Kalam'

    SELECT c.*FROM Courses cJOIN Teachers t ON c.teacher_id = t.teacher_id WHERE CONCAT(t.first_name, ' ', t.last_name) = 'Abdul Kalam';
7.Search students by name containing 'an'

    SELECT * FROM Students WHERE first_name LIKE '%an%' OR last_name LIKE '%an%';
8.Count total students enrolled

    SELECT COUNT(*) AS total_students FROM Students;
9.Count total teachers hired

    SELECT COUNT(*) AS total_teachers FROM Teachers;
10.List courses with 'computer science' in the name

    SELECT * FROM Courses WHERE course_name LIKE '%computer science%';
11.Get the phone number of the student named 'John Doe'

    SELECT phone_number FROM Students WHERE CONCAT(first_name, ' ', last_name) = 'John Doe';
12.Get teacher details with phone number starting with '123'

    SELECT * FROM Teachers WHERE phone_number LIKE '123%';

13.List students enrolled on the same day (Jan 10, 2025)

    SELECT * FROM Students WHERE enrollment_date = '2025-01-10';
14.List courses and the hire date of their teachers

    SELECT c.course_name, CONCAT(t.first_name, ' ', t.last_name) AS teacher_name, t.hire_date
    FROM Courses c
    JOIN Teachers t ON c.teacher_id = t.teacher_id;
15.Find courses taught by teachers hired after 2024-12-01

    SELECT c.course_name, CONCAT(t.first_name, ' ', t.last_name) AS teacher_name, t.hire_date
    FROM Courses c
    JOIN Teachers t ON c.teacher_id = t.teacher_id
    WHERE t.hire_date > '2024-12-01';
16.Update the name of a student

    update students set name ='ram' where student_id='102';

17.List students sorted by enrollment_date (newest first)

    SELECT * FROM Students ORDER BY enrollment_date DESC;
18.List teachers sorted by hire_date (oldest first)

    SELECT * FROM Teachers ORDER BY hire_date ASC;
19.Get student emails ending with 'gmail.com'

    SELECT * FROM Students WHERE email LIKE '%gmail.com';
20.List students with phone numbers longer than 9 digits

    SELECT * FROM Students WHERE LENGTH(phone_number) > 9;



  
    

  




