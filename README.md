##PDO Function for PHP
This function allows users in PHP to interface with mySQL databases using the PDO library which has the benefit of allowing prepared statements to avoid the potential exploit of a sql injection attack. This is particularly useful when running frontend web applications. 

###Sample Use
Select statement returned in an associative array. One value is then echoed. 
```php
$return = sqlQuery($connection, "SELECT * FROM my_users;");
echo $return[0]['username']
```
Select statement returns an associative array with one argument. All results are then printed out.
```php
$returntwo = sqlQuery($connection, "SELECT * FROM prepared WHERE name = ?;", array("nick"));
foreach ($returntwo as $key => $value) {
	echo $value['age']."<br />";
}
```
Insert statement does not return any useful data, it is just executed. In this example there are multiple arguments.
```php
sqlQuery($connection, "INSERT INTO prepared (name,age) VALUES (?,?)", array("Jane", 18));
```

###Installation
1) Download sqlQuery.php and place it in your project directory.

2) Require the file in your project.
```php
require_once("sqlQuery.php");
```
3) Use as directed above.

###Author
Nicholas Elder 

###Contact
baffu (at) stormcraft (dot) ca

###Licence
The MIT License (MIT)

Copyright (c) 2015 Nicholas Elder

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.