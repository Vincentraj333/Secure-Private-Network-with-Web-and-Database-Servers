# Secure-Private-Network-with-Web-and-Database-Servers
A simple web application where users can fill a form and upload a file (like a resume). The data gets saved in a MySQL database, and the file is stored on the web server. Everything runs inside a private network of virtual machines (VMs). Virtual Machines Setup (in VirtualBox) You created 3 VMs using Red Hat Linux WebServer1 – Hosts the website (frontend + backend code) DBServer – Hosts the MySQL database BackupServer – Currently unused, reserved for backups later Networking: NAT: For internet access Internal Network: For VM-to-VM communication (private) Web Server Setup (WebServer1) You installed: Apache HTTP Server – to serve web pages PHP – to run backend code Website Files Stored In: css Copy Edit /var/www/html/ Files Created: main.php: A form to submit name, age, country, degree, and upload a PDF index.php: Optional homepage or redirect What it does:

Takes form input

Uploads the file (like a resume)

Saves all details in the database 3. Database Server Setup (DBServer) You installed:

MySQL Server 8.0+

Created Database and Table:

sql Copy Edit CREATE DATABASE udc; USE udc;

CREATE TABLE users ( id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255) NOT NULL, age INT NOT NULL, country VARCHAR(255), degree VARCHAR(100) ); Tested with sample data: Confirmed that records can be inserted and retrieved

SSH Access (PuTTY) You used PuTTY to connect to the VMs over SSH using: IP: 192.168.0.210 (your internal/private IP) Port: 22 User: First logged in as nikhil, then switched to root Through SSH you: Navigated to /var/www/html Uploaded PHP files Verified database and file upload were working

PHP Form & File Upload (main.php) The form you built does the following: Takes user input: Name, Age, Country, Degree Lets users upload a PDF file Saves the data in MySQL (in the users table) Saves the uploaded file on the server Displays a success message Success message shown on submission: User data has been successfully stored in the database. File uploaded successfully.

Final Output Verified You confirmed: Database entries are inserted correctly Files are uploading successfully Apache + PHP are working on WebServer1 MySQL is running and accessible on DBServer A simple multi-VM private web application built with Apache, PHP, and MySQL. Designed in a secure network using VirtualBox and SSH for easy data storage and file upload.
