# Travel Agency Project

This is the **first individual delivery** for the Fullstack Developer course offered by **Recode Pro AI**.

## Project Overview

The project simulates the homepage of a fictional travel agency. This initial phase focuses on visual presentation and database planning, laying a solid foundation for the final solution. No dynamic features or interactive systems are required at this stage.

---

## Requirements

### 1. Visual Interface
Create a homepage for the travel agency with:

- **HTML**: To structure the content.
- **CSS**: To style and personalize the design.
- **Bootstrap (Optional)**: To create a responsive and modern layout.

### 2. Code Versioning (Optional)
- Use Git to version the project from the start of development.
- Create a public repository on GitHub and organize commits logically.
- The repository should include:
  - All source code.
  - Additional files (e.g., database model images and SQL scripts).

### 3. Database Modeling
Develop the database diagrams for the travel agency:

- **Conceptual**: Representation of entities and their relationships.
- **Logical**: Detailed structure with attributes and relationships.
- **Physical**: Final representation ready for implementation.

#### Tools:
- Use **BRModelo** or equivalent tools (**Excalidraw** and **Mermaid**).
- Generate the SQL script to create tables from the physical diagram.

> **Note**: Integration with the interface is not required at this stage.

---

## Folder Structure
```plaintext
➜  tree
.
├── assets
│   ├── favicon.svg
│   └── logo.svg
├── Database
│   ├── database.sql
├── index.html
├── Pages
│   ├── aboutUs.html
│   ├── contact.html
│   └── destination.html
├── readme.md
└── style
    └── style.css

3 directories, 8 files
```

---

## Images

### Project Preview
<table>
    <thead>
        <tr>
            <th>Version</th>
            <th>Preview</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Desktop Version</td>
            <td><img src="https://github.com/user-attachments/assets/6690fcfe-5820-448d-8b91-034d26ea9bef" alt="Desktop Version"></td>
        </tr>
        <tr>
            <td>Mobile Version</td>
            <td><img src="https://github.com/user-attachments/assets/981f2d6f-3c1c-4f5d-9937-c95d0541bf2b" alt="Mobile Version"></td>
        </tr>
    </tbody>
</table>

### Conceptual Model
![Conceptual Model](https://github.com/user-attachments/assets/3dba2121-b8a3-4cab-9079-f064db0da3ef)

### Logical Model
![Logical Model](https://github.com/user-attachments/assets/c8d1e0b8-7368-4515-be22-5626ba53bcc3)

### Physical Model
```mysql
CREATE TABLE CLIENT (
    ID_CLIENT INT PRIMARY KEY AUTO_INCREMENT,
    client_name VARCHAR(100) NOT NULL,
    client_email VARCHAR(100) UNIQUE NOT NULL,
);

CREATE TABLE DESTINATION (
    ID_DESTINATION INT PRIMARY KEY AUTO_INCREMENT,
    destination_name VARCHAR(100) NOT NULL,
    destination_type ENUM('National', 'International') NOT NULL,
    destination_description TEXT,
    destination_base_price DECIMAL(10,2) NOT NULL
);

CREATE TABLE PACKAGE (
    ID_PACKAGE INT PRIMARY KEY AUTO_INCREMENT,
    package_name VARCHAR(100) NOT NULL,
    package_description TEXT,
    package_price DECIMAL(10,2) NOT NULL,
    package_type ENUM('Promotional', 'Customized') NOT NULL
);

CREATE TABLE RESERVATION (
    ID_RESERVATION INT PRIMARY KEY AUTO_INCREMENT,
    reservation_Date DATE NOT NULL,
    Total_Value DECIMAL(10,2) NOT NULL,
    ID_CLIENT INT NOT NULL,
    ID_PACKAGE INT NOT NULL,
    FOREIGN KEY (ID_CLIENT) REFERENCES CLIENT(ID_CLIENT),
    FOREIGN KEY (ID_PACKAGE) REFERENCES PACKAGE(ID_PACKAGE)
);

CREATE TABLE PACKAGE_DESTINATION (
    ID_PACKAGE INT,
    ID_DESTINATION INT,
    PRIMARY KEY (ID_PACKAGE, ID_DESTINATION),
    FOREIGN KEY (ID_PACKAGE) REFERENCES PACKAGE(ID_PACKAGE),
    FOREIGN KEY (ID_DESTINATION) REFERENCES DESTINATION(ID_DESTINATION)
);

CREATE INDEX idx_reservation_date ON RESERVATION(Reservation_Date);
```

---

## How to Run

1. Clone the repository or extract the files from the compressed folder.
2. Open `index.html` in a web browser to view the homepage.
3. To review the database structure, open the `database.sql` file in any SQL editor.

---

## Video Link
No ferget of add link video later

## Project Link
> See the project in: 
