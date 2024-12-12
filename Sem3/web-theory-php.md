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


# 3. `$_SESSION` in PHP:

`$_SESSION` is a **superglobal variable** in PHP used to store data across multiple pages during a user's visit to a website. 

### Key Points:
1. **What It Does**  
   - It keeps track of user information (like login status or preferences) as they navigate through your site.
   - The data is stored on the server, and each user has a unique **session ID**.

2. **How It Works**  
   - You start a session using `session_start()`.
   - You can then store data in the `$_SESSION` variable like this:
     ```php
     $_SESSION['username'] = 'John';
     ```
   - The data remains available until the session ends (e.g., when the user logs out or closes the browser).

3. **Why Use It?**  
   - Unlike cookies, session data is not stored on the user's computer, making it more secure for sensitive information.
   - Useful for tasks like keeping a user logged in or managing a shopping cart.

4. **Example:**
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

### Analogy:  
Imagine you’re at a theme park, and you get a wristband when you enter (session ID). The park keeps your information (like tickets bought, food orders, etc.) in their system linked to your wristband. When you leave the park, all your data is cleared. This is how `$_SESSION` works!

