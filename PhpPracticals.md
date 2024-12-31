# PHP Practical List

## Index Table

| Practical No. | Title                                           |
|---------------|-------------------------------------------------|
| 1             | [Practical 1](#practical-1)                    |
| 2             | [Practical 2](#practical-2)                    |
| 3             | [Practical 3](#practical-3)                    |
| 4             | [Practical 4](#practical-4)                    |
| 5             | [Practical 5](#practical-5)                    |
| 6             | [Practical 6](#practical-6)                    |
| 7             | [Practical 7](#practical-7)                    |
| 8             | [Practical 8](#practical-8)                    |
| 9             | [Practical 9](#practical-9)                    |
| 10            | [Practical 10](#practical-10)                  |
| 11            | [Practical 11](#practical-11)                  |
| 12            | [Practical 12](#practical-12)                  |
| 13            | [Practical 13](#practical-13)                  |
| 14            | [Practical 14](#practical-14)                  |
| 15            | [Practical 15](#practical-15)                  |                  |

# Practical 1:	
## Write a program using Conditional Structure. 

```html
<!DOCTYPE html>
<html>
<body>
<?php 
$marks = 75;

if ($marks > 79) {
    echo "Grade: A";
} elseif ($marks > 60) {
    echo "Grade: B";
} elseif ($marks > 50) {
    echo "Grade: C";
} elseif ($marks == 50) {
    echo "Grade: D";
} else {
    echo "Grade: F";
}
?>
</body>
</html>
```
---

# Practical 2:	 
## Write a program using array which accepts five values and print the values. 

```html
<!DOCTYPE html>
<html>  
<head> 
<title>Array Values</title> 
</head> 
<body> 
<?php 
$color = array("green", "red", "yellow","blue","black"); 
foreach ($color as $value) 
{ 
echo "$value <br>"; 
} 
?> 
</body> 
</html> 

```
---

# Practical 3:	 
## Write a program using Looping Structure with concept of Functions. 

```html
<!DOCTYPE html> 
<head> 
<title> Function using Looping Structure </title> 
</head> 
<body> 
<?php 
function table($n)
{
   for($i=1;$i<=10; $i++)
    {
         echo "$n*$i=".($n*$i)."<br>";
     }
}
  table(5);
?>
```
---

# Practical 4: 
## Write a Program for type casting a variable.

```html
<!DOCTYPE html>
<html lang="en">
<body>
    <?php
    $a = 12.5;
    echo "The Float Value : $a <br>";
    $k = (int)$a;
    echo "Converting into int Value : $k <br>";
    $k = (string)$a;
    echo "Converting into String Value : $k <br>";
    ?>
</body>
</html>
```

# Practical 5:  
## Write a program in PHP to display Multiplication Table using nested for loop. 

```html
<!DOCTYPE html>
<html>
<head> 
<title>Multiplication Table</title> 
</head> 
<body> 
<?php 
// PHP program to display multiplication table 
// Define the range of the multiplication table 
$start = 1; 
$end = 10; 
// Display the multiplication table using nested for loops 
for ($i = $start; $i <= $end; $i++)
 { 
for ($j = 1; $j <= 10; $j++) 
{ 
$result = $i * $j; 
echo "$i x $j = $result\n"; 
} 
echo "\n"; // Add a newline after each row for better readability 
} 
?> 
</body> 
</html>
```
---

# Practical 6:	
## Write a program In PHP to Sort an array using Bubble Sort function.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Bubble Sort Function</title>
</head>
<body>
<?php
// PHP program to sort an array using Bubble Sort
function bubbleSort(&$arr) {
    $n = count($arr);
    for ($i = 0; $i < $n - 1; $i++) {
        for ($j = 0; $j < $n - $i - 1; $j++) {
            if ($arr[$j] > $arr[$j + 1]) {
                // Swap elements if they are in the wrong order
                $temp = $arr[$j];
                $arr[$j] = $arr[$j + 1];
                $arr[$j + 1] = $temp;
            }
        }
    }
}

// Example usage
$arrayToSort = [64, 34, 25, 12, 22, 11, 90];

echo "Original Array: " . implode(", ", $arrayToSort) . "<br>";

// Call the bubbleSort function to sort the array
bubbleSort($arrayToSort);

echo "Sorted Array: " . implode(", ", $arrayToSort) . "<br>";
?>
</body>
</html>
```
---
# Practical 7:	
## Design the personal information form, submit and retrieve the form data using php $_POST, $_GET, $ REQUEST variable.  

### HTML File:
```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Personal Information Form</title> 
</head> 
<body> 
<h2>Personal Information Form</h2> 
<form action="process_form.php" method="post"> 
<label for="name">Name:</label> 
<input type="text" name="name" required><br> 
<label for="email">Email:</label> 
<input type="email" name="email" required><br> 
<label for="age">Age:</label> 
<input type="number" name="age" required><br> 
<input type="submit" value="Submit"> 
</form> 
</body> 
</html>
```

### PHP File:
```html
<!DOCTYPE html> 
<head> 
<title>Process Form</title> 
</head> 
<body> 
<?php 
// PHP code to process the form data 
if ($_SERVER["REQUEST_METHOD"] == "POST") { 
// Using $_POST to retrieve form data 
$name = $_POST["name"]; 
$email = $_POST["email"]; 


$age = $_POST["age"]; 
// Displaying the submitted data 
echo "<h2>Submitted Data using \$_POST:</h2>"; 
echo "Name: $name<br>"; 
echo "Email: $email<br>"; 
echo "Age: $age<br>"; 
} 
// Using $_GET to retrieve form data 
if (isset($_GET["name"]) && isset($_GET["email"]) && isset($_GET["age"])) { 
$name_get = $_GET["name"]; 
$email_get = $_GET["email"]; 
$age_get = $_GET["age"]; 
// Displaying the submitted data 
echo "<h2>Submitted Data using \$_GET:</h2>"; 
echo "Name: $name_get<br>"; 
echo "Email: $email_get<br>"; 
echo "Age: $age_get<br>"; 
} 
// Using $_REQUEST to retrieve form data 
if (isset($_REQUEST["name"]) && isset($_REQUEST["email"]) && isset($_REQUEST["age"])) { 
$name_request = $_REQUEST["name"]; 
$email_request = $_REQUEST["email"]; 
$age_request = $_REQUEST["age"]; 
// Displaying the submitted data 
echo "<h2>Submitted Data using \$_REQUEST:</h2>"; 
echo "Name: $name_request<br>"; 
echo "Email: $email_request<br>"; 
echo "Age: $age_request<br>"; 
} 
?> 
</body> 
</html>
```
---
# Practical 8:
## Study of Cookies and Session in PHP.

### Session 1:
```html
<!DOCTYPE html>
<html>
<head> 
<title>Session 1</title> 
</head> 
<body> 
<?php 
// Setting a cookie 
$cookie_name = "user"; 
$cookie_value = "John Doe"; 
setcookie($cookie_name, $cookie_value, time() + (86400 * 30), "/"); // Cookie will expire in 30 days 
// Retrieving and displaying cookie value 
if (isset($_COOKIE[$cookie_name])) { 
echo "Cookie '" . $cookie_name . "' has the value: " . $_COOKIE[$cookie_name]; 
} else { 
echo "Cookie named '" . $cookie_name . "' is not set."; 
} 
?> 
</body>
</html>
```
### Session 2:
```html
<!DOCTYPE html>
<html>
<head> 
<title>Session 2</title> 
</head> 
<body> 
<?php 
// Starting a session 
session_start(); 
// Setting session variables 
$_SESSION["username"] = "JohnDoe"; 
$_SESSION["user_id"] = 123; 
// Retrieving and displaying session variables 
echo "Username: " . $_SESSION["username"] . "<br>"; 
echo "User ID: " . $_SESSION["user_id"] . "<br>"; 
// Destroying the session 
session_destroy(); 
?> 
</body> 
</html>
```
---
# Practical 9:
## Study of MySQL DDL, DML, DCL Commands.

### DDL
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Database Table Create</title>
</head>
<body>
<?php
// DDL Example: Creating a Table
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "KumarDatabase";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$sql = "CREATE TABLE users (
    id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(30) NOT NULL,
    email VARCHAR(50) NOT NULL,
    reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
)";

if ($conn->query($sql) === TRUE) {
    echo "Table created successfully";
} else {
    echo "Error creating table: " . $conn->error;
}

$conn->close();
?>
</body>
</html>
``` 
### DML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Insert Data in DataBase</title>
</head>
<body>
<?php
// DML Example: Inserting Data
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "Kumardatabase";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$sql = "INSERT INTO users (username, email)
        VALUES ('john_doe', 'john@example.com')";

if ($conn->query($sql) === TRUE) {
    echo "Data inserted successfully";
} else {
    echo "Error inserting data: " . $conn->error;
}

$conn->close();
?>
</body>
</html>
```

### DCL
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grant Privileges</title>
</head>
<body>
<?php
// DCL Example: Granting Privileges
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "Kumardatabase";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

$sql = "GRANT SELECT, INSERT, UPDATE, DELETE ON Kumardatabase.users TO 'new_user'@'localhost'";

if ($conn->query($sql) === TRUE) {
    echo "Privileges granted successfully";
} else {
    echo "Error granting privileges: " . $conn->error;
}

$conn->close();
?>
</body>
</html>
```
---

# Practical 10:	
## Design Login Form and Validate that form using PHP Code.

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Validate Login Form</title>
</head>
<body>
<h2>Login Form</h2>
<form action="p8Validate.php" method="post">
<label for="username">Username:</label>
<input type="text" name="username" required><br>
<label for="password">Password:</label>
<input type="password" name="password" required><br>
<input type="submit" value="Login">
</form>
</body>
</html>
```
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Validate Login</title>
</head>
<body>
<?php
// PHP code to validate the login form
if ($_SERVER["REQUEST_METHOD"] == "POST") {
// Get form data
$username = $_POST["username"];
$password = $_POST["password"];
// Hard-coded username and password for demonstration purposes
$valid_username = "user123";
$valid_password = "password123";
// Validate the login credentials
if ($username == $valid_username && $password == $valid_password) {
echo "Login successful! Welcome, $username.";
} else {
echo "Invalid username or password. Please try again."; 
}
} else {
header("C:\xampp\htdocs\pra\p8.php");
exit();
}
?>
</body>
</html> 
```
---

# Practical 11:	
## Write a PHP code to create database & table in Mysql 

```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Database Create</title> 
</head> 
<body> 
<?php 
// DDL Example: Creating a Table 
$servername = "localhost"; 
$username = "root"; 
$password = ""; 
$dbname = "RGI";
$conn = new mysqli($servername, $username, $password, $dbname); 
if ($conn->connect_error) { 
die("Connection failed: " . $conn->connect_error); 
} 
$sql = "CREATE TABLE student ( 
id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, 
username VARCHAR(30) NOT NULL, 
email VARCHAR(50) NOT NULL, 
reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP 
)"; 
if ($conn->query($sql) === TRUE) { 
echo "Table created successfully"; 
} else { 
echo "Error creating table: " . $conn->error; 
} $conn->close(); 
?> 
</body>
</html>
```
---

# Practical 12:	
## Write a PHP code to insert ,delete,select the data from database 

```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Database- Insert, Delete</title> 
</head> 
<body> 
<?php 
// Database connection parameters 
$servername = "localhost"; 
$username = "root"; 
$password = ""; 
$database = "Kumardatabase"; 
$conn = new mysqli($servername, $username, $password, $database); 
if ($conn->connect_error) { 
die("Connection failed: " . $conn->connect_error); 
} 
$insertSql = "INSERT INTO users (username, email) VALUES ('john_doe', 'john@example.com')"; 
if ($conn->query($insertSql) === TRUE) { 
echo "Data inserted successfully.<br>"; 
} else { 
echo "Error inserting data: " . $conn->error . "<br>"; 
} 
// Delete data from the database 
$deleteSql = "DELETE FROM users WHERE username='john_doe'"; 
if ($conn->query($deleteSql) === TRUE) { 
echo "Data deleted successfully.<br>"; 
} else { 
echo "Error deleting data: " . $conn->error . "<br>"; 
} 
// Select data from the database 
$selectSql = "SELECT * FROM users"; 
$result = $conn->query($selectSql); 
if ($result->num_rows > 0) { 
echo "<h2>Users:</h2>"; 
while ($row = $result->fetch_assoc()) { 
echo "ID: " . $row["id"] . " - Username: " . $row["username"] . " - Email: " . $row["email"] . "<br>"; 
} 
} else { 
echo "No users found.<br>"; 
} 
// Close the database connection 
$conn->close(); 
?> 
</body> 
</html>
```
---

# Practical 13:	
## Design a from which upload & Display image in PHP 

```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Image Upload Form</title> 
</head> 
<body> 
<h2>Image Upload Form</h2> 
<form action="upload_image.php" method="post" enctype="multipart/form-data"> 
<label for="image">Select Image:</label> 
<input type="file" name="image" accept="image/*" required><br> 
<input type="submit" value="Upload Image"> 
</form> 
</body> 
</html>
```

```html
<!DOCTYPE html> 
<head> 
<title>Uploed Image</title> 
</head> 
<body> 
<?php 
if ($_SERVER["REQUEST_METHOD"] == "POST") { 
if (isset($_FILES["image"])) { 
$uploadDir = "C:\Users\kumar\Pictures\Camera Roll"; // Directory to store uploaded images 
$fileName = $_FILES["image"]["name"]; 
$fileTmpName = $_FILES["image"]["tmp_name"]; 
$fileType = $_FILES["image"]["type"]; 
$fileSize = $_FILES["image"]["size"]; 
$fileError = $_FILES["image"]["error"]; 
$uniqueFileName = uniqid() . "_" . $fileName; 
if (move_uploaded_file($fileTmpName, $uploadDir . $uniqueFileName)) { 
echo "Image uploaded successfully.<br>"; 
echo "<h2>Uploaded Image:</h2>"; 
echo "<img src='$uploadDir$uniqueFileName' alt='Uploaded Image'>"; 
} else { 
echo "Error uploading image: " . $fileError; 
} 
} else { 
echo "No file selected."; 
} 
} else { 
header("C:\xampp\htdocs\MCA PHP Practicals\Practical_13\image_upload_form.html"); 
exit(); 
}?>
</body>
</html>
```
---

# Practical 14:	
## Write a PHP Code to make database connection, Create Data Base, Create Table In Mysql.

```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Database & Table Create</title> 
</head> 
<body> 
<?php 
$hostname = "localhost"; 
$username = "root"; 
$password = ""; 
$conn = new mysqli($hostname, $username, $password); 
if ($conn->connect_error) { 
die("Connection failed: " . $conn->connect_error); 
} 
$databaseName = "exampledatabase"; 
$createDatabaseSql = "CREATE DATABASE IF NOT EXISTS $databaseName"; 
if ($conn->query($createDatabaseSql) === TRUE) { 
echo "Database created successfully.<br>"; 
} else { 
echo "Error creating database: " . $conn->error . "<br>"; 
} 
$conn->select_db($databaseName); 
$createTableSql = "CREATE TABLE IF NOT EXISTS users ( 
id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, 
username VARCHAR(30) NOT NULL, 
email VARCHAR(50) NOT NULL, 
reg_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP 
)"; 
if ($conn->query($createTableSql) === TRUE) { 
echo "Table created successfully.<br>"; 
} else { 
echo "Error creating table: " . $conn->error . "<br>"; } 
$conn->close(); 
?> 
</body> 
</html>
```
---

# Practical 15:	
## Write a PHP code Insert, Delete, Update, Select the Data From Database.

```html
<!DOCTYPE html> 
<html lang="en"> 
<head> 
<meta charset="UTF-8"> 
<meta name="viewport" content="width=device-width, initial-scale=1.0"> 
<title>Database - Insert , Update, Delete</title> 
</head> 
<body> 
<?php 
// Database connection parameters 
$hostname = "localhost"; 
$username = "root"; 
$password = ""; 
$database = "exampledatabase"; 
// Create a connection to MySQL 
$conn = new mysqli($hostname, $username, $password, $database); 
// Check connection 
if ($conn->connect_error) { 
die("Connection failed: " . $conn->connect_error); 
} 
$insertSql = "INSERT INTO users (username, email) VALUES ('john_doe', 'john@example.com')"; 
if ($conn->query($insertSql) === TRUE) { 
echo "Data inserted successfully.<br>"; 
} else { 
echo "Error inserting data: " . $conn->error . "<br>"; 
} 
// Update data in the table 
$updateSql = "UPDATE users SET email='john_updated@example.com' WHERE username='john_doe'"; 
if ($conn->query($updateSql) === TRUE) { 
echo "Data updated successfully.<br>"; 
} else { 
echo "Error updating data: " . $conn->error . "<br>"; 
} 
// Delete data from the table 
$deleteSql = "DELETE FROM users WHERE username='john_doe'"; 
if ($conn->query($deleteSql) === TRUE) { 
echo "Data deleted successfully.<br>"; 
} else { 
echo "Error deleting data: " . $conn->error . "<br>"; 
} 
// Select data from the table 
$selectSql = "SELECT * FROM users"; 
$result = $conn->query($selectSql); 
if ($result->num_rows > 0) { 
echo "<h2>Users:</h2>"; 
while ($row = $result->fetch_assoc()) { 
echo "ID: " . $row["id"] . " - Username: " . $row["username"] . " - Email: " . $row["email"] . "<br>"; 
} 
} else { 
echo "No users found.<br>"; 
} 
// Close the database connection 
$conn->close(); 
?> 
</body> 
</html> 
```
---
