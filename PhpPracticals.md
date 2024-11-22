# PHP Practical List

## Index Table

| Practical No. | Title                                                                                   |
|---------------|-----------------------------------------------------------------------------------------|
| 1             | [Conditional Structure](#practical-1)                                                 |
| 2             | [Array to Accept and Print Five Values](#practical-2)                                  |
| 3             | [Looping Structure with Functions](#practical-3)                                      |
| 4             | [Type Casting a Variable](#practical-4)                                               |
| 5             | [Multiplication Table](#practical-5)                                                  |
| 6             | [Bubble Sort Function](#practical-6)  

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
} elseif ($marks >= 50) {
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
 
    



