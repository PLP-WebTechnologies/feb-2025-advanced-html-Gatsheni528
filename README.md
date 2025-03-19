# Advanced HTML5 Elements and Forms

## Objectives
Implement HTML5 images, lists, tables, forms and input types.
Use form validation attributes.
Apply multimedia elements such as audio and video.

## Instructions

- Create an index.html file.
- Add an ordered list with roman numerals
- Add an external image from pexels.com
- Add a table of 5 contacts with; name, address, mobile and emails
- Add a registration form

>[!NOTE]
>  The registration form should have:
>- Name, email, password, and date fields.
>- A dropdown, radio buttons, and checkboxes.
>- Proper labels and placeholders.
>- Required fields and validation attributes.
>- Ensure proper indentation and commenting.
 
# Tasks
- Create a well-structured HTML5 document.
- Ensure semantic correctness.

Happy Coding! 💻✨
 Here is My assignment:

 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multimedia Webpage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        table {
            border-collapse: collapse;
            width: 100%;
            margin: 20px 0;
        }
        th, td {
            border: 1px solid black;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        .error {
            color: red;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <h1>Welcome to My Multimedia Page</h1>

    <!-- Embedded Image -->
    <h2>Featured Image</h2>
    <img src="https://via.placeholder.com/400x200" alt="Sample Image" style="max-width: 100%; height: auto;">

    <!-- Audio Element -->
    <h2>Listen to This Audio</h2>
    <audio controls>
        <source src="https://www.w3schools.com/html/horse.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <!-- Video Element -->
    <h2>Watch This Video</h2>
    <video width="400" controls>
        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
        Your browser does not support the video element.
    </video>

    <!-- Registration Form -->
    <h2>Register Here</h2>
    <form id="registrationForm" onsubmit="return validateForm()">
        <label for="username">Username:</label><br>
        <input type="text" id="username" name="username" required minlength="3" maxlength="20"><br>
        <span id="usernameError" class="error"></span><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" required><br>
        <span id="emailError" class="error"></span><br>

        <label for="password">Password:</label><br>
        <input type="password" id="password" name="password" required minlength="6"><br>
        <span id="passwordError" class="error"></span><br>

        <input type="submit" value="Register">
    </form>

    <!-- Table -->
    <h2>Sample Table</h2>
    <table>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
        <tr>
            <td>John Doe</td>
            <td>28</td>
            <td>New York</td>
        </tr>
        <tr>
            <td>Jane Smith</td>
            <td>34</td>
            <td>Los Angeles</td>
        </tr>
    </table>

    <!-- List -->
    <h2>My Favorite Things</h2>
    <ul>
        <li>Music</li>
        <li>Movies</li>
        <li>Technology</li>
        <li>Travel</li>
    </ul>

    <!-- JavaScript for Form Validation -->
    <script>
        function validateForm() {
            let isValid = true;
            const username = document.getElementById('username').value;
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            // Username validation
            if (username.length < 3 || username.length > 20) {
                document.getElementById('usernameError').textContent = 'Username must be 3-20 characters';
                isValid = false;
            } else {
                document.getElementById('usernameError').textContent = '';
            }

            // Email validation
            const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailPattern.test(email)) {
                document.getElementById('emailError').textContent = 'Enter a valid email';
                isValid = false;
            } else {
                document.getElementById('emailError').textContent = '';
            }

            // Password validation
            if (password.length < 6) {
                document.getElementById('passwordError').textContent = 'Password must be at least 6 characters';
                isValid = false;
            } else {
                document.getElementById('passwordError').textContent = '';
            }

            return isValid;
        }
    </script>
</body>
</html>
