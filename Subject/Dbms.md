# DBMS Notes

[SQL Practice Question](https://www.notion.so/SQL-Practice-Question-1db620726aa88005809dec07ba805431?pvs=21)

## What is Data

Data is any fact that can be stored.

> **Data when processed becomes Information**

## What is Database

A database is a structured collection of interrelated data organized to enable efficient storage, retrieval, and manipulation of information. Key characteristics include:

- Collection of interrelated data.
- Stored in the form of tables.
- Can be of any size.

## What is File System

A file system is a structure used by an operating system to manage and organize files on a storage device (e.g., hard drive, USB flash drive). It defines how data is organized, accessed, and stored, acting as an interface between the user and the data.

## Disadvantages of the File System

- **Data Redundancy**: Duplication occurs when the same data (e.g., customer information) is stored in multiple files, like separate spreadsheets for sales, contacts, and inventory.
- **Poor Memory Utilization**: Storing redundant data wastes memory resources.
- **Data Inconsistency**: Inconsistent updates (e.g., updating a customer’s address in one file but not others) lead to conflicting data.
- **Data Security**: File systems lack controlled access, unlike DBMS, which can restrict access to sensitive data.

## Database Management System (DBMS)

DBMS is software designed to manage, manipulate, and organize large volumes of data efficiently. It acts as an interface between the database and users/applications, providing tools for storing, retrieving, updating, and managing data securely.

**Examples**: Banking Systems, Airline Reservation Systems, Education Management Systems.

## Need for DBMS

- Manage data (Insert, Delete, Update, Search).
- Ensure data accuracy and security (prevent unauthorized access).
- Support decision-making.

## Advantages of DBMS

- **Data Security**: Protects against unauthorized access.
- **Data Redundancy and Inconsistency**: Eliminates redundancy, minimizing storage needs and ensuring consistency by maintaining a unified data version.  
  *Example*: Multiple registers storing the same data waste memory and slow updates.
- **Data Integrity**: Enforces rules/constraints to prevent incorrect data.  
  *Example*: Ensures age is entered as an integer.
- **Data Scalability**: Handles large datasets and scales with growth.  
  *Example*: Seamlessly adds 1200 new employee records to a database of 40 employees.
- **Data Abstraction**: Allows interaction with the database without understanding underlying complexities.

## Disadvantages of DBMS

- High cost.
- Unsuitable for small projects.
- Vendor lock-in (e.g., switching from SQL to NoSQL is difficult).

## Data Abstraction

Data abstraction hides complex database organization details from users, simplifying interaction.  
*Example*: Users don’t need to know about indexing, memory storage, or data structures to interact with the database.

### Levels of Abstraction

- **Physical Level**: Describes how data is stored, including complex data structures.
- **Logical Level**: Middle level; defines what data is stored and its structure.
- **View Level**: Highest level; focuses on user interaction and accessible data.

## What is Schema

A schema is a logical container defining the database structure, including:

- Data organization.
- Data types.
- Constraints.
- Relationships.
- Acts as a blueprint for data integrity, consistency, and efficient retrieval.

### Types of Schema

- **Physical Schema**: Defines how data is stored on hardware (e.g., storage format, indexing).  
  **Characteristics**: Focuses on optimizing storage/retrieval.  
  *Example*: Clustered indexing for faster retrieval.
- **Logical Schema**: Defines data structure, tables, relationships, and constraints.  
  **Characteristics**: Prioritizes data modeling over hardware specifics.  
  *Example*: Defining tables, primary/foreign keys, and views.

#### Types of Logical Schema

- **Conceptual Schema**: Represents the overall database structure and relationships.  
  *Example*: University database with Student, Course, and Department entities, where Students enroll in Courses, and Courses are offered by Departments.
- **External/View Schema**: User-specific views of the database.  
  *Example*: Student Portal view showing StudentID, Name, Address, and CoursesEnrolled, excluding other students’ data.

## What is Instance

An instance is the data residing in a database at a specific point in time.

## 3-Tier DBMS Architecture

- **Presentation Layer**: Handles the user interface.
- **Application Layer**: Manages business logic.
- **Data Layer**: Manages data storage and processing.

### Advantages of 3-Tier Architecture

- **Scalability**: Distributed deployment allows layer-specific adjustments.
- **Security**: Clients don’t directly access the server.
- **Modularity and Maintainability**: Simplified maintenance due to separated responsibilities.
- **Performance**: Individual optimization of layers improves performance.

### Disadvantages of 3-Tier Architecture

- **Increased Complexity**: Extra middle layer doubles communication points.
- **Potential Latency/Bottlenecks**: Processing steps increase latency risks.
- **Longer Development Time**: Distributed responsibilities extend development.
- **Resource Overhead**: Additional tier increases development/maintenance costs.

## Data Model

Data models define relationships between database components.

### Types of Data Models

1. **Hierarchical Data Model**: Tree structure with parent-child relationships; used in older systems.
2. **Network Data Model**: Graph-like structure with multiple parent-child relationships; more flexible than hierarchical.
3. **Relational Data Model**: Organizes data into tables (relations) with rows/columns; uses SQL; based on set theory.
4. **Entity-Relationship Model (ER Model)**: Represents entities and relationships visually.
5. **Object-Oriented Data Model**: Integrates object-oriented principles.

### NoSQL Data Models

- **Document-oriented** (e.g., MongoDB).
- **Key-value** (e.g., Redis).
- **Column-family** (e.g., Cassandra).
- **Graph** (e.g., Neo4j).

## Entity and Its Types

- **Strong Entity**: Has a unique primary key; exists independently.  
  *Example*: “Person” entity.
- **Weak Entity**: Lacks its own primary key; depends on a strong entity.  
  *Example*: “Dependents” entity relies on “Employee” entity.

## E-R and EER Diagrams

- **E-R Diagram**: Visualizes entities, attributes, and relationships.
- **EER Diagram**: Enhanced ER diagram with additional features (e.g., specialization, generalization).

### Relationship and Degree in ER Model

- **Strong Relationships**: Between strong entities.
- **Weak Relationships**: Involve weak entities.

#### Degree Types

| Degree | Name           | Definition                           |
|--------|----------------|--------------------------------------|
| 1      | Unary          | Relation with a single attribute     |
| 2      | Binary         | Relation with two attributes         |
| 3      | Ternary        | Relation with three attributes       |
| 4+     | N-ary          | Relation with more than three attributes |

## Null Value

A null value represents missing or inapplicable data due to:

- **Not Needed Information**: E.g., “Spouse Name” for an unmarried person.
- **Unknown Answer**: E.g., Unknown quiz answer.
- **Forgot to Fill In**: Missing data due to oversight.

## Types of Keys

- **Candidate Key**: Attribute(s) that can uniquely identify a record.
- **Primary Key**: Unique identifier for a record; no duplicates allowed.
- **Foreign Key**: Attribute linking to a primary key in another table.
- **Super Key**: Set of attributes that can uniquely identify a record.

## Normalization

Normalization organizes data to eliminate redundancy and ensure consistency.

### First Normal Form (1NF)

- Columns contain atomic (indivisible) values.
- Single-type values per column.
- No repeating groups/arrays.

### Second Normal Form (2NF)

- In 1NF.
- Non-key attributes fully depend on the entire primary key (no partial dependency).

*Example*: Split a table with partial dependency (e.g., StudentName depending on StudentID) into separate tables.

### Third Normal Form (3NF)

- In 2NF.
- Attributes depend only on the primary key (no transitive dependency).

*Example*: Separate transitive dependencies (e.g., CustomerName depending on CustomerID) into new tables.

### Boyce-Codd Normal Form (BCNF)

- In 3NF.
- For every functional dependency, the determinant is a super key.

### Fourth Normal Form (4NF)

- In BCNF.
- No multi-valued dependencies.

*Example*: Decompose tables with independent attributes (e.g., Course and Hobby).

### Fifth Normal Form (5NF)

- In 4NF.
- Cannot be decomposed without losing data or adding redundancy.

## Functional Dependency

A functional dependency (X → Y) describes a relationship where X (determinant) determines Y (dependent).

- **Full Functional Dependency**: Y depends entirely on X; removing any attribute from X breaks the dependency.  
  *Example*: (StudentID, CourseID) → Grade.
- **Partial Functional Dependency**: Non-key attribute depends on part of a composite key.  
  *Example*: StudentName depends on StudentID, not (StudentID, CourseID).
- **Trivial Functional Dependency**: Dependent attribute is part of the determinant.  
  *Example*: (Roll no., Name) → Name.
- **Non-trivial Functional Dependency**: Dependent attribute is not part of the determinant.  
  *Example*: (Roll no., Name) → Dept name.
- **Transitive Dependency**: Indirect dependency (A → B, B → C, so A → C).  
  *Example*: Roll no. → Dept name → Dept building.
- **Multivalued Dependency**: Independent dependent attributes.  
  *Example*: Roll no. → (Name, Dept name).

## Vertical and Horizontal Scaling

- **Vertical Scaling**: Adding resources (e.g., CPU, RAM) to an existing system.  
  *Example*: Upgrading a server’s RAM; easier and cheaper but limited by hardware capacity.
- **Horizontal Scaling**: Adding new servers to the system.  
  *Example*: Adding server racks; more complex and costly but highly resilient.

### Differences Between Horizontal and Vertical Scaling

| Horizontal Scaling | Vertical Scaling |
|--------------------|------------------|
| Adds new servers | Adds resources to existing system |
| Expands horizontally | Expands vertically |
| Easier to upgrade | Harder; may require downtime |
| Difficult to implement | Easy to implement |
| Costly (new servers) | Cheaper (new resources) |
| More time to implement | Less time to implement |
| High resilience, fault-tolerant | Single point of failure |
| Examples: Cassandra, MongoDB | Examples: MySQL, Amazon RDS |

### Advantages of Vertical Scaling

- Cost-effective.
- Simple to implement/manage.
- Fast to scale up.

### Disadvantages of Vertical Scaling

- Limited by single machine capacity.
- May require downtime.
- Single point of failure.

### Advantages of Horizontal Scaling

- High availability; no single point of failure.
- Scales indefinitely by adding machines.
- No downtime for upgrades.

### Disadvantages of Horizontal Scaling

- Complex to implement/manage.
- More expensive.
- Time-consuming to configure new servers.