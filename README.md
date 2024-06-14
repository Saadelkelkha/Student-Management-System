# Student-Management-System

**Description:**
The Student Management System is a web-based application built using PHP, MySQL, and jQuery. It allows users to perform CRUD (Create, Read, Update, Delete) operations on student records. The system includes a navigation header for easy access to different pages and utilizes a MySQL database to store student data. Below is a brief overview of the main components and their functionality:

1. **db.php:**
   - Establishes a connection to the MySQL database using PDO.
   ```php
   <?php
   $conn = new PDO("mysql:host=localhost;dbname=mydb", "root", "123");
   ?>
   ```

2. **header.php:**
   <img src="img\header.png" width="100%">
   - Contains the navigation menu for the application, providing links to the home page and the create student page.
   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
   </head>
   <body>
       <nav style="display:flex;text-decoration:none;flex-direction:row;justify-content: center;background-color:black;padding-right:2%;width:100%">
           <ul style="list-style-type:none;display:flex;align-content: center;width:100%;color:white;gap:15%">
               <li><a href="index.php" style="text-decoration:none;color:white;">Home</a></li>
               <li><a href="create.php" style="text-decoration:none;color:white;">Create a student</a></li>
           </ul>
       </nav>
   </body>
   </html>
   ```

4. **index.php:**
   - Displays a table of all students in the database with options to edit or delete each record.
  <img src="img\index.png" width="100%">

6. **create.php:**
   - Provides a form to add a new student to the database.
    <img src="img\add.png" width="100%">

8. **edit.php:**
   - Allows editing of an existing student's information.
   <img src="img\modify.png" width="100%">

10. **delete.php:**
   - Deletes a student record from the database based on the ID.
   ```php
   <?php
       require_once "db.php";
       $id = $_GET['id'];
       $query = $conn->prepare('DELETE FROM etudiant WHERE ID=?');
       $exe = $query->execute([$id]);
       header('location: index.php');
   ?>
   ```

This system provides a simple interface for managing student records, demonstrating basic database interactions and web development practices using PHP and MySQL.
