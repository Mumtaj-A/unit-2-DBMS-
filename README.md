<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>File Organization and Relational Algebra Concepts</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            line-height: 1.6;
        }
        h1, h2, h3, h4, h5, h6 {
            text-transform: uppercase;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Unit-2: File Organization and Relational Algebra Concepts</h1>
    
    <h2>1. File Organization</h2>
    <p>File organization refers to how data is stored in a file system to optimize retrieval, modification, and storage efficiency. Different methods help in improving performance.</p>
    
    <h3>1.1 Types of File Organization</h3>
    <h4>1.1.1 Indexed Sequential Access (ISAM)</h4>
    <p>Data is stored in order, and an index is used to find it quickly.</p>
    
    <h4>1.1.2 B-Trees & B++ Trees</h4>
    <p>B-Trees: Balanced tree structures used for indexing large datasets, ensuring fast access.</p>
    
    <h4>1.1.3 Hashing</h4>
    <p>A technique that maps keys to storage locations for fast data retrieval.</p>
    
    <h4>1.1.4 Collision Resolution Techniques</h4>
    <p>Chaining: Uses linked lists to store multiple records in the same hash bucket.</p>
    
    <h4>1.1.5 Extendible Hashing</h4>
    <p>A dynamic hashing method where the directory expands dynamically, preventing excessive collisions.</p>
    
    <h2>2. Relational Databases</h2>
    <p>A relational database stores data in tables (relations), which consist of rows (tuples) and columns (attributes).</p>
    
    <h3>2.1 Relational Model Concepts</h3>
    <p>Data is organized into tables with well-defined relationships.</p>
    
    <h3>2.2 Relational Constraints</h3>
    <p>To maintain data integrity, databases use different constraints.</p>
    
    <h2>3. Relational Algebra Concepts</h2>
    <p>Relational algebra is a set of operations used to manipulate relational database tables.</p>
    
    <h3>3.1 Types of Relational Operations</h3>
    <p>Selection (σ) – Filters rows based on a condition.</p>
    
    <h3>3.2 Joins in SQL</h3>
    <p>Joins are used in SQL to retrieve related data from multiple tables.</p>
    
    <h2>4. Static vs. Dynamic Hashing</h2>
    <p>A comparison of static and dynamic hashing.</p>
    
    <h2>5. Database Design using EER to Relational Model</h2>
    <p>An Enhanced Entity-Relationship (EER) model includes entities, attributes, and relationships.</p>
</body>
</html>
