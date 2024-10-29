# University of Texas Global Faculty Database Project

This project provides a structured database and dashboard to analyze faculty information, including their expertise, department affiliations, and international interests. It utilizes various data science techniques (3NF, K-means clustering, Transformers, Unstructured Data Analytics) and data visualization tool (Tableau) to facilitate insights into faculty expertise areas and their global reach. The repository contains a Jupyter Notebook (`Texas_Global.ipynb`) with code, as well as screenshots of a Tableau dashboard and the database’s Entity-Relationship Diagram (ERD).

## Contents

1. `Texas_Global.ipynb`: Code file containing data processing and analytical steps.
2. Tableau Dashboard: Visual representation of faculty expertise and global reach.
3. Entity-Relationship Diagram (ERD): Database structure for faculty data.

---

## Techniques Used in `Texas_Global.ipynb`

The code in `Texas_Global.ipynb` covers multiple data processing, exploration, and analysis techniques, including:

### 1. Data Import and Cleaning

   - The code begins by importing data from Filemaker Pro faculty data in a CSV file, which contain faculty, department, expertise, and country information.
   - Basic cleaning processes, such as handling missing values and standardizing column names, are employed to prepare data for analysis.

### 2. Data Normalization to 3NF

   - The `fmp-dump.csv` data is processed to achieve Third Normal Form (3NF), which enhances data integrity and reduces redundancy.
   - Key steps include:
     - Identifying and separating functional dependencies within the data.
     - Creating new tables (e.g., `Department`, `Faculty`, `Expertise`, `Countries`) to represent each entity individually.
     - Adding link tables, such as `Faculty Expertise Table` and `Faculty Country of Interest Table`, to manage many-to-many relationships without redundancy.
     - Defining primary keys for each table and establishing foreign key relationships, as shown in the ERD.
   - This normalization ensures the data structure is efficient, consistent, and optimized for analysis.

### 3. Data Merging and Relational Mapping

   - Merges are performed across normalized datasets to combine faculty details with their expertise and countries of interest.
   - SQL-like operations in Python (`pandas` library) enable the connection of datasets, following the structure defined in the ERD.


### 4. Data Preparation for Visualization

   - Data is aggregated and grouped based on expertise categories and geographical location to facilitate visual analysis.
   - Final tables are formatted to align with the requirements of the Tableau dashboard, ensuring compatibility for efficient data visualization.

---

## Tableau Dashboard

The Tableau dashboard (`Dashboard 1`) offers an interactive interface to explore the faculty data visually. Key components of the dashboard include:

### 1. Faculty-Expertise Bar Chart

   - Displays a bar chart that ranks expertise areas by the number of faculty members.
   - Allows users to see which expertise areas have the highest representation among faculty.

   ![Faculty-Expertise Bar Chart](Images/faculty_expertise_bar_chart.png)

### 2. Global Map of Faculty Interests

   - A world map visualization shows the distribution of faculty interests across different countries.
   - Countries are shaded to reflect the number of faculty members with interests in each location, providing a quick view of international engagement.

   ![Global Map of Faculty Interests](Images/global_map_faculty_interests.png)

These visualizations enable users to understand faculty expertise and international interests, helping to identify areas of strength and potential for global collaboration.

---

## Entity-Relationship Diagram (ERD)

The ERD provides a conceptual view of the faculty database structure, defining relationships between the main entities:

1. **Department Table**: Contains department details, including `DepartmentID`, `Department Name`, and associated `School`.
2. **Faculty Table**: Lists faculty members, including `FacultyID`, `DepartmentID` (foreign key), `First Name`, `Last Name`, and `Job Title`.
3. **Faculty Expertise Table**: Relates faculty to their areas of expertise, connecting `FacultyID` and `ExpertiseID` to identify individual faculty expertise.
4. **Expertise Table**: Details various expertise categories with `ExpertiseID` and `Category Name`.
5. **Faculty Country of Interest Table**: Links faculty to countries of interest, using `FacultyID` and `CountryID`.
6. **Countries Table**: Lists countries with `CountryID` and `Country Name`.

   ![Entity-Relationship Diagram (ERD)](Images/ERD.png)

The ERD represents a normalized relational database structure that minimizes redundancy and optimizes data retrieval for complex queries.

---
