<h1 style="background-color: #3498db; color: white; padding: 10px; text-align: center;">
    Unit-2: File Organization and Relational Algebra Concepts
</h1>


# UNIT-2: FILE ORGANIZATION AND RELATIONAL ALGEBRA CONCEPTS

## 1. FILE ORGANIZATION  
File organization refers to how data is stored in a file system to optimize retrieval, modification, and storage efficiency. Different methods help in improving performance.  

### 1.1 TYPES OF FILE ORGANIZATION  

#### 1.1.1 INDEXED SEQUENTIAL ACCESS (ISAM)  
- Data is stored in order, and an index is used to find it quickly.  
- Uses primary and secondary indexes for faster access.  
- **Example**: If student records are sorted by roll number, an index helps in jumping directly to a specific roll number.  

#### 1.1.2 B-TREES & B++ TREES  
- **B-Trees**: Balanced tree structures used for indexing large datasets, ensuring fast access.  
- **B++ Trees**: An improved version where all keys are stored at leaf nodes, making range queries more efficient.  

#### 1.1.3 HASHING  
- A technique that maps keys to storage locations for fast data retrieval.  
- **Hashing Functions**: Functions that compute the storage location for a given key.  

#### 1.1.4 COLLISION RESOLUTION TECHNIQUES  
- **Chaining**: Uses linked lists to store multiple records in the same hash bucket.  
- **Open Addressing**: Finds the next available slot when a collision occurs.  

#### 1.1.5 EXTENDIBLE HASHING  
- A dynamic hashing method where the directory expands dynamically, preventing excessive collisions.  

#### 1.1.6 DYNAMIC HASHING (SELF-STUDY)  
- Expands and shrinks hash tables dynamically based on data volume, improving performance and storage utilization.  

---

## 2. RELATIONAL DATABASES  
A **relational database** stores data in **tables** (relations), which consist of **rows** (tuples) and **columns** (attributes).  

### 2.1 RELATIONAL MODEL CONCEPTS  
- Data is organized into tables with well-defined relationships.  
- Each table has a **Primary Key**, which uniquely identifies each row.  
- Relationships between tables are maintained using **Foreign Keys**.  

### 2.2 RELATIONAL CONSTRAINTS  
To maintain data integrity, databases use different constraints:  
1. **Domain Constraint**: Ensures each column has a specific type of data. *(e.g., Age column should only have numbers.)*  
2. **Key Constraint**: Each row must have a unique key (Primary Key).  
3. **Referential Integrity Constraint**: Ensures foreign keys in one table match primary keys in another.  

### 2.3 SQL & SQL CONSTRAINTS  
SQL (Structured Query Language) is used to manage relational databases. Some common constraints in SQL include:  
- `NOT NULL` – Ensures a column cannot have empty values.  
- `UNIQUE` – Ensures all values in a column are unique.  
- `PRIMARY KEY` – Combines NOT NULL and UNIQUE constraints.  
- `FOREIGN KEY` – Ensures referential integrity between two tables.  

**Example SQL Query:**  
```sql
CREATE TABLE Students (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Age INT CHECK (Age > 18),
    Course_ID INT,
    FOREIGN KEY (Course_ID) REFERENCES Courses(Course_ID)
);
```

---

## 3. RELATIONAL ALGEBRA CONCEPTS  
Relational algebra is a set of operations used to manipulate relational database tables. It helps in query processing.  

### 3.1 TYPES OF RELATIONAL OPERATIONS  

1. **Selection (σ)** – Filters rows based on a condition.  
   - **Example**: Select students older than 20.  
   - `σ Age > 20 (Students)`  

2. **Projection (π)** – Selects specific columns.  
   - **Example**: Show only names and ages of students.  
   - `π Name, Age (Students)`  

3. **Union (∪)** – Combines two tables with the same structure.  
   - **Example**: Merge two student lists.  
   - `Students_A ∪ Students_B`  

4. **Intersection (∩)** – Returns common rows between two tables.  
   - **Example**: Find students enrolled in both "Math" and "Science."  

5. **Difference (-)** – Returns rows from one table that are not in another.  
   - **Example**: Find students in "Math" but not in "Science."  

6. **Cartesian Product (×)** – Combines all rows from two tables.  
   - **Example**: Pair every student with every course.  

7. **Join (⨝)** – Combines related rows from two tables.  
   - **Example**: Join "Students" and "Courses" tables on `Course_ID`.  

### 3.2 JOINS IN SQL  
Joins are used in SQL to retrieve related data from multiple tables.  

1. **Inner Join** – Returns matching rows from both tables.  
   ```sql
   SELECT Students.Name, Courses.Course_Name
   FROM Students
   INNER JOIN Courses ON Students.Course_ID = Courses.Course_ID;
   ```
2. **Left Join** – Returns all rows from the first table and matching rows from the second.  
3. **Right Join** – Returns all rows from the second table and matching rows from the first.  
4. **Full Join** – Returns all rows from both tables, with NULL for missing matches.  

---

## 4. STATIC VS. DYNAMIC HASHING  

| **Feature**         | **Static Hashing** | **Dynamic Hashing** |
|---------------------|------------------|------------------|
| **Definition**      | Uses a fixed-size hash table that does not change over time. | Hash table size changes dynamically based on the number of records. |
| **Memory Utilization** | May waste memory if the table is too large; may cause overflow if too small. | Efficient use of memory as the table grows or shrinks as needed. |
| **Performance** | Can slow down due to overflow handling (chaining or open addressing). | Maintains good performance by adjusting the table size automatically. |
| **Collision Handling** | Uses chaining or open addressing to handle overflow when table is full. | Reduces collisions by expanding buckets when needed. |
| **Scalability** | Not scalable; if data size increases, performance decreases. | Highly scalable as it adjusts to data size automatically. |
| **Speed** | Slower in case of high data load due to fixed table size. | Faster because it reorganizes the structure to avoid excessive collisions. |
| **Example Techniques** | Uses **fixed-size** tables and overflow resolution techniques like chaining. | Uses **Extendible Hashing** and **Linear Hashing**, allowing table expansion or contraction. |

---

## 5. DATABASE DESIGN USING EER TO RELATIONAL MODEL  
A **Enhanced Entity-Relationship (EER) model** includes:  
- **Entities (Objects like Students, Courses, etc.)**  
- **Attributes (Properties like Name, Age, Course_ID, etc.)**  
- **Relationships (How entities relate to each other)**  

---

## CONCLUSION  
This unit covers essential concepts of file organization, relational databases, and relational algebra for efficient database design and management. 🚀
