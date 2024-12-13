# 1. What is the name of scripting engine in PHP

_**Zend Engine**_

# 2. Features of PHP (in simple terms):

**Easy to Learn and Use** - PHP has a simple syntax, making it beginner-friendly.

**Open Source** - It's free to download and use, with a large supportive community.

**Server-Side Scripting** - PHP runs on the server, generating dynamic web pages before sending them to your browser.

**Cross-Platform** - It works on different operating systems like Windows, macOS, and Linux.

**Database Integration** - PHP easily connects to databases like MySQL, helping build websites with dynamic content.

**Fast Performance** - PHP scripts execute quickly, improving website speed.

**Built-In Functions** - It comes with many ready-to-use functions for file handling, string manipulation, and more.

**Customizable** - You can embed PHP in HTML, making it flexible for web design.

**Secure** - PHP has tools to build secure web applications by handling encryption, authentication, and data validation.

**Widely Used** - Big platforms like WordPress and Facebook use PHP, making it a trusted choice for developers.


# 3. $_SESSION in PHP:

`$_SESSION` is a **superglobal variable** in PHP used to store data across multiple pages during a user's visit to a website. A PHP session is used to store data on a server rather than the computer of the user.

A "session" in web development is used to maintain user information across multiple pages within a website


 **Example:**
   ```php
   <?php
   // Start the session
   session_start();

   // Store data in the session
   $_SESSION['username'] = 'Alice';
   $_SESSION['loggedIn'] = true;

   // Access session data
   echo "Welcome, " . $_SESSION['username'];
   ?>
   ```



# 4. what is PEAR?

PEAR means **PHP Extension and Application Repository**

# 5. Rules for naming php variable

- A variable starts with the $ sign, followed by the name of the variable
- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive ($age and $AGE are two different variables)

# 6. 










# $ vs $$ in php.
or
# Difference between $_message and $$_message.

The **$\_message** (single dollar) is a normal variable with the name \_message that stores any value like string, integer, float, etc.

The **$$\_message** (double dollar) is a reference variable that stores the value of anoher variable inside it.

```php
<?php
$name = "Ankita";
$her_name = "name";

echo $her_name . "<br>";
echo $$her_name . "<br>";

// another example
$var = "Hello"; 
$Hello = "GeeksforGeeks"; 

echo $var . "<br>"; 
echo $$var; 

/* OUTPUT =  
name
Ankita
Hello
GeeksforGeeks
*/
?>
```

# sort

```php
$cars = array("Volvo", "BMW", "Toyota");
sort($cars);

// reverse sort
rsort($cars);
```

# connection using PDO

```php
<?php
try{
$servername = "localhost";
$username = "username";
$password = "password";

$conn = new PDO("mysql:host=$servername;dbname=myDB", $username, $password);
echo "connection successful"
}
catch (PDOException $e) {
    echo "Database not connected: " . $e->getMessage();
}
?>
```

# connection using musqli

```php
<?php
$server = "localhost";
$user = "root";
$password = "";
$db = "testdb";
$conn = "";

$conn = mysqli_connect($server, $user, $password, $db);

if(!$conn){
    echo "database not connected";
}
else{
    echo "connection successful";
}
?>
```