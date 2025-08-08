# -DATABASE-MIGRATION-

CODTECH IT SOLUTIONS PVT.LTD

Dhana Packiyam M

CT04DH2476

SQL

 Neela Santhosh Kumar 

 📄 Task Description: Data Migration from MySQL to PostgreSQL
The goal of this task is to migrate data from a MySQL database to a PostgreSQL database, using a structured, reliable process that preserves data integrity, maintains relationships between tables, and ensures no data is lost or corrupted in the process. The dataset used includes two related tables: Customers and Orders, where the Orders table contains a foreign key (CustomerID) referencing the Customers table.

Data migration between different relational database systems (RDBMS) like MySQL and PostgreSQL is a common need in real-world scenarios — often driven by performance requirements, licensing changes, or better support for specific features in the target system. However, differences in syntax, data types, and constraint enforcement between systems make it crucial to plan and validate the migration carefully.

🔹 Step-by-Step Migration Approach
Exporting Data from MySQL
The first step is to export the existing data and schema from the MySQL database. This can be done using the mysqldump utility. You can export both the schema and data into an SQL file or choose to export the data as CSV files using the --tab option. For compatibility with PostgreSQL, the --compatible=postgresql flag is useful to reduce syntax issues.

Creating the Schema in PostgreSQL
PostgreSQL requires a corresponding schema before data can be imported. You manually create tables in PostgreSQL using CREATE TABLE statements that mirror the structure of the original MySQL tables. Data types such as VARCHAR, INT, and foreign key constraints should be defined properly to maintain the relational structure.

Importing Data into PostgreSQL
After the schema is set, data is imported using PostgreSQL’s COPY command for CSV files or psql for SQL dumps. If using CSV, you must ensure that delimiters, quotes, and line endings are correctly handled. It’s important to load data in the correct order (e.g., load Customers before Orders) to satisfy foreign key constraints.

Ensuring Data Integrity
This step is critical. You verify that:

Row counts match between the source and target.

Primary and foreign key constraints are still valid.

There are no orphan records (e.g., orders linked to non-existent customers).

Sample data in both systems is identical.

In the given dataset, an integrity issue was discovered: one order (OrderID 104) had a CustomerID (5) that didn’t exist in the Customers table. PostgreSQL would reject this unless foreign key checks are disabled or the data is cleaned beforehand.

<!-- Uploading "Screenshot 2025-08-08 094737.png"... -->

<!-- Uploading "Screenshot 2025-08-08 094737.png"... -->
