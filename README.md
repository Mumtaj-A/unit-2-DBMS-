Unit-2: File Organization and Relational Algebra Concepts

1. File Organization

File organization refers to how data is stored in a file system to optimize retrieval, modification, and storage efficiency. Different methods help in improving performance.

1.1 Types of File Organization

1.1.1 Indexed Sequential Access (ISAM)

Data is stored in order, and an index is used to find it quickly.

Uses primary and secondary indexes for faster access.

Example: If student records are sorted by roll number, an index helps in jumping directly to a specific roll number.

1.1.2 B-Trees & B++ Trees

B-Trees: Balanced tree structures used for indexing large datasets, ensuring fast access.

B++ Trees: An improved version where all keys are stored at leaf nodes, making range queries more efficient.

1.1.3 Hashing

A technique that maps keys to storage locations for fast data retrieval.

Hashing Functions: Functions that compute the storage location for a given key.

1.1.4 Collision Resolution Techniques

Chaining: Uses linked lists to store multiple records in the same hash bucket.

Open Addressing: Finds the next available slot when a collision occurs.

1.1.5 Extendible Hashing

A dynamic hashing method where the directory expands dynamically, preventing excessive collisions.

1.1.6 Dynamic Hashing (Self-Study)

Expands and shrinks hash tables dynamically based on data volume, improving performance and storage utilization.

2. Relational Databases

A relational database stores data in tables (relations), which consist of rows (tuples) and columns (attributes).

2.1 Relational Model Concepts

Data is organized into tables with well-defined relationships.

Each table has a Primary Key, which uniquely identifies each row.

Relationships between tables are maintained using Foreign Keys.

2.2 Relational Constraints

To maintain data integrity, databases use different constraints:

Domain Constraint: Ensures each column has a specific type of data. (e.g., Age column should only have numbers.)

Key Constraint: Each row must have a unique key (Primary Key).

Referential Integrity Constraint: Ensures foreign keys in one table match primary keys in another.

2.3 SQL & SQL Constraints

SQL (Structured Query Language) is used to manage relational databases. Some common constraints in SQL include:

NOT NULL – Ensures a column cannot have empty values.

UNIQUE – Ensures all values in a column are unique.

PRIMARY KEY – Combines NOT NULL and UNIQUE constraints.

FOREIGN KEY – Ensures referential integrity between two tables.

Example SQL Query:

CREATE TABLE Students (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Age INT CHECK (Age > 18),
    Course_ID INT,
    FOREIGN KEY (Course_ID) REFERENCES Courses(Course_ID)
);

3. Relational Algebra Concepts

Relational algebra is a set of operations used to manipulate relational database tables. It helps in query processing.

3.1 Types of Relational Operations

Selection (σ) – Filters rows based on a condition.

Example: Select students older than 20.

σ Age > 20 (Students)

Projection (π) – Selects specific columns.

Example: Show only names and ages of students.

π Name, Age (Students)

Union (∪) – Combines two tables with the same structure.

Example: Merge two student lists.

Students_A ∪ Students_B

Intersection (∩) – Returns common rows between two tables.

Example: Find students enrolled in both "Math" and "Science."

Difference (-) – Returns rows from one table that are not in another.

Example: Find students in "Math" but not in "Science."

Cartesian Product (×) – Combines all rows from two tables.

Example: Pair every student with every course.

Join (⨝) – Combines related rows from two tables.

Example: Join "Students" and "Courses" tables on Course_ID.

3.2 Joins in SQL

Joins are used in SQL to retrieve related data from multiple tables.

Inner Join – Returns matching rows from both tables.

SELECT Students.Name, Courses.Course_Name
FROM Students
INNER JOIN Courses ON Students.Course_ID = Courses.Course_ID;

Left Join – Returns all rows from the first table and matching rows from the second.

Right Join – Returns all rows from the second table and matching rows from the first.

Full Join – Returns all rows from both tables, with NULL for missing matches.

4. Static vs. Dynamic Hashing

Feature

Static Hashing

Dynamic Hashing

Definition

Uses a fixed-size hash table that does not change over time.

Hash table size changes dynamically based on the number of records.

Memory Utilization

May waste memory if the table is too large; may cause overflow if too small.

Efficient use of memory as the table grows or shrinks as needed.

Performance

Can slow down due to overflow handling (chaining or open addressing).

Maintains good performance by adjusting the table size automatically.

Collision Handling

Uses chaining or open addressing to handle overflow when table is full.

Reduces collisions by expanding buckets when needed.

Scalability

Not scalable; if data size increases, performance decreases.

Highly scalable as it adjusts to data size automatically.

Speed

Slower in case of high data load due to fixed table size.

Faster because it reorganizes the structure to avoid excessive collisions.

Example Techniques

Uses fixed-size tables and overflow resolution techniques like chaining.

Uses Extendible Hashing and Linear Hashing, allowing table expansion or contraction.

5. Database Design using EER to Relational Model

A Enhanced Entity-Relationship (EER) model includes:

Entities (Objects like Students, Courses, etc.)

Attributes (Properties like Name, Age, Course_ID, etc.)

Relationships (How entities relate to each other)
