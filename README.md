<!DOCTYPE html>
<html>
<head>
    <title>Sports Performance Monitoring and Event Management Platform</title>
    <style>
        h2, h3 {
            color: #2c3e50;
        }
        ul {
            list-style-type: square;
        }
        code {
            background-color: #f4f4f4;
            padding: 2px 4px;
            border-radius: 4px;
            font-family: monospace;
        }
        pre {
            background-color: #f4f4f4;
            padding: 10px;
            border-radius: 4px;
            overflow: auto;
        }
    </style>
</head>
<body>
    <h2>Sports Performance Monitoring and Event Management Platform</h2>

    <p>This project is designed to streamline sports management by integrating performance monitoring, user role management, and event organization into a unified platform. It provides functionalities tailored for athletes, coaches, and administrators, enabling them to manage their respective responsibilities efficiently.</p>

    <hr>

    <h3>Project Overview</h3>
    <h4>Purpose</h4>
    <p>The platform is built to cater to the unique needs of sports teams and organizations, providing tools to:</p>
    <ul>
        <li>Monitor Athlete Performance: Track key metrics like height, weight, category, and coach assignments.</li>
        <li>Event Management: Organize, schedule, and oversee sports events and training sessions.</li>
        <li>User Management: Role-based access for athletes, coaches, and administrators to ensure secure and seamless operations.</li>
    </ul>

    <h4>Technologies Used</h4>
    <h5>Backend</h5>
    <ul>
        <li>Spring Boot Framework: Simplifies application development with built-in configurations.</li>
        <li>MySQL Database: Efficiently stores user and performance data.</li>
        <li>Spring Security & JWT: Ensures secure authentication and authorization.</li>
    </ul>
    <h5>Frontend</h5>
    <ul>
        <li>HTML, CSS, and JavaScript: Creates a responsive and user-friendly interface.</li>
        <li>Bootstrap: Utilizes its grid system and ready-made components for faster development and responsive layouts.</li>
    </ul>
    <h5>Testing Tools</h5>
    <ul>
        <li>Postman: Used for API testing and ensuring endpoints work as expected.</li>
    </ul>

    <hr>

    <h3>Features</h3>
    <ul>
        <li><b>Role-Based Access Control:</b>
            <ul>
                <li>Athletes: View and update performance metrics.</li>
                <li>Coaches: Manage athlete data and schedules.</li>
                <li>Administrators: Oversee user roles and organize events.</li>
            </ul>
        </li>
        <li><b>Database Automation:</b> The database is auto-configured when the application runs, eliminating manual setup.</li>
        <li><b>User Authentication:</b> Login and registration endpoints validate users and assign roles securely.</li>
        <li><b>Frontend Navigation:</b> A browser-based interface for ease of use.</li>
        <li><b>Event Scheduling:</b> Administrators can create, modify, and delete sports events.</li>
    </ul>

    <hr>

    <h3>Restricting Admin Registration</h3>
    <ol>
        <li>After registering an admin through the application, open the <code>register.html</code> file located in the frontend directory.</li>
        <li>Locate the dropdown section in the HTML code where user roles are listed.</li>
        <li>Comment out the option for "Admin" by modifying the dropdown code as shown below:</li>
    </ol>
    <pre>
    &lt;select id="role" name="role"&gt;
        &lt;option value="ATHLETE"&gt;Athlete&lt;/option&gt;
        &lt;option value="COACH"&gt;Coach&lt;/option&gt;
        &lt;!-- &lt;option value="ADMIN"&gt;Admin&lt;/option&gt; --&gt;
    &lt;/select&gt;
    </pre>

    <hr>

    <h3>Usage Scenarios</h3>
    <ul>
        <li><b>For Athletes:</b>
            <ul>
                <li>Log in to view your personal profile.</li>
                <li>Check metrics like training progress, assigned coach, and event participation.</li>
            </ul>
        </li>
        <li><b>For Coaches:</b>
            <ul>
                <li>Manage athlete training schedules and performance data.</li>
                <li>Organize team practice sessions.</li>
            </ul>
        </li>
        <li><b>For Administrators:</b>
            <ul>
                <li>Monitor system-wide performance.</li>
                <li>Manage user accounts, including coaches and athletes.</li>
                <li>Oversee the creation and execution of sports events.</li>
            </ul>
        </li>
    </ul>

    <hr>

    <h3>Getting Started</h3>
    <h4>Prerequisites</h4>
    <ul>
        <li><b>Git:</b> Download from <a href="https://git-scm.com">Git Official Site</a>.</li>
        <li><b>Java Development Kit (JDK):</b> Version 8 or above from <a href="https://www.oracle.com/java/technologies/javase-downloads.html">Oracle JDK Downloads</a>.</li>
        <li><b>IntelliJ IDEA:</b> Download from <a href="https://www.jetbrains.com/idea/download">JetBrains IntelliJ IDEA Download</a>.</li>
        <li><b>MySQL:</b> Version 8.0 or above from <a href="https://dev.mysql.com/downloads">MySQL Downloads</a>.</li>
        <li><b>Node.js:</b> Version 14 or above from <a href="https://nodejs.org">Node.js Official Site</a>.</li>
        <li><b>Postman:</b> Download from <a href="https://www.postman.com/downloads">Postman Downloads</a>.</li>
    </ul>

    <h4>Step-by-Step Setup</h4>
    <ol>
        <li>Clone the project repository using IntelliJ IDEA.</li>
        <li>Configure the backend by editing the <code>application.properties</code> file.</li>
        <li>Run the backend server and verify database setup.</li>
        <li>View the frontend pages and explore the application features.</li>
        <li>Test API endpoints using Postman.</li>
    </ol>

    <h4>Testing API Endpoints</h4>
    <p><b>Login API:</b></p>
    <pre>
    Request Type: POST
    Endpoint URL: http://localhost:8080/api/auth/login
    Body (JSON):
    {
        "email": "testemail",
        "password": "testpassword"
    }
    </pre>
    <p><b>Registration API:</b></p>
    <pre>
    Request Type: POST
    Endpoint URL: http://localhost:8080/api/auth/register
    Body (JSON):
    {
        "name": "your name",
        "email": "user email",
        "password": "newpassword",
        "role": "select role"
    }
    </pre>

    <hr>

    <h3>Contributing</h3>
    <ol>
        <li>Fork the repository.</li>
        <li>Create a new branch: <code>git checkout -b feature/<feature-name></code></li>
        <li>Commit and push your changes.</li>
        <li>Submit a pull request for review.</li>
    </ol>

</body>
</html>
