Here is a step-by-step example of how to create a database Student with a collection example, insert two documents related to shapes, and perform the requested operations.


---

1. Create Database and Collection

Switch to the Student database:

use Student

Insert two documents into the example collection:

db.example.insertMany([
    { name: "Circle", sides: 0, radius: 10, area: 314.16 },
    { name: "Square", sides: 4, sideLength: 5, area: 25 }
]);


---

2. Perform Operations

a. $cmp

Compare the area of the two shapes:

db.example.aggregate([
    {
        $project: {
            name: 1,
            areaComparison: { $cmp: ["$area", 100] }
        }
    }
]);

Result Explanation:

0 if the area is equal to 100.

1 if the area is greater than 100.

-1 if the area is less than 100.



---

b. $gt (Greater Than)

Find shapes with an area greater than 100:

db.example.find({ area: { $gt: 100 } });

Result: Only the Circle document will match.


---

c. $lt (Less Than)

Find shapes with an area less than 100:

db.example.find({ area: { $lt: 100 } });

Result: Only the Square document will match.


---

d. $eq (Equal To)

Find shapes with exactly 4 sides:

db.example.find({ sides: { $eq: 4 } });

Result: Only the Square document will match.


---

e. $lte (Less Than or Equal To)

Find shapes with sides less than or equal to 4:

db.example.find({ sides: { $lte: 4 } });

Result: Both documents will match, as Circle has 0 sides and Square has 4 sides.


---

f. $gte (Greater Than or Equal To)

Find shapes with an area greater than or equal to 25:

db.example.find({ area: { $gte: 25 } });

Result: Both documents will match, as Circle has an area of 314.16 and Square has an area of 25.


---

Full Example Output

Documents:

[
    { _id: ObjectId("..."), name: "Circle", sides: 0, radius: 10, area: 314.16 },
    { _id: ObjectId("..."), name: "Square", sides: 4, sideLength: 5, area: 25 }
]

Results:

1. $cmp: Compares area with 100.

[
    { "_id": 1, "name": "Circle", "areaComparison": 1 },
    { "_id": 2, "name": "Square", "areaComparison": -1 }
]


2. $gt: Returns Circle.


3. $lt: Returns Square.


4. $eq: Returns Square (4 sides).


5. $lte: Returns both Circle and Square.


6. $gte: Returns both Circle and Square.



Let me know if you need help with further operations!

