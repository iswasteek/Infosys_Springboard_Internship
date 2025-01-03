# Sports Performance Monitoring and Event Management Platform

This project streamlines sports management by integrating performance monitoring, user role management, and event organization into a unified platform.

---

## Usage Scenarios

1. **For Athletes**:

   - Log in to view your personal profile.
   - Check metrics like training progress, assigned coach, and event participation.

2. **For Coaches**:

   - Manage athlete training schedules and performance data.
   - Organize team practice sessions.

3. **For Administrators**:
   - Monitor system-wide performance.
   - Manage user accounts, including coaches and athletes.
   - Oversee the creation and execution of sports events.

---

## Getting Started

Follow the steps below to download, set up, and run the project for the first time.

### Prerequisites

Ensure the following tools are installed on your system:

1. **Git**: [Download Git](https://git-scm.com/)
2. **Java Development Kit (JDK)**: Version 8 or above [Download JDK](https://www.oracle.com/java/technologies/javase-jdk-downloads.html)
3. **IntelliJ IDEA**: [Download IntelliJ IDEA](https://www.jetbrains.com/idea/download/)
4. **MySQL Community Server & MySQL Workbench**: Version 8.0 or above [Download MySQL](https://dev.mysql.com/downloads/)
5. **Node.js**: Version 14 or above [Download Node.js](https://nodejs.org/)
6. **Postman**: [Download Postman](https://www.postman.com/)

---

## Step-by-Step Setup

### Step 1: Clone the Project Repository

1. Open IntelliJ IDEA.
2. Select **Get from VCS** on the Welcome Screen.
3. Paste the Git repository URL into the URL field.
4. Click **Clone** and load Maven dependencies.

### Step 2: Configure the Backend

1. Navigate to the `application.properties` file in the backend directory.
2. Update the database configuration:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/auth
   spring.datasource.username=<your-username>
   spring.datasource.password=<your-password>
   spring.jpa.hibernate.ddl-auto=update
   Replace <your-username> and <your-password> with your MySQL credential
   ```

### Step 3: Run the Backend Server

Click the Run button in IntelliJ IDEA.

Verify that the server starts at http://localhost:8080.

Insert roles into the roles table:
INSERT INTO roles (id, name) VALUES  
(1, 'ADMIN'),  
(2, 'COACH'),  
(3, 'ATHLETE');

### Step 4: View the Frontend Pages

Open the frontend directory.
Locate the starting HTML file, e.g., welcome.html.
Open the file in your browser.

### Step 5: Test the API Endpoints

Login API:
POST http://localhost:8080/api/auth/login  
Body:  
{  
 "email": "testemail",  
 "password": "testpassword"  
}

Registration API:

POST http://localhost:8080/api/auth/register  
Body:  
{  
 "name": "your name",  
 "email": "user email",  
 "password": "newpassword",  
 "role": "select role"  
}

### Troubleshooting Common Issues

Backend Server Fails to Start:

Verify database credentials in application.properties.
Ensure MySQL Server is running.
Frontend Pages Not Loading:

Verify Node.js installation.
Ensure the backend server is running.
API Calls Failing in Postman:

Check if the backend server is running at http://localhost:8080.
Include the JWT token in the Authorization header.

### Contributing

Fork the repository.
Create a new branch:
git checkout -b feature/<feature-name>  
Commit and push your changes.
Submit a pull request for review.

### Table Scripts

-- Create 'user' table
CREATE TABLE user (
id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(100) NOT NULL,
email VARCHAR(100) UNIQUE NOT NULL,
password VARCHAR(255) NOT NULL
);

-- Create 'roles' table
CREATE TABLE roles (
id INT AUTO_INCREMENT PRIMARY KEY,
name ENUM('ADMIN', 'COACH', 'ATHLETE') NOT NULL
);

-- Create 'user_roles' table
CREATE TABLE user_roles (
id INT AUTO_INCREMENT PRIMARY KEY,
user_id INT NOT NULL,
roles_id INT NOT NULL,
FOREIGN KEY (user_id) REFERENCES user (id) ON DELETE CASCADE,
FOREIGN KEY (roles_id) REFERENCES roles (id) ON DELETE CASCADE
);

-- Create 'events' table
CREATE TABLE events (
id INT AUTO_INCREMENT PRIMARY KEY,
category VARCHAR(50) NOT NULL,
event_date DATE NOT NULL,
event_name VARCHAR(100) NOT NULL,
image_link VARCHAR(255),
meet VARCHAR(255)
);

-- Create 'registrations' table
CREATE TABLE registrations (
id INT AUTO_INCREMENT PRIMARY KEY,
event_id INT NOT NULL,
user_id INT NOT NULL,
FOREIGN KEY (event_id) REFERENCES events (id) ON DELETE CASCADE,
FOREIGN KEY (user_id) REFERENCES user (id) ON DELETE CASCADE
);

-- Insert default roles
INSERT INTO roles (id, name) VALUES
(1, 'ADMIN'),
(2, 'COACH'),
(3, 'ATHLETE');

### How to Use:

Execute these scripts in MySQL Workbench or any MySQL client.
Ensure the auth database exists before running these scripts, or create it using:
CREATE DATABASE auth;
USE auth;

## Conclusion

The **Sports Performance Monitoring and Event Management Platform** is designed to simplify the complex workflows involved in sports management by integrating performance tracking, event scheduling, and user role management into one cohesive platform. With its secure role-based access control, user-friendly interface, and powerful backend, this project empowers athletes, coaches, and administrators to focus on what matters most—improving sports performance.

We welcome contributions to enhance the platform further. If you have any feedback or suggestions, feel free to submit a pull request or create an issue in the repository. Thank you for exploring this project!

---

**Contact Information**  
If you encounter any issues or have questions about the project, please feel free to reach out:

- **GitHub**: [GitHub Profile](https://github.com/iswasteek)
- **LinkedIn**: [LinkedIn Profile](https://www.linkedin.com/in/swastikk/)

We hope this platform helps you streamline sports management and achieve your goals! 🎉
