Database Management System (DBMS) Notes
What is Data
Data is any fact that can be stored.

Data when processed becomes Information

What is a Database
A database is a structured collection of interrelated data organized to enable efficient storage, retrieval, and manipulation of information. Key characteristics include:

Collection of interrelated data
Stored in the form of tables
Can be of any size

What is a File System
A file system is a structure used by an operating system to manage and organize files on a storage device (e.g., hard drive, USB flash drive). It defines how data is organized, accessed, and stored, acting as an interface between the user and the data.
Disadvantages of File Systems

Data Redundancy: Duplication occurs when the same data (e.g., customer information) is stored in multiple files, such as separate spreadsheets for sales, contacts, and inventory.
Poor Memory Utilization: Storing duplicate data wastes memory resources.
Data Inconsistency: Inconsistent updates (e.g., changing a customer’s address in one file but not others) lead to discrepancies.
Data Security: File systems lack controlled access mechanisms, unlike DBMS, which can restrict access to sensitive data.

Database Management System (DBMS)
A DBMS is software designed to manage, manipulate, and organize large volumes of data efficiently. It acts as an interface between the database and users or applications, providing tools for storing, retrieving, updating, and managing data securely.
Examples: Banking Systems, Airline Reservation Systems, Education Management Systems
Need for DBMS

Managing Data: Supports insert, delete, update, and search operations.
Ensuring Data Accuracy and Security: Prevents unauthorized access.
Supporting Decision-Making: Facilitates data-driven decisions.

Advantages of DBMS

Data Security: Protects data from unauthorized access.
Data Redundancy and Inconsistency: Eliminates redundancy, reducing storage needs and ensuring consistency by maintaining a unified data version.Example: Multiple registers storing the same data waste memory and slow updates.
Data Integrity: Enforces rules and constraints to prevent incorrect data entry.Example: Ensures age is entered as an integer.
Data Scalability: Handles large datasets and scales seamlessly.Example: Adding 1200 new employee records to a database with 40 employees.
Data Abstraction: Allows users to interact with the database without understanding its underlying complexities.

Disadvantages of DBMS

Cost: High implementation and maintenance costs.
Small Projects: Overkill for small-scale applications.
Vendor Lock-in: Switching between DBMS types (e.g., SQL to NoSQL) is challenging.

Data Abstraction
Data abstraction hides complex database structures, making it easier for users to interact with the database without understanding underlying details.  
Example: Users don’t need to know about indexing, memory storage, or data structures to query the database.
Levels of Abstraction

Physical Level: Describes how data is stored, including complex data structures.
Logical Level: Defines what data is stored and its structure (middle level).
View Level: The highest level, focusing on user interaction and accessible data.

What is a Schema
A schema is a logical container that defines the structure of a database, including:

How data is organized
Data types used
Constraints applied
Relationships between data
Ensures data integrity, consistency, and efficient retrieval

Types of Schema

Physical Schema: Defines how data is stored on hardware (e.g., storage format, file organization, indexing).Characteristics: Focuses on optimizing storage and retrieval.Example: Using clustered indexing for faster data retrieval.
Logical Schema: Defines the structure of data in tables, relationships, and constraints, independent of hardware.

Types of Logical Schema

Conceptual Schema: Represents the overall database structure and relationships.Example: A university database with entities like Student (StudentID, Name, Address), Course (CourseID, CourseName), and Department (DepartmentID, DepartmentName), with relationships such as students enrolling in multiple courses.
External/View Schema: Defines user-specific views of the database.Example: A student portal view showing StudentProfile (StudentID, Name, Address, CoursesEnrolled) without access to other students’ data or course details.

Characteristics of Logical Schema

Defines tables, primary/foreign keys, and views.
Prioritizes data modeling over hardware/storage specifics.

What is an Instance
An instance is the information stored in a database at a specific point in time.
3-Tier DBMS Architecture

Presentation Layer: Handles the user interface.
Application Layer: Manages business logic.
Data Layer: Manages data storage and processing.

Advantages of 3-Tier Architecture

Scalability: Each layer can be adjusted independently.
Security: Clients don’t directly access the server.
Modularity and Maintainability: Simplified maintenance due to separated responsibilities.
Performance: Individual optimization of layers improves performance.

Disadvantages of 3-Tier Architecture

Increased Complexity: Additional middle layer doubles communication points.
Potential Latency/Bottlenecks: Issues in any layer can cause delays.
Longer Development Time: Distributed responsibilities increase development time.
Resource Overhead: Extra tier requires more resources for development and maintenance.

Data Models
Data models define relationships between database components.
Types of Data Models

Hierarchical Data Model: Organizes data in a tree structure with parent-child relationships. Used in older systems.
Network Data Model: Allows multiple parent-child relationships, resembling a graph, offering more flexibility.
Relational Data Model: Organizes data into tables (relations) with rows and columns, using SQL for manipulation. Most common model.
Entity-Relationship Model (ER Model): Represents entities and their relationships visually.
Object-Oriented Data Model: Integrates object-oriented programming concepts into databases.

NoSQL Data Models

Document-Oriented: e.g., MongoDB
Key-Value: e.g., Redis
Column-Family: e.g., Cassandra
Graph: e.g., Neo4j

Entity and Its Types
Strong Entity
A strong entity has a unique identifier (primary key) and exists independently.Example: A Person entity with attributes like PersonID, Name.
Weak Entity
A weak entity lacks its own primary key and depends on a strong entity (owner) for its identity.Example: A Dependents entity linked to an Employee entity, where dependents rely on the employee’s ID.
