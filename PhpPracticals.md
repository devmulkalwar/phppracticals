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
$color = array("green", "red", "yellow",”blue”,”black”); 
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
<html>
<head> 
<title> Function using Looping Structure </title> 
</head> 
<body> 
<?php 
function table($n)
{
   for($i=1;$i<=10; $i++)
    {
         echo “$n*$i=”.$n*$n*$i.”<br>”;
     }
}
  table(5);
?>
</html>
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

```html
HTML File: - 
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
PHP File: - 
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
```
### Session 2:
```html
</html>
<!DOCTYPE html> 
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
