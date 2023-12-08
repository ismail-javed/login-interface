# login-interface
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-image: url('https://www.highereducationdigest.com/wp-content/uploads/2022/09/Meerut-Institute-of-Engineering-and-Technology-550x330.jpg'); /* <!-- Add background image here --> Replace the URL with your image */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            height: 100vh;
        }

        .login-container, .signup-container {
            max-width: 400px;
            margin: 50px auto;
            padding: 20px;
            border: 1px solid #ccc;
            background-color: rgba(255, 255, 255, 0.9);
        }

        #company-logo {
            width: 38%;
            margin-bottom: 20px;
        }

        .input-column {
            width: 40%;
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
        }

        #password {
            width: 100%;
        }

        .password-condition {
            font-size: 12px;
            color: #888;
        }

        .forgot-password {
            color: blue;
            cursor: pointer;
        }

        .sign-up {
            color: #333;
            cursor: pointer;
        }
    </style>
    <title>Login</title>
</head>
<body>
    <div class="login-container">
        <img id="company-logo" src="https://www.miet.ac.in/assets/frontend/images/MIET_Logo.png" alt="Company Logo">
        <div class="input-column">
            <label for="email">Email or Phone Number</label>
            <input type="text" id="email" placeholder="Enter email or phone number">
        </div>
        <div class="input-column">
            <label for="password">Password</label>
            <input type="password" id="password" placeholder="Enter password">
            <p class="password-condition">Password must contain at least 1 numeric, 1 small and 1 capital alphabet, and at least one special character.</p>
        </div>
        <p class="forgot-password">Forget Password</p>
        <p class="sign-up" onclick="openSignUpPage()">Sign Up</p>
        <button onclick="login()">Login</button>
    </div>

    <div class="signup-container" style="display: none;">
        <h1 style="font-size: 28%;">Sign Up</h1>
        <div class="input-column">
            <label for="firstName">First Name</label>
            <input type="text" id="firstName" placeholder="Enter your first name">
        </div>
        <div class="input-column">
            <label for="middleName">Middle Name</label>
            <input type="text" id="middleName" placeholder="Enter your middle name">
        </div>
        <div class="input-column">
            <label for="lastName">Last Name</label>
            <input type="text" id="lastName" placeholder="Enter your last name">
        </div>
        <!-- Add the rest of the sign-up form here -->
    </div>

    <script>
        function login() {
            var email = document.getElementById("email").value;
            var password = document.getElementById("password").value;

            // Check password conditions
            if (!validatePassword(password)) {
                alert("Password must meet the specified conditions.");
                return;
            }

            // Check email validity
            if (!validateEmail(email)) {
                alert("Invalid email address.");
                return;
            }

            // Perform login logic (not implemented in this example)
            // You would typically send the credentials to a server for authentication.
        }

        function validatePassword(password) {
            // Password must contain at least 1 numeric, 1 small, 1 capital alphabet, and at least one special character.
            var passwordRegex = /^(?=.\d)(?=.[a-z])(?=.[A-Z])(?=.[\W_]).{8,}$/;
            return passwordRegex.test(password);
        }

        function validateEmail(email) {
            // Simple email validation (you might want to use a more sophisticated approach)
            var emailRegex = /\S+@\S+\.\S+/;
            return emailRegex.test(email);
        }

        function openSignUpPage() {
            // Hide the login container and show the sign-up container
            document.querySelector('.login-container').style.display = 'none';
            document.querySelector('.signup-container').style.display = 'block';
        }
    </script>
</body>
</html>
